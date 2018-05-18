# sample-autoscaling-app for OpenShift

### Create Openshift Project 
```sh
oc new-project hello-world
```

### Create application 
```sh
oc create -f hello-world.yaml
```

### Create horizontal scaler
```sh
oc autoscale dc/hello-world --min 1 --max 15 --cpu-percent=5
```

### Pump  some test traffic
```sh
ab -n 1000000 -c 75 http://xxxxxxx
```