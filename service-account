In Kubernetes, 𝐒𝐞𝐫𝐯𝐢𝐜𝐞 𝐚𝐜𝐜𝐨𝐮𝐧𝐭𝐬 are primarily used for authenticating and authorizing pods to interact with the Kubernetes API server or other cluster resources.

Automated Authentication: When you create a pod, you can associate it with a specific service account. The Kubernetes runtime environment automatically provides credentials (such as API tokens) to pods associated with a service account, enabling them to interact with the Kubernetes API server and other resources.

RBAC Integration: Kubernetes Role-Based Access Control (RBAC) can be used to define fine-grained access control policies for service accounts. You can specify what actions a service account is allowed to perform on specific Kubernetes resources.

Default Service Account: Every Kubernetes namespace has a default service account automatically created for it. If you don't explicitly specify a service account for a pod, it will use the default service account of its namespace.

mount location in Pod: /var/run/secrets/kubernetesio/serviceaccount/token

Custom Service Accounts: You can create custom service accounts if you need to assign specific permissions or control to a group of pods. Custom service accounts can be associated with pods when they are created.

Here's a basic example of how to create and use a custom service account in Kubernetes:

Create a Custom Service Account:
You can create a custom service account using a YAML manifest like this:

apiVersion: v1
kind: ServiceAccount
metadata:
 name: my-service-account

Apply this manifest using kubectl apply -f custom-service-account.yaml.

Associate the Service Account with a Pod:
In the pod specification, you can specify the service account to use:

apiVersion: v1
kind: Pod
metadata:
 name: my-pod
spec:
 serviceAccountName: my-service-account
 containers:
 - name: my-container
  image: my-image

This pod will use the custom service account my-service-account for authentication and authorization when interacting with Kubernetes resources.

RBAC Policies:
To control what resources and actions the my-service-account can perform, you can define RBAC policies that grant permissions to this service account.

Service accounts are essential for maintaining security and access control within a Kubernetes cluster.
