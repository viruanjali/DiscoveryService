mvn clean package
docker build --tag=discoveryservice-ws --force-rm=true .

docker tag 6d624712aa87 amsidhlokhande/photoapp_discoveryservice-ws
docker push amsidhlokhande/photoapp_discoveryservice-ws

docker run -d -p 8010:8010 -e "spring.cloud.config.uri=http://localhost:8012" -v //d/UdemyWorkspace/photoapp-logs/discoveryservice-ws:/api-logs amsidhlokhande/photoapp_discoveryservice-ws

eureka portal url   http://localhost:8010/

