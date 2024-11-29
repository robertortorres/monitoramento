

# dashboard

Sistema de monitoramento com **Grafana**+**Prometheus**

<br>

## O que irá monitorar:
* Uso de CPU/RAM/Disk/Network/Temperatura/etc (node-exporter)
* Uso de Docker Container (cadvisor)
* S.M.A.R.T (script-exporter)

<br>

## Docker Stacks

Pode acessar a interface web `http://<host>:<porta>`.

|Imagem Docker|Nome do Container|Descrição|Porta|
|-|-|-|-|
|grafana/grafana|grafana|Visualize dados de monitoramento com fonte de dados `prometheus`.|3000|
|prom/prometheus|prometheus|Extraia dados de métricas de cada exportador e armazene-os.|9090|
|gcr.io/google-containers/cadvisor|cadvisor|Colete dados de contêineres.|9250|
|prom/node-exporter|node-exporter|Coletar dados do sistema.|9100|
|matusnovak/prometheus-smartctl|script-exporter|Exporta todos os dados disponíveis do smartctl|9902|

<br>

## Instalação
```bash
$ sudo git clone https://github.com/robertortorres/monitoramento
$ cd monitoramento
$ docker-compose up -d
```

Acesse o grafana pelo endereço `http://localhost:3000`
