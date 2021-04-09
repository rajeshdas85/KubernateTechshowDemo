# KubernateTechshowDemo
Follow the links->https://github.com/kubernetes/dashboard

# Create simple user  the dashboard
cluster-admin.yml ->  kubectl create -f .\cluster-admin.yml

# Creating a Service Account
service-account.yml-> kubectl create -f .\ServiceAccount.yml

# Configure the dashboard
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.2.0/aio/deploy/recommended.yaml
kubectl proxy

# Getting a Bearer Token
kubectl -n kubernetes-dashboard get secret $(kubectl -n kubernetes-dashboard get sa/admin-user -o jsonpath="{.secrets[0].name}") -o go-template="{{.data.token | base64decode}}"

# Create build Image 
docker build -t  rajeshdas17062019/kubernatetechshowdemo:V1.0.0.0 .

# Create run  container  
docker run -p 5000:80 rajeshdas17062019/kubernatetechshowdemo:V1.0.0.0

# Test the container 
http://localhost:5000/

# Push docker image to my docker hub repository
docker push rajeshdas17062019/kubernatetechshowdemo:V1.0.0.0

Note: check the image https://hub.docker.com/repository/docker/rajeshdas17062019/kubernatetechshowdemo

#create deployment file for kubernate

#create service file for kubernate












