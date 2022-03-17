# Deploy nginx-ingress-controller
Follow these 3 steps to setup nginx ingress controller on kubernetes and create ingress objects

## 1. Deploy nginx ingress controller

```
cd controller
kubectl create -f ingress-controller-deploy.yaml
```
The nginx ingress controller deployed above would listen on nodeport 32555 (http) / 32666 (https).

## 2. Deploy an app and expose with a ClusterIP service

```
cd app
kubectl create -f .
```
A simple kubernetes 'deployment' is made and exposed as a 'service' on port 80.

## 3. Deploy ingress object to access the app deployed above

```
cd ingress
kubectl create -f app-ingress.yaml
```

You can now access the app at http://any-node-IP:32555
