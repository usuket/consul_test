# consul_test

consul agent -server -ui -config-file /etc/consul/default.json

docker-compose build --no-cache

https://qiita.com/kz-takahashi/items/c413df2973accbdcb680
curl -s http://localhost:8500/v1/catalog/services  
curl -s http://localhost:8500/v1/catalog/service/consul 
curl -s http://localhost:8500/v1/catalog/nodes 

curl -XPUT -d 'hello, world!' http://localhost:8500/v1/kv/hello/key  
curl -s http://localhost:8500/v1/kv/hello/key | jq '.[].Value | .' -r | base64  -D
dig @127.0.0.1 -p 8600 consul.node.consul any  