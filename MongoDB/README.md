# MongoDB

## Problem Statement

As of now (Aug/2018) **Cosmos DB** is either a clunky or an expensive NoSQL Document database.
- **Clunky** – if you use the “Provisioned Throughput” ~$22/month and put everything in one collection. _(this is non-standard relative to how Mongo developers think about using a document database)_
- **Expensive** – if you use the “Provision throughput for a set of containers collectively”, which has a minimum of 50K RUs ~$2000/month.

## Questions

- What would it take to run a MongoDB Replica Set on Kubernetes 
- How performant or cost effective would it be compared to either **Clunky** or **Expensive** above? 
- What are the minimum number of nodes needed (minimum cost)? 
- How do we scale it up? 
- At what point does Cosmos just makes more sense?


After talking with experts around the office, I found  some [guidance](http://k8smongodb.net/) that looks like it is up to date.

From reading, I'm pretty sure we want to us Azure Files for [persistent volumes](https://docs.microsoft.com/en-us/azure/aks/azure-files-dynamic-pv)


Read through [part 1](http://pauldone.blogspot.com/2017/06/deploying-mongodb-on-kubernetes-gke25.html), [part 2](http://pauldone.blogspot.com/2017/06/mongodb-kubernetes-production-settings.html) and [part 4](http://pauldone.blogspot.com/2017/07/sharded-mongodb-kubernetes.html) for an overview of deploying mongo on kubernetes

Together with the [script](https://github.com/pkdone/azure-acs-mongodb-demo/blob/master/scripts/generate.sh) he wrote for [deploying to Azure](https://github.com/pkdone/azure-acs-mongodb-demo) should get the job done.

Then investigate [Kubernetes](https://docs.docker.com/docker-for-mac/kubernetes/#specify-a-namespace), [Draft](https://github.com/Azure/draft/blob/master/docs/install-minikube.md) and [Helm](https://github.com/helm/helm)

