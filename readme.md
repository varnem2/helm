# What did I do to get here.. [https://www.baeldung.com/kubernetes-helm](https://www.baeldung.com/kubernetes-helm)

`install docker & kubernetes`

`choco install kubernetes-helm`

`helm create hello-world`

`helm lint ./hello-world/` -> Returned with `1 chart(s) linted, no failures`

`helm template ./hello-world/` -> Returned with the contents of [template.yml](./template.yml)

`helm install --name hello-worl ./hello-world` -> Deployed the service as well as some additional notes to get the pod running.

`
    NOTES:
    1. Get the application URL by running these commands:
    export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=hello-world,app.kubernetes.io/instance=hello-worl" -o jsonpath="{.items[0].metadata.name}")        
    echo "Visit http://127.0.0.1:8080 to use your application"
    kubectl port-forward $POD_NAME 8080:80
`

After running the port-forward command it worked and was able to see the nginx page on port 8080.