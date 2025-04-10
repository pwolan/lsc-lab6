# lsc-lab6
Large Scale Computing

# NFS Server setup
helm repo add stable https://charts.helm.sh/stable
helm repo update
helm install nfs-server stable/nfs-server-provisioner --set storageClass.name=nfs-client-provisioner

# create PVC
kubectl apply -f pvc.yaml

# create deployment
kubectl apply -f deployment.yaml

# create load balancer
kubectl apply -f service.yaml

# create job
kubectl apply -f job.yaml

# get address of site - EXTERNAL-IP
kubectl get svc web-server-service 