## Deploy a ExpressJS project in GKE with Artifact registrory google 

# 1.Create a simple app with nodejs express

Create a express folder 

cd express

npm init -y
npm i express

create app.js

node app.js

check the browser : localhost:3000

Create a dockerfile 
and .dockerignore

enable artifact registry API
create a artifact repository 

docker buildx build -t LOCATION-docker.pkg.dev/PROJECT-ID/REPOSITORY/IMAGE:tag .


authenticate with artifactory:
   
   gcloud auth configure-docker eu-west1-docker.pkg.dev

   docker push LOCATION-docker.pkg.dev/PROJECT-ID/REPOSITORY/IMAGE:TAG

   docker run -d -p 3000:80 LOCATION-docker.pkg.dev/<PROJECT_ID>/imagename:tag

# 2.Create a simple cluster in gcp console

# 3. Write the kubernetes manifest file 

connect to the cluster 
and then run

cd kubernetes

kubctl apply -f deployment.yaml
kubectl apply -f service.yaml

kubectl get deploy
kubectl get svc
