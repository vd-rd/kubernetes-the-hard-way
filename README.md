# Kubernetes The Hard Way

This tutorial walks you through setting up Kubernetes the updated (hard) way. This is an opionated guide. This guide is not for people looking for a fully automated command to bring up a Kubernetes cluster. It mixes knowledge from multiple sources where documentation is still scarce.

Kubernetes The Hard Way is optimized for learning, which means taking the long route to ensure you understand each task required to bootstrap a Kubernetes cluster. 

> The results of this tutorial should not be viewed as production ready, and may receive limited support from the community, but don't let that stop you from learning!

## Copyright

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
Huge shout out to Kelsey Hightower for his work.

## Target Audience

The target audience for this tutorial is someone planning to support a Kubernetes cluster on bare metal/home lab as close to production as possible.

## Cluster Details

Kubernetes The Hard Way guides you through bootstrapping a highly available Kubernetes cluster with end-to-end encryption between components and RBAC authentication.

Ok, so the magic number of everything is 3. That means that in the end the Cluster will be composed of something simillar to this:
 * 3 control plane nodes (running kubelet, api-server, node-controller, kube-scheduler)
 * 3 infra nodes (running etcd, nginx-ingress, quay, prometheus, grafana)
 * 3 storage nodes (running ceph components to provide block/object storage)
 * 3 worker nodes (for general purpose apps)
 
Regarding infrastructure assumptions, constraints:
 * Centos 8 OS
 * Selinux active and watching out for us
 * crun as runtime ( paves the way for cgroup v2)
 * cri-o for pods
 * nf_tables without downgrade for legacy 


## Labs
This tutorial assumes that you can provision VMs and networking between them/outside world where needed.



* [Prerequisites](docs/01-prerequisites.md)
* [Installing the Client Tools](docs/02-client-tools.md)
* [Provisioning Compute Resources](docs/03-compute-resources.md)
* [Provisioning the CA and Generating TLS Certificates](docs/04-certificate-authority.md)
* [Generating Kubernetes Configuration Files for Authentication](docs/05-kubernetes-configuration-files.md)
* [Generating the Data Encryption Config and Key](docs/06-data-encryption-keys.md)
* [Bootstrapping the etcd Cluster](docs/07-bootstrapping-etcd.md)
* [Bootstrapping the Kubernetes Control Plane](docs/08-bootstrapping-kubernetes-controllers.md)
* [Bootstrapping the Kubernetes Worker Nodes](docs/09-bootstrapping-kubernetes-workers.md)
* [Configuring kubectl for Remote Access](docs/10-configuring-kubectl.md)
* [Provisioning Pod Network Routes](docs/11-pod-network-routes.md)
* [Deploying the DNS Cluster Add-on](docs/12-dns-addon.md)
* [Smoke Test](docs/13-smoke-test.md)
* [Cleaning Up](docs/14-cleanup.md)
