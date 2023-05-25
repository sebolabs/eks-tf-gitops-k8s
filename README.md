# eks-tf-gitops-k8s
Kubernetes configuration for different types of deployments use cases using ArgoCD applications and Helm charts.

The code here is used by the [EKS-TF-GitOps](https://github.com/sebolabs/eks-tf-gitops) project.

## StarTrek
The "App of apps" ArgoCD pattern is used.

### Charecteristics
* Terraform points to the `apps/startrek` folder as the source of the root application
* the parent application configuration is entirely controlled with Terraform
* allows individual applications configurations to be different per environment with the use of values files
* allows individual applications' resources (services) configuration to be different per environment with the use of values files
* services are represented by dedicated Helm charts

## StarWars
Multi-application concept with a single Helm chart template used as dependency.

### Charecteristics
* Terraform points to the `apps/starwars/apps/*` folders as the source of individual applications
* application configuration is entirely controlled with Terraform
* application resources' (services) configuration templates are defined using a single Helm chart blueprint
* the blueprint is meant to contain templates for all relevant K8s resources
* services' configuration of individual resources is provided entirely with the use of values files
* allows services' configuration to be different per environment with the use of values files

## Avengers
The "ApplicationSet" ArgoCD controller is used.

**>>> YET TO COME!**

### Charecteristics
* ...
