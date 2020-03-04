# Knative demo


## 01-deploy

```
cd 01-deploy

kubectl apply -f hello-world.yaml

kubectl -n demo get route

kubectl -n demo get route

curl helloworld.demo.34.65.60.22.nip.io
```


## 02-autoscaling

```
kubectl apply -f autoscaling.yaml
kubectl -n demo get route
watch kubectl -n demo get pods

curl http://autoscaling.demo.34.65.60.22.nip.io

hey -c 30 -z 30s http://autoscaling.demo.34.65.60.22.nip.io
```


## 03-traffic-management

```
for i in {1..20}; do curl http://myapp.demo.34.65.60.22.nip.io; sleep 1; done


curl http://prod-myapp.demo.34.65.60.22.nip.io

curl http://candidate-myapp.demo.34.65.60.22.nip.io
```