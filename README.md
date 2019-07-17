# Simple JAVA Application

## Team members:
- Xia Liu
- Sudip Adhikari
- Timothy Bush

## Deployed Link:
- http://deploymentappjava-env.pbyqhfkccg.us-east-1.elasticbeanstalk.com/

## Steps on cretaing deployment environment:

### Elastic beanstalk
- Open the AWS Elastic beanstalk console.
- Select get started or Create new Application.
- Give your app a name, choose region, select platform (JAVA), select sample application and click create.

### Your app on intellij:
- Update your gitignore
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/gitignore.png) 
- Create a Procfile (text file) with following line of code: web: java -jar build/libs/application.jar
- Add following line of code to your build.gradle: bootJar { archiveFileName = 'application.jar' }

### Code pipeline
- On your AWS CodePipeline console click create pipeline.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenOne.png) 
- Choose a pipeline name, select new service role and click next.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenTwo.png)
- Choose source provider (gitHub) and connect to gitHub by providing your credentials.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenThree.png)
- Choose the repository and the branch (master) that you want to deploy.
- Select use GitHub webhooks and click next.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenFour.png)
- Select skip build stage and click next.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenFive.png)
- Choose deploy provider (Elastic Beanstalk), and choose the region, application name, and environment name(should auto-populate), and click next.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenSix.png)
- Click create pipeline.

## Creating test stage
- On your pipeline, click edit on top left corner.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/editPipeline.png)
- Click on Add stage
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/addStage.png)
- Give your stage a name
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/stageName.png)
- Click Add Action Group
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/addActionGroup.png)
- Specify action name and provider(AWS codeBuild).
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/provideActionDetails.png)
- Select default for input artifact, select project name from codeBuild (Steps mentioned below), and click done.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-java/master/assets/varifytest.png)


## Creating project in codeBuild
- On codebuild console, create project.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenSix.png)
- Give your project a name
- Select no source for source provider
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenSix.png)
- Select your operating system, select new service role, and accept all default selections, and create build project.
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/ScreenSix.png)



- To see auto-update, edit the index.php file and merge the commit to master. You should see the updates on your deployed website.

## Screenshots of pipeline updating after change in the master of the repo and once update is complete: 

![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/screen15.png)
![Screen Screen](https://raw.githubusercontent.com/sadhikari07/deployment-app-php/master/assets/screen16.png)


-Additional Screens located in assets. 
  
  
 ## Reference: 
 https://aws.amazon.com/getting-started/tutorials/continuous-deployment-pipeline/
