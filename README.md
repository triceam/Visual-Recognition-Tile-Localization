# ⚠️ This repo has been forked/copied here for archive purposes.  The Visual Recognition service on IBM Cloud is no longer available, and will no longer work as-is. ⚠️ 



# Visual-Recognition-Tile-Localization

The *Visual-Recognition-Tile-Localization* application leverages the Watson Visual Recognition service with image pre-processing techniques to deliver localized image classification.  For example, "show me where there is rust on the bridge".

You can view a demonstration of this application in action in the video here:

[https://youtu.be/wEs1imQmk-Y](https://youtu.be/wEs1imQmk-Y)

[![Video showing sample application](https://img.youtube.com/vi/wEs1imQmk-Y/0.jpg)](https://www.youtube.com/watch?v=wEs1imQmk-Y)

The user drags & drops an image onto the applicaiton within the browser, and the image is uploaded to the Node.js application.  Once uploaded, the image is "chopped up" into smaller images (tiles) and each individual tile is analyzed by the Watson Visual Recognition service.  Once complete, all results are visualized within the browser in a heatmap-like visualization, where colorization is based on the confidence scores being returned by the Visual Recognition service's custom classifier.

### Build status

![Bluemix Deployments](https://deployment-tracker.mybluemix.net/stats/08049cff3cd80ac8b203d9068a36cb53/badge.svg)

### Reference/Docs

* [Node.js on IBM Bluemix](https://console.ng.bluemix.net/catalog/starters/sdk-for-nodejs/)
* [Watson Visual Recognition API Reference](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/)
* [Watson Visual Recognition Custom Classifiers](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#classifiers)
* [Best Practices Creating Custom Classifiers] (https://www.ibm.com/blogs/bluemix/2016/10/watson-visual-recognition-training-best-practices/)


### Run the app locally

1. [Install Node.js][install_node]
2. Download the code
3. Edit `app.js` and add your Watson Visual Recognition Key and Customer Classifier ID
4. cd into the app directory
5. Run `npm install` to install the app's dependencies
6. Run `npm start` to start the app
7. Access the running app in a browser at http://localhost:6001

### Run on IBM Bluemix

The app will also run as-is (with Watson key and classifier id) in the default [Node.js buildpack on Bluemix][node_bluemix].  Once you have modified `app.js` and updated the `WATSON_KEY` and `WATSON_CLASSIFIER` values, then you can deploy using the [Bluemix CLI][bluemix_cli] `push` command. 

### Privacy Notice

The sample web application includes code to track deployments to Bluemix and other Cloud Foundry platforms. The following information is sent to a [Deployment Tracker] [deploy_track_url] service on each deployment:

* Application Name (`application_name`)
* Space ID (`space_id`)
* Application Version (`application_version`)
* Application URIs (`application_uris`)

This data is collected from the `VCAP_APPLICATION` environment variable in IBM Bluemix and other Cloud Foundry platforms. This data is used by IBM to track metrics around deployments of sample applications to IBM Bluemix. Only deployments of sample applications that include code to ping the Deployment Tracker service will be tracked.

### Disabling Deployment Tracking

Deployment tracking can be disabled by removing `require("cf-deployment-tracker-client").track();` from the `app.js` main server file.

[deploy_track_url]: https://github.com/cloudant-labs/deployment-tracker
[install_node]: https://nodejs.org/en/download/
[node_bluemix]: https://console.ng.bluemix.net/catalog/starters/sdk-for-nodejs/
[bluemix_cli]: https://console.ng.bluemix.net/docs/cli/reference/bluemix_cli/index.html
