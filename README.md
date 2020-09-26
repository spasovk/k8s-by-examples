# k8s-by-examples
training course converted to tasks so one can study by examples

## Tasks at hand:

1. Install VirtualBox or an alternative
2. Install Vagrant
3. Deploys 5 VMs - 2 Master, 2 Worker and 1 Loadbalancer with the name 'kubernetes-ha-* '

	* IPs in your private subnet
	* Allow internet
	* Install docker on workers
	* On all nodes allow network forwarding in IP Tables
	* Setup keys from your workstation to the VMs
	* Install kubeclt on your workstation 

4. Certificates and their distribution them on the master nodes:
	
	* Generate CA key, csr and crt
	* Admin key crt
	* Controller Manager
	* Kube Proxy
	* Scheduler
	* K8s API Server
	* ETCD
	* Service account

5. Generate kubeconfigs (needed for authentication)
	
	- Note down the Loadbalancer IP address

	* The kube-proxy 
	* The kube-controller-manager
	* The kube-scheduler
	* The admin

	- Copy the appropriate kube-proxy kubeconfig files to each worker instance:
	- Copy the appropriate admin.kubeconfig, kube-controller-manager and kube-scheduler kubeconfig files to each controller instance:

6. Generate encryption key and encryption config file

7. Download and install the etcd binaries

	- Configure the etcd server
	- Verify it

8. Bootstrap the Kubernetes control plane

	- kube-aptiserver
	- kube-controller-manager
	- kube-scheduler
	- kubectl 

9. Provision a k8s frontend Loadbalancer

10. Bootstrap the worker nodes

	- provision the kubelet client certificates
	- kubelet config file
	- transfer the certs, keys and kubeconfig to the worker nodes
	- install kubelet & define service/values 
	- install kube-proxy & define service
	- install kubectl

11. (Optional) TLS bootstrapping the worker nodes

	- kube-apiserver - ensure bootstrap token for authentication is enabled
	- kube-controller-manager - it should have CA.crt and key
	- download and install the binaries for kubelet, kube-proxy and kubectl
	- create the bootstrap token
	- authorize workers to create/approve CSR
	- configure kubelet to TLS Bootsrtap
	- create kubelet config file and service
	- configure kube-proxy config file and service
	- approve the csr request

12. Configure the kubectl

	- Create the admin k8s configuration file

13. Pod networking

	- deploy CNI plugins
	- deploy Weaver or Callico network

14. kube-apiserver to kubelet

	- generate ClusterRole for access from kube-apiserver to kubelet-api
	- bind the ClusterRole to the kubernetes user

15. Deploy the coredns addon

16. Tests

	- data encryption
	- deploy nginx single container pod
	- deploy nodeport service for the nginx
	- check the logs
	- execute command within a container
	- install kubetest & run it
