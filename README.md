Creating a Kubernetes Ingress
First, let’s create two services to demonstrate how the Ingress routes our request. We’ll run two web applications that output a slightly different response.

Create the resources

$ kubectl apply -f apple.yaml
$ kubectl apply -f banana.yaml

Now, declare an Ingress to route requests to /apple to the first service, and requests to /banana to second service. Check out the Ingress’ rules field that declares how requests are passed along.


Create the Ingress in the cluster

$ kubectl create -f ingress.yaml

Check Output

$ curl -kL http://localhost/apple
apple

$ curl -kL http://localhost/banana
banana
