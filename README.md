Enterprise EKS Monitoring with Prometheus, Grafana, Node Exporter, Blackbox Exporter and Alertmanager


Alertmanger,Blackbox_exporter,Prometheus,Grafana are setup as the container using the offical docker hub images

Example official repositories:
prom/prometheus
grafana/grafana
prom/blackbox-exporter
prom/alertmanager 


//Passing required  configuration to  prometheus
docker run -d \
--name prometheus_node_discovery \
-p 9090:9090 \
-v $(pwd)/prometheus_node_discovery.yml:/etc/prometheus/prometheus.yml \
-v $(pwd)/alert_rules.yml:/etc/prometheus/alert_rules.yml \
prom/prometheus

//Passing required configuration to alert manger
docker run -d \
--name alertmanager \
-p 9093:9093 \
-v $(pwd)/alertmanager.yml:/etc/alertmanager/alertmanager.yml \
prom/alertmanager



![Architecture](images/Monitoring.png)
