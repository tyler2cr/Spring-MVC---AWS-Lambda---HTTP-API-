
This project was initially cloned from  
[awslabs/aws-serverless-java-container "Serverless Spring Boot 2 example"](https://github.com/awslabs/aws-serverless-java-container/blob/6d88f503c02988cc947743bad78d965d8aa0b5a2/samples/springboot2/pet-store/README.md)

# Serverless Spring Boot 2 example
A basic pet store written with the [Spring Boot 2 framework](https://projects.spring.io/spring-boot/). The `StreamLambdaHandler` object is the main entry point for Lambda.

The application can be deployed in an AWS account using the [Serverless Application Model](https://github.com/awslabs/serverless-application-model). The `template.yml` file in the root folder contains the application definition.

## Pre-requisites
* [AWS CLI](https://aws.amazon.com/cli/)
* [SAM CLI](https://github.com/awslabs/aws-sam-cli)
* [Gradle](https://gradle.org/) or [Maven](https://maven.apache.org/)

## Deployment
In a shell, navigate to the sample's folder and use the SAM CLI to build a deployable package
```
$ sam build
```

This command compiles the application and prepares a deployment package in the `.aws-sam` sub-directory.

To deploy the application in your AWS account, you can use the SAM CLI's guided deployment process and follow the instructions on the screen

```
$ sam deploy --guided
```

Once the deployment is completed, the SAM CLI will print out the stack's outputs, including the new application URL. You can use `curl` or a web browser to make a call to the URL

```
...
---------------------------------------------------------------------------------------------------------
OutputKey-Description                        OutputValue
---------------------------------------------------------------------------------------------------------
PetStoreApi - URL for application            https://xxxxxxxxxx.execute-api.us-west-2.amazonaws.com/pets
---------------------------------------------------------------------------------------------------------

$ curl https://xxxxxxxxxx.execute-api.us-west-2.amazonaws.com/pets
```

---

# Cold starts
- [AWS Blog on optimizing cold starts (language-agnostic)](https://aws.amazon.com/blogs/compute/operating-lambda-performance-optimization-part-1/)
- [Spring-specific optimization for cold start times](https://github.com/awslabs/aws-serverless-java-container/wiki/Quick-start---Spring-Boot2#optimizing-cold-start-times)


# See also

[Wiki - aws-serverless-java-container](https://github.com/awslabs/aws-serverless-java-container/wiki)

[Quick-start---Spring-Boot2](https://github.com/awslabs/aws-serverless-java-container/wiki/Quick-start---Spring-Boot2)
- [Optimizing cold start times](https://github.com/awslabs/aws-serverless-java-container/wiki/Quick-start---Spring-Boot2#optimizing-cold-start-times)



