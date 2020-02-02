# fabcar

引用元<br>
[https://github.com/hyperledger/fabric-samples](https://github.com/hyperledger/fabric-samples/tree/release)

Apache License, Version 2.0なのでいじくったソース載せてもいいはず・・

# 使い方

このQiitaの記事などを参考にHyperledgerのfabcarサンプルを動作させる準備を進めます<br>

[Hyperledger Fabricのチュートリアル触ってみた(FabCar)](https://qiita.com/ImYuya/items/21eb529b66c666d61129)

元の**fabcar.go**を差し替えて**startFabric.sh**からチェーンコードを起動します<br>
**node enrollAdmin.js**と**node registerUser.js**は元コードをそのまま実行し、ユーザー登録をします<br>
その後、**node invoke.js**を実行して、メールアドレスと紐づくスマホのIMEIを登録します。curlなどで以下のように登録します。<br>

```
curl -X POST -H 'Content-Type: application/json' http://localhost:28080/input -d '{ "Mail": "test@test.com", "IMEI": "112233445566778"}'
```

登録が終わったら**node query.js**を起動させて、こちらもcurlなどでAPIリクエストをなげて確認してみましょう<br>

```
curl -X POST -H 'Content-Type: application/json' http://localhost:38080/query -d '{ "Mail": "test@test.com", "IMEI": "112233445566778"}'
```

**0**が返ってくればOKです<br>

# License
Hyperledger Project source code files are made available under the Apache License, Version 2.0 (Apache-2.0), located in the LICENSE file. Hyperledger Project documentation files are made available under the Creative Commons Attribution 4.0 International License (CC-BY-4.0), available at (http://creativecommons.org/licenses/by/4.0/)[http://creativecommons.org/licenses/by/4.0/].
