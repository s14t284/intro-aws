# Hands-on #4: サーバーレス入門

## Serverless architecture

- 計算のリソースはクラウドプロバイダーが全て管理し、仮想インスタンスを一台まるごと借りるのではなく，実行したいプログラムをクラウドに提出するようなアーキテクチャ
- 既存のServerfulな実行形態では、処理の実行が少ない時でもサーバーの電気代や管理費、クラウドの賃料はかかるため、いつ何時でもそれなりのコストがかかる
- Serverless architecture を使うことで、処理を実行しているときだけ、お金がかかるため、うまく使えば費用の軽減になる

### Lambda

- 実行したいプログラムを予め登録しておき、所定の場所にリクエストすることで登録されたプログラムが実行される
- Python, Node.js, ruby, Java, Go などが現在サポートされている

### S3(Simple Storage Service)

- サーバーレスストレージ
- 通常であれば、サーバーにDBやファイルストレージを配置してデータを保管する
  - マシンとOSが存在する必要があり、パワーが必要でなくてもCPUリソースが必要になる
  - マシンごとにデータ領域のサイズが決まってしまう
- サーバーを用意しなくてもデータを保管でき、データ領域は自動で拡張されていくようなサービス
- 料金は保存してあるデータの総容量と外部へのデータ転送の総量で決定
  - ただし、データをs3に入れる通信は無料
  - AWS内の同じリージョン間のサービスにデータを転送するのも無料

### DynamoDB

- S3と同じようにサーバーを意識せずに利用できるDB
- 分散型のDBで、スケーリングはAWSが自動で行ってくれる

### その他のサーバーレスクラウドの構成要素

- API Gateway
- Fargate
- SNS(Simple Notification Service)
- Step Functions