# Google Maps - Store Location Demo

This is a simple demo of using the Google Maps APIs to create a store locator. This demo has been created to location Service Ontraio locations based upon a GeoJson file of 6 locations of Service Ontario in Ottawa. These location were found using Google Maps search and the details of each location are made up for demo purposes only.

## Google Maps APIs

The following Google Maps APIs are being used in this demo
- Places API
- Maps JavaScript API
- Distance Matrix API
- Street View Static API

## Update the demo code

Once you have created your Google Maps API inside the Google Maps Platform Credentials section (make sure to secure your API with Application restrictions and API Restrictions). You will need to update:

- index.html - Update the script include line and replace `YOUR_KEY_HERE` on line 104 with your API key
- maps.js - Update the apiKey constant on line 22 with your API key

## Deploy to Cloud Run

1. Build the container using the docker build command:
  - e.g. docker build . -t us-central1-docker.pkg.dev/PROJECT-ID/REPO-NAME/maps-demo
  - This will build the container locally and tag it with a Google Cloud Artifact Registry repo that you have already created

2. Push the container to the repository.
  - e.g. docker push us-central1-docker.pkg.dev/PROJECT-ID/REPO-NAME/maps-demo

3. Deploy to Cloud Run
  - e.g. gcloud run deploy maps-demo --image us-central1-docker.pkg.dev/PROJECT-ID/REPO-NAME/maps-demo --platform=managed --allow-unauthenticated


The deployment assumes you have a Google Cloud project setup with the Artifcat Registry and Cloud Run APIs enabled.