NOTE: I have moved away from using the ansible solution to a cloud-init method. Please refer to https://github.com/salimwp/k8s-bootstrap

This ansible playbook is created to spin up a small Kubernetes cluster. Rather than using minikube we can use this to practice staging or near production deployments and fine tuning of clustered solutions.

Note: this installation is just a basic installation designed to get familar with k8s and plan workflows. Security hardening of the base CentOS servers and k8s is left for your organization, as organizations' security requirements differ. However, feel free to message me and I will try to guide you through.

The following requirements are needed to run this playbook:

* 3 CentOS 7.7 Servers
* Set the IP addresses to 192.168.50.107 for Master, 192.168.50.105 for node1 and 192.168.50.106 for node2. You can change the IP address and the login user in the multihosts file.
* Python3

Instructions:
Once you have configured your 3 CentOS servers you can run the following commands to install a base installation of k8s. 

```sh
$ git clone https://github.com/salimwp/k8s-ansible
$ cd k8s-ansible
$ python3 -m venv .
$ source bin/activate
$ pip3 install -r requirements.txt
$ ansible-playbook -i multihosts -k -K k8s.yaml
```
