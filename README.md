# Nginx Kubernetes Deployment

This repository contains YAML files for deploying an Nginx pod and a service to access it in a Kubernetes cluster.

## Steps

# You'll need to have a Kubernetes cluster set up. You can use a local cluster like Minikube, a managed Kubernetes service from a cloud provider.

1. Install Minikube, a tool for running a local Kubernetes cluster:
     brew install minikube

# Install the `kubectl` command-line tool, which is used to interact with Kubernetes clusters.

2. Start the Minikube cluster:
     minikube start
   
3. Install kubectl, the command-line tool for interacting with Kubernetes clusters:
     brew install kubernetes-cli

4. Verify that kubectl is installed correctly:
     kubectl version --client
  
5. Check the cluster information:
     kubectl cluster-info

# Defines an Nginx pod.

6. Create the YAML file for the Nginx pod:
     vim nginx-pod.yaml

# Defines a NodePort service to access the Nginx pod from outside the cluster.

7. Create the YAML file for the Nginx service:
     vim nginx-service.yaml

8. Create a new namespace for the deployment:
     kubectl create namespace devops-exercise

# This command creates a new namespace named `devops-exercise` in your Kubernetes cluster. Namespaces are used to organize and isolate resources within the cluster.

9. Deploy the Nginx pod to the `devops-exercise` namespace:
     kubectl apply -f nginx-pod.yaml -n devops-exercise
 
10. Deploy the Nginx service to the `devops-exercise` namespace:
       kubectl apply -f nginx-service.yaml -n devops-exercise

11. Get the IP address of the Minikube cluster:
       minikube ip

12. Get information about the Nginx service:
       kubectl get services -n devops-exercise

13. Access the Nginx service using the Minikube IP and the service URL:
      minikube service nginx-service -n devops-exercise --url
    
# This command retrieves the URL for accessing the `nginx-service` in the `devops-exercise` namespace, which you can then use in your web browser.
