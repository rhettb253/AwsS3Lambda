# AWS: S3 and Lambda

AWS Lambda allows us to write code that is triggered in the cloud, without thinking about maintaining servers. This is practice integrating a Lambda Function.

## Before You Start

Make sure your IAM User has permissions 'AmazonS3FullAccess' & 'AWSLambda_FullAccess'.

## S3

- console -> S3 -> create bucket
- add a name, then click create bucket
- set up permissions with a permissions policy
- <img src='./s3AdmissionsConfig.png' />
- Here's a breakdown of what this policy is saying:
  - Version: This specifies the version of the policy language. In this case, it's using version "2012-10-17," which is a common version.
  - Statement: This is an array of policy statements. In your example, there's only one statement.
    - Sid: This is just a unique identifier for the statement. It doesn't affect the policy's functionality but can be useful for reference.
    - Principal: "*" means that this policy applies to any AWS principal. In other words, it grants permissions to any AWS account or user.
    - Effect: "Allow" means that the actions specified in this statement are allowed.
    - Resource: "arn:aws:s3:::awspracticebucketforthewin/*" is the Amazon Resource Name (ARN) of the resource to which this policy applies. In this case, it's an S3 bucket named "awspracticebucketforthewin" and all objects within that bucket (indicated by /*).
    - Action: This is an array of actions that are allowed. The policy allows two actions:
      - "s3:GetObject": This action allows any AWS principal to retrieve (read) objects from the specified bucket.
      - "s3:PutObject": This action allows any AWS principal to upload (write) objects to the specified bucket.
     
## Lambda

- console -> Lambda -> create function
- add a name, runtime: node.js 16, then click create function
  - const AWS = require('aws-sdk');
  - const S3 = new AWS.S3();
- what our class code looked like:
- <img src='./workingCode1.png' />
- <img src='./workingCode2.png' />
