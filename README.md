# openshift
Scripts and Hints, How to configure and install on centos

https://youtu.be/wWSRpaosc-M?t=377


https://www.youtube.com/watch?v=ZkFIozGY0IA

## How to start

yum update

nano /etc/hosts
sudo yum install git

git clone https://github.com/gshipley/installcentos.git

cd installcentos
./install-openshift.sh


## Check
  
  oc version


# Install on fedora

https://developer.fedoraproject.org/deployment/openshift/about.html


FEDORA
## Install
sudo dnf install origin-clients docker

## Start
oc cluster up

## check
docker version

## Change config for insecure registyr

nano /etc/containers/registries.conf 
and add 172.30.0.0/16 to the list of registries under [registries.insecure] category. For example:

[registries.insecure]
registries = ['172.30.0.0/16']

## Restart
sudo systemctl restart docker
oc cluster up


oc new-app https://github.com/openshift/ruby-hello-world
