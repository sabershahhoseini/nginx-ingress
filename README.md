# NGINX Ingress Controller On Kubernetes 
Setup NGINX Ingress Controller On Kubernetes.

Clone the repo:

```
git clone 'https://github.com/sabershahhoseini/nginx-ingress'
```

Deploy the chart:

```
helm upgrade --install ingress-nginx ingress-nginx --repo https://kubernetes.github.io/ingress-nginx --namespace ingress-nginx --create-namespace
```

Create namespace for your deployment:

```
kubectl create ns frontend
```

Apply the manifests. You need to change `ingress.yml` to use your own domain. You probably need to change `frontend-deployment.yml` and use your own docker image. Also you may need to change `frontend-service.yml` and set your application port. 

```
kubectl apply -f frontend-deployment.yml
kubectl apply -f frontend-service.yml
kubectl apply -f ingress.yml
```

I mean, how easy was that?
