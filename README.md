# Lambda-Instance-Count
Function: AWS Lambda function to count Orphaned IP's and EC2 instances


## Lambda-Instance-Count
## =================

A utility AWS lambda function to count Orphaned IP's and EC2 instances and pushes the metrics to Cloudwatch.

The Lambda function takes new backups when executed, and manages the deletion of the old ones when the upper limit is reached.

### Dependencies

The tool uses the supplied `boto3` library to connect to the AWS account.
```
    ec2 = boto3.resource('ec2')
    cloudwatch = boto3.client('cloudwatch')
```
The role requires.......

### Lambda Deployment

Create a Lambda function.
Runtime - Python 2.7
Handler - lambda_function.lambda_handler

### Configuring the lambda Function

The configuration of the lambda is simple

Things you might want to review and change are:

* The "running instance metric name" - running_instances_metric_name = 'NumberRunningInstances'
* The "orphaned EIP's metric name" - orphan_eips_metric_name = 'NumberOrphanElasticIps'
* The metric namespace - metric_namespace = 'EC2'
