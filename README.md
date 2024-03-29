# cloud9 with AWS development environment

## 起動と終了
### 起動

```
docker-compose up -d
```
### 終了

```
docker-compose down
```

## 動作確認
ブラウザで以下のURLを開くとcloud9のトップ画面が表示される。

```
http://localhost:8080
```

![cloud9_top](https://user-images.githubusercontent.com/14244767/66695569-4087ca00-ecfe-11e9-9d65-a91e67e39689.png)



ログインユーザー名とパスワードのデフォルトは以下の通り。

（docker-compose.yml内で指定されているため変更可能）

```
USERNAME: user
PASSWORD: pass
```



## ディレクトリ構成
```
├── Dockerfile
├── README.md
├── docker-compose.yml
├── workspace
└── aws
```



- workspace

  ホストとコンテナが共有するディレクトリ。cloud9で作成したソースコードが格納される。

- aws

  ホストとコンテナが共有するディレクトリ。AWS認証ファイルの保管用。「aws configure」で生成した認証ファイルはこのディレクトリから読み込まれる。

## AWS認証ファイルの作成

1. cloud9の下部のタブからターミナルを起動する。無い場合はメニューの「Window - New Terminal」から起動する。

2. aws configureコマンドを実行し、認証ファイルを作成する。（作成方法は公式サイトを参照）

   （以降はdocker-compose実行の度に同じ認証ファイルが使用される。）
   
## コーディングと実行
1. Python3.6が使用できる状態になっているため、[File]-[New File]からpythonfファイルを新規作成し、コーディングを進める。

2. Runを実行、もしくはターミナルでpythonコマンドを実行すると、コードが実行される。

## ライブラリの追加

Pythonのライブラリはpipコマンドで追加する。「Window - New Terminal」からターミナルを起動しpipコマンドを実行できる。