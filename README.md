# ansible_deploy_collectd_prometheus
Deploy collectd , collectd exporter and Prometheus for performance monitoring with ansible
# Deploying Performance monitoring and metrics gathering with Collectd and Prometheus
Ansible playbooks to deploy collectd and prometheus based monitoring solution

# Prerequisites
See above list for Sensu
# Package versions

|Package                  |Version      |Ports                                       |
|-------------------------|-------------|--------------------------------------------|
|Prometheus               |2.0.0        |TCP 9090                                    |
|Collectd                 |5.8.0.1      |                                            |
|Collectd exporter        |0.4.0        |UDP/TCP defined in group_vars/all file      |
|OpenStack exporter       |0.2.0        |TCP defined in group_vars/all file          |
|Prometheus Alert Manager |0.12.0       |TCP 6783                                    |
|SNMP Trapper Webhook     |             |TCP 9099                                    |

## How to run
To run playbooks first update the group_vars/all with environment specific parameters.
Then run the playbooks in the playbooks folder to deploy individual components or all
at the same time. Each components can be deployed on their own. There are playbooks to
deploy as well as remove as this will help in testing.

Following shows deploying just grafana
```
ansible-playbook playbooks/install_grafana.yaml
```
To install all the components one at a time,
```
ansible-playbook playbooks/install_collectd_exporter.yaml
ansible-playbook playbooks/install_prometheus.yaml
ansible-playbook playbooks/install_alert_manager.yaml
ansible-playbook playbooks/install_snmptrapper.yaml
```
To install all components and configure sensu checks and alerts
```
ansible-playbook playbooks/install_all.yaml
```
To configure target hosts for collectd client ,
```
ansible-playbook playbooks/configure_collectd_targets.yaml
```

## To Do
* 

