# django-deploy-sample

## 本リポジトリの内容

Django アプリケーションをサーバー上にデプロイする手順と、設定例を紹介するリポジトリです。

## 前提

AWS EC2 と RDS を利用して、Django アプリケーションを動作させることを想定した内容となっています。  
設定する VPS 環境は、AWS 特有のものはほとんど利用していません。  
別のパブリッククラウドを利用する場合も、流用可能と思います。

## 構成

設定を行うサーバ構成を簡易的に示します。

```
（ブラウザ）
  ↓ ↑  HTTP
Nginx（Webサーバー）
  ↓ ↑ TCPまたはソケット通信
uWSGI（アプリケーションサーバ―）
  ↓ ↑ プログラム呼び出し
Django アプリケーション
  ↓ ↑ TCP通信
PostgresSQL（データベース）
```

## ドキュメント

設定方法の詳細は、別のファイルにまとめています。  
以下のディレクトリを参照してください。  
[docs](/docs/)

## 非対応事項

当リポジトリに掲載の内容は、Django アプリケーションを AWS 上で永続化させる設定手順を示したものです。  
個別のアプリケーション向けの最適な設定までは解説に含めていません。  
また、ネットワーク構成などについても、取り扱っていません。  
本番環境の構成においては、上記の点も考慮したうえで環境を構築する必要がありますので、ご留意ください。
