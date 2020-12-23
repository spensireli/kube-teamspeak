# About

This project creates a Teamspeak server that is deployed to a Kubernetes environment. The example is using an NFS backed persistent volume claim but could be easily substituted for an enterprise data store such as EBS etc.

## Usage

```bash
$ kubectl create -f teamspeak-ns.yaml
namespace/teamspeak created
$ kubectl create -f teamspeak-pv.yaml
persistentvolume/pv0005-teamspeak created
$ kubectl create -f teamspeak-pvc.yaml
persistentvolumeclaim/pv0005-teamspeak created
$ kubectl create -f teamspeak-deployment.yaml
deployment.apps/teamspeak created
$ kubectl create -f teamspeak-svc.yaml
service/udp-port created
service/next-port created
service/next-next-port created
```

To get the initial `ServerAdmin privilege key` view the logs at first creation.
```bash
$ kubectl -n teamspeak logs teamspeak-<pod-id>
```
