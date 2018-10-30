[![Build Status](https://travis-ci.org/IBM/watson-second-opinion.svg?branch=master)](https://travis-ci.org/IBM/watson-second-opinion)

# Create a Review Analyzer with Watson Natural Language Understanding
This is the code pattern for https://2ndopinion.mybluemix.net/.

![demo](https://i.makeagif.com/media/6-07-2018/IeEcIv.gif)

In this Code Pattern, we will create a Node.js app that takes the reviews from an online shopping website, Amazon, and feeds them into the Watson Natural Language Understanding service. The reviews will be stored in a Cloudant database. The Watson Natural Language Understanding service will show the overall sentiments of the reviews. The sample application will do all the reading of reviews for you and will give an overall insight about them. The Code Pattern can be useful to developers that are looking into processing multiple documents with Watson Natural Language Understanding.

When the reader has completed this Code Pattern, they will understand how to:

* Interact with Watson Natural Language Understanding using Watson's Node SDK
* Build a user interface around the result of Watson Natural Language Understanding
* Create and use Cloudant NoSQL Database
* Deploy a Nodejs application to analyze product reviews

<!--Remember to dump an image in this path-->
![Architecture](/docs/app-architecture.png)

## Flow
1. The user deploys the app in IBM Cloud. The user interacts with the user interface of the app.
2. The user enters the product URL and the app would start getting the reviews of the Product.
3. The app then stores the reviews in a database for later use.
4. The app starts to upload the reviews in Watson Natural Language Understanding.
5. After Watson Natural Language Understanding finishes processing the reviews, the app then stores the result (General Sentiment and Top Entities) in Cloudant. The user will see the result in the UI.

## Included components
* [Watson Natural Language Understanding](https://www.ibm.com/watson/services/natural-language-understanding/):  Analyze text to extract meta-data from content such as overall sentiment, emotion, concepts, entities, keywords, categories, relations and semantic roles.
* [Cloudant NoSQL DB](https://console.ng.bluemix.net/catalog/services/cloudant-nosql-db): A fully managed data layer designed for modern web and mobile applications that leverages a flexible JSON schema.

## Featured technologies
* [Node.js](https://nodejs.org/): An open-source JavaScript run-time environment for executing server-side JavaScript code.
* [Databases](https://en.wikipedia.org/wiki/IBM_Information_Management_System#.22Full_Function.22_databases): Repository for storing and managing collections of data.
* [Cloud](https://www.ibm.com/developerworks/learn/cloud/): Accessing computer and information technology resources through the Internet.

## Requirements
- [IBM Cloud Account](https://ibm.biz/BdYpAv)
- [Node.js](https://nodejs.org/en/download/)


# Steps

### 1. Create IBM Cloud services

From IBM Cloud catalog, create the following services:

* [**Watson Natural Language Understanding**](https://console.bluemix.net/catalog/services/natural-language-understanding)
* [**Cloudant NoSQL DB**](https://console.ng.bluemix.net/catalog/services/cloudant-nosql-db/)

### 2. Get Service Credentials

Once the service is created, click on it, and then click on `Service credentials` in the top left corner of the screen. Then click `New credential` and then `add`. For `Cloudant NoSQL DB`, save the value for `url`. For `Natural Language Understanding` save the value for `username` and `password`.

### 3. Clone the repo

```
$ git clone https://github.com/xnorax/watson-second-opinion.git
$ cd watson-second-opinion/
```
### 4. Set Envioronment Variables

From your cloned repo folder, go to *.env* file to paste your credentials.  

```
CLOUDANT_URL=
NLU_USERNAME=
NLU_PASSWORD=
```

### 5. Install Dependencies

```
$ npm install
```

### 6. Run the App

Run the app by starting Node.

```
$ node app.js
```

Go to `http://localhost:4000/` in your browser of choice, and you should be greeted with the Watson Second Opinion UI.

Find a product in Amazon that you want to learn more about, copy the URL of the product page, paste it into the app, and click 🔍. After Watson Natural Language Understanding finishes processing all the reviews, the app will show you its General Sentiment and Top entities found:


![Landing Page](docs/analysis.png)

Great job! You've successfully run Watson Second Opinion on your local machine! Thanks for taking the time to walk through the app with me. I am welcoming all pull requests, and any updates to the project. Have fun with it!

# Learn more

* **Node.js Code Patterns**: Enjoyed this Code Pattern? Check out our other [Node.js Code Patterns](https://developer.ibm.com/code/technologies/node-js/)
* **Artificial Intelligence Code Patterns**: Enjoyed this Code Pattern? Check out our other [AI Code Patterns](https://developer.ibm.com/code/technologies/artificial-intelligence/).
* **AI and Data Code Pattern Playlist**: Bookmark our [playlist](https://www.youtube.com/playlist?list=PLzUbsvIyrNfknNewObx5N7uGZ5FKH0Fde) with all of our Code Pattern videos
* **With Watson**: Want to take your Watson app to the next level? Looking to utilize Watson Brand assets? [Join the With Watson program](https://www.ibm.com/watson/with-watson/) to leverage exclusive brand, marketing, and tech resources to amplify and accelerate your Watson embedded commercial solution.

# License
[Apache 2.0](LICENSE)
