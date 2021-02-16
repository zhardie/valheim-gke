# Valheim Server on Google Kubernetes Engine

## Setup

1. Download and install gcloud and kubectl
2. `gcloud auth login`
3. `gcloud config set project yourproject`
4. `gcloud config set compute/zone us-central1-c`
5. `gcloud container clusters create valheim-cluster --num-nodes=1 --machine-type=e2-medium`
6. `gcloud compute disks create --size 20GB valheim-disk --zone us-central1-c`
7. `gcloud container clusters get-credentials valheim-cluster --zone us-central1-c`
8. edit `valheim-server.yaml` with your own `SERVER_NAME`, `WORLD_NAME` and `SERVER_PASS`
9. `kubectl apply -f valheim-server.yaml`
10. `kubectl apply -f valheim-service.yaml`
