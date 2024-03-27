# Ingate Dashboards for Grafana

The dashboards here are intended to provide visualisation for all SIP and generic metrics available in the v6.3.x firmware. The layout and data presented in each dashboard is the same - the only differences between dashboards are the back-end DB that they use i.e. how its queries are made. It is safe to install and use multiple copies of the same or different dashboards. Future dashboards and their panels may provide additional statistics as they become available in the firmware and should retain compatibility with older firmwares.

To read which metrics are available for your Firmware version, please refer to the user-manual. The minimum required firmware version for TSDB and metrics is v6.3.0. 

[v6.3 SIP metrics](https://account.ingate.com/manuals/6_3_1/reference_guide_6_3_1.html#_ingate_sip_metrics)


Dashboards are currently available for:

- [x] [InfluxDB](/ingatesystems-63x-influxdb.json) ( InfluxDB supports CollectD, Graphite, OpenTSDB formats )
- [x] [Graphite](/ingatesystems-63x-graphitedb.json) 
- [x] [Prometheus](/ingatesystems-63x-prometheus.json) 
- [ ] OpenTSDB

## Preview
![InfluxDB dashboard](/InfluxDB-screenshot.png)


## Install a dashboard

Refer to Grafana instructions for [how to import](https://grafana.com/docs/grafana/latest/reference/export_import/#importing-a-dashboard) a dashboard; paste the JSON content or upload the JSON file from the GUI. Or (also in your docker installation), put the JSON file(s) in the `/etc/grafana/provisioning/dashboards/` folder and restart Grafana. 

## Information on InfluxDB dashboard

To use the InfluxDB dashboard requires:
* an InfluxDB instance running
* SBC(s) [sending data to the DB instance](https://account.ingate.com/manuals/6_3_1/reference_guide_6_3_1.html#_database_servers)
* an [InfluxDB datasource](https://grafana.com/docs/grafana/latest/features/datasources/influxdb/) configured in Grafana


The InfluxDB dashboard was built progressively on Grafana v6.3-v6.7, and was exported from Grafana 10.4.1. 

Note: InfluxDB for CollectD requires only the default `types.db`.


## Information on GraphiteDB dashboard

To use the GraphiteDB dashboard requires:
* a GraphiteDB instance running
* SBC(s) [sending data to the DB instance](https://account.ingate.com/manuals/6_3_1/reference_guide_6_3_1.html#_database_servers)
* a [GraphiteDB datasource](https://grafana.com/docs/grafana/latest/features/datasources/graphite/) configured in Grafana


The InfluxDB dashboard was built progressively on Grafana v6.3-v6.7, and was exported from Grafana 10.4.1. 

Note: GraphiteDB requires only port 2003


## Information on Prometheus dashboard

To use the Prometheus dashboard requires:
* a Prometheus instance running
* [Prometheus configured to scrape an Ingate SBC which has Prometheus configured](https://account.ingate.com/manuals/6_3_1/reference_guide_6_3_1.html#_prometheus_exporter)
* a [Prometheus datasource](https://grafana.com/docs/grafana/latest/features/datasources/prometheus/) configured in Grafana


The GraphiteDB dashboard was built on Grafana v7, and was exported from Grafana 10.4.1. 


We welcome PRs, fixes and contributions for these dashboards and other DB types.


# Version history

* v1.0 - initial release - 2020-05-20
* v1.1 - update panels via Grafana 10.4.1 to remove angular based graphs - 2024-03-27