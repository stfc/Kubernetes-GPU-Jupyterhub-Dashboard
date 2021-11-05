# Kubernetes-GPU-Jupyterhub-Dashboard
A dashboard to monitor kubernetes cluster with GPU and JupyterHub for use with the 
Jupyterhub-Prometheus-Stack-Production ansible-playbook

## Demo
![Alt Text](https://github.com/Donald954732/Kubernetes-GPU-Jupyterhub-Dashboard/raw/main/demo/Demo-Dashboard.gif)

## Notes
### Version
- `dashboard.json`: for headless deployment with helm dashboard provider
  - This version comes with variable hard coded onto the dashboard
- `dashboard-portable.json`: **For manual deployment using WebUI**   

### Pods selector
The Dashboard use regex to identifly JupyterHub user pods using prefix (`jupyter-` if installed with default helm chart). This can be changed in `jhubNameLabel` in `Settings -> Variables`. 

Avoid deploying other pods with the same prefix.

### Potential change in syntax
The promQL to querry the metrics can change base on the exporter version. Check the querry if some values are missing.

## Other Use case
Can be used to monitor Kubernetes cluster with other applications by deleting the irrelevent tabs (e.g. JupyterHub, GPU).

## Based On
- [1 K8S for Prometheus Dashboard](https://github.com/starsliao/Prometheus)
- [Grafana Dashboards for JupyterHub](https://github.com/jupyterhub/grafana-dashboards)
- [NVIDIA DCGM Exporter Dashboard](https://grafana.com/grafana/dashboards/12239)
