# Kubernetes Elasticsearch snapshots

A role to deploy [curator](https://hub.docker.com/r/bobrik/curator) on a Kubernetes cluster. Makes automatic backups of Elasticsearch indexes to S3.
Your elasticsearch instance already has to be configured for S3 backups to get this role working.

Requirements
------------

This role depends on you having a kubernetes cluster. It uses a [headless service](https://kubernetes.io/docs/concepts/services-networking/service/) for discovery of elasticsearch nodes.


Role Variables
--------------

The following variables should be set before using this role:     

* logstash_backup_base_path: default is "k8s-{{ cluster_name }}"
* k8s_namespace: default is ""
* logstash_backup: Name of the S3-bucket. default is "logstash-backups"
* curator_older_than_unit: default is "days"
* curator_older_than_unit_count: default is 12

For more variables you can override, look into [defaults/main.yml](defaults/main.yml)
