## Dockerインストール
インストール方法は以下記事参照
https://docs.docker.jp/get-started/index.html

## バージョン
- Ruby： 3.2.1
- Ruby on Rails： 7.0.4
- React： 18系

## 環境構築
※Dockerのセットアップが完了してから行うこと

### リポジトリをクローン
```
% git clone git@github.com:takuya178/rails-react.git
```

```
cd rails-react/
```

### dockerコンテナ立ち上げ
```
docker compose up -d
```

### コンテナが立ち上がっていることを確認
```
% docker compose ps
NAME                  COMMAND                  SERVICE             STATUS              PORTS
rails-react-api-1     "entrypoint.sh /bin/…"   api                 running             0.0.0.0:3001->3000/tcp             // Railsコンテナ
rails-react-db-1      "docker-entrypoint.s…"   db                  running             0.0.0.0:3306->3306/tcp, 33060/tcp  // DBコンテナ
rails-react-front-1   "docker-entrypoint.s…"   front               running             0.0.0.0:3000->3000/tcp             // Reactコンテナ
```
### Railsが起動していることを確認
http://localhost:3001 にアクセス
![スクリーンショット 2023-06-03 11 20 19](https://github.com/takuya178/rails-react/assets/78284579/7d664c88-3d39-47ae-8b63-a7ac2387b7ae)

## Reactの起動
### フロントコンテナに入る
```
% docker compose exec front bash
```
### パッケージのインストール
```
npm install
```
### React起動
```
npm start
```

### Reactが起動しているか確認
http://localhost:3000 にアクセス
![スクリーンショット 2023-06-03 11 28 57](https://github.com/takuya178/rails-react/assets/78284579/08bce9ca-e29f-4f01-a2a3-1fca8219429c)

