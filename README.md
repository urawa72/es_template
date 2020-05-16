# Elastcisearch multi nodes docker template

- ElasticsearchをDockerで起動するためのテンプレートです。
- 1クラスター・3ノードで起動します。


## Setup
- dockerイメージをビルドしdocker-composeで起動
```
docker build -t es_7_6_2 .
docker-compose up -d
```

- localhost:5601でKibanaにアクセスし、DevToolでElasticsearchの起動を確認する
- curlでもOK
```
# Kibana
GET /
{
  "name" : "es_1",
  "cluster_name" : "play-cluster",
  "cluster_uuid" : "E52ERSzGSlyeiyHOR5BUJw",
  "version" : {
    "number" : "7.6.2",
    "build_flavor" : "default",
    "build_type" : "docker",
    "build_hash" : "ef48eb35cf30adf4db14086e8aabd07ef6fb113f",
    "build_date" : "2020-03-26T06:34:37.794943Z",
    "build_snapshot" : false,
    "lucene_version" : "8.4.0",
    "minimum_wire_compatibility_version" : "6.8.0",
    "minimum_index_compatibility_version" : "6.0.0-beta1"
  },
  "tagline" : "You Know, for Search"
}

# curl
curl -X GET localhost:9200
```
