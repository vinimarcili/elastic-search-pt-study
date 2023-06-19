# Elastic Search

## Docker Commands

1. `docker pull docker.elastic.co/elasticsearch/elasticsearch:8.8.1`

2. `docker network create elastic`

3. exec:

```bash
docker run \
  --name es01 \
  --net elastic \
  -p 9200:9200 \
  -e discovery.type=single-node \
  -e ES_JAVA_OPTS="-Xms1g -Xmx1g"\
  -e xpack.security.enabled=false \
  -it \
  docker.elastic.co/elasticsearch/elasticsearch:8.8.1
```

```bash
docker run \
  --name kibana \
  --net elastic \
  -p 5601:5601 \
  docker.elastic.co/kibana/kibana:8.2.2
```
