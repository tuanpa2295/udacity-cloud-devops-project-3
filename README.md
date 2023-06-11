We are archiving this repository because we do not want learners to push personal development to the current repository. If you have any issues or suggestions to make, feel free to:
- Utilize the https://knowledge.udacity.com/ forum to seek help on content-specific issues.
- [Submit a support ticket](https://udacity.zendesk.com/hc/en-us/requests/new) along with the link to your forked repository.
- If you are an enterprise learner, please [Submit a support ticket here](https://udacityenterprise.zendesk.com/hc/en-us/requests/new?ticket_form_id=360000279131)

## Give your Application Auto-Deploy Superpowers

In this project, you will prove your mastery of the following learning objectives:

- Explain the fundamentals and benefits of CI/CD to achieve, build, and deploy automation for cloud-based software products.
- Utilize Deployment Strategies to design and build CI/CD pipelines that support Continuous Delivery processes.
- Utilize a configuration management tool to accomplish deployment to cloud-based servers.
- Surface critical server errors for diagnosis using centralized structured logging.

![Diagram of CI/CD Pipeline we will be building.](udapeople.png)

### Instructions

* [Selling CI/CD](instructions/0-selling-cicd.md)
* [Getting Started](instructions/1-getting-started.md)
* [Deploying Working, Trustworthy Software](instructions/2-deploying-trustworthy-code.md)
* [Configuration Management](instructions/3-configuration-management.md)
* [Turn Errors into Sirens](instructions/4-turn-errors-into-sirens.md)

### Project Submission

For your submission, please submit the following:

- A text file named `urls.txt` including:
  1. Public Url to GitHub repository (not private) [URL01]
  1. Public URL for your S3 Bucket (aka, your green candidate front-end) [URL02]
  1. Public URL for your CloudFront distribution (aka, your blue production front-end) [URL03]
  1. Public URLs to deployed application back-end in EC2 [URL04]
  1. Public URL to your Prometheus Server [URL05]
- Your screenshots in JPG or PNG format, named using the screenshot number listed in the instructions. These screenshots should be included in your code repository in the root folder.
  1. Job failed because of compile errors. [SCREENSHOT01]
  1. Job failed because of unit tests. [SCREENSHOT02]
  1. Job that failed because of vulnerable packages. [SCREENSHOT03]
  1. An alert from one of your failed builds. [SCREENSHOT04]
  1. Appropriate job failure for infrastructure creation. [SCREENSHOT05]
  1. Appropriate job failure for the smoke test job. [SCREENSHOT06]
  1. Successful rollback after a failed smoke test. [SCREENSHOT07]
  1. Successful promotion job. [SCREENSHOT08]
  1. Successful cleanup job. [SCREENSHOT09]
  1. Only deploy on pushed to `master` branch. [SCREENSHOT10]
  1. Provide a screenshot of a graph of your EC2 instance including available memory, available disk space, and CPU usage. [SCREENSHOT11]
  1. Provide a screenshot of an alert that was sent by Prometheus. [SCREENSHOT12]

- Your presentation should be in PDF format named "presentation.pdf" and should be included in your code repository root folder.

Before you submit your project, please check your work against the project rubric. If you haven’t satisfied each criterion in the rubric, then revise your work so that you have met all the requirements.

### Built With

- [Circle CI](www.circleci.com) - Cloud-based CI/CD service
- [Amazon AWS](https://aws.amazon.com/) - Cloud services
- [AWS CLI](https://aws.amazon.com/cli/) - Command-line tool for AWS
- [CloudFormation](https://aws.amazon.com/cloudformation/) - Infrastrcuture as code
- [Ansible](https://www.ansible.com/) - Configuration management tool
- [Prometheus](https://prometheus.io/) - Monitoring tool

## Steps to complete

## Step 1: Integrate Slack
https://github.com/CircleCI-Public/slack-orb/wiki/Setup

* Create a Slack App
* Add permission
* Install and Receive Token
* Create a Context on CircleCI

## Step 2: Create RDS database
* Create RDS Postgres database
* Get host endpoint
* Add inbound rules to security groups to test database creation


## Step 3: Create infrastructure

* Configure AWS CLI on local machine
* Run the command to create init infrastructure
`aws cloudformation deploy \
            --template-file cloudfront.yml \
            --stack-name InitialStack\
            --parameter-overrides WorkflowID=udapeople-pnqpjltbtp`

## Step 4: Setup CircleCI
Add the following environment variables to your Circle CI project by navigating to {project name} > Settings > Environment Variables as shown here:
```
AWS_ACCESS_KEY_ID=(from IAM user with programmatic access)
AWS_SECRET_ACCESS_KEY= (from IAM user with programmatic access)
AWS_DEFAULT_REGION=(your default region in aws)
TYPEORM_CONNECTION=postgres
TYPEORM_MIGRATIONS_DIR=./src/migrations
TYPEORM_ENTITIES=./src/modules/domain/**/*.entity.ts
TYPEORM_MIGRATIONS=./src/migrations/*.ts
TYPEORM_HOST={your postgres database hostname in RDS}
TYPEORM_PORT=5432 (or the port from RDS if it’s different)
TYPEORM_USERNAME={your postgres database username in RDS}
TYPEORM_PASSWORD={your postgres database password in RDS}
TYPEORM_DATABASE=postgres {or your postgres database name in RDS}
```
## Step 5: Project configuration

* Create kvdb for some variables storing
* Add SSH key to CircleCI project configuration (configure server step)

## Configuration for Prometheus Monitoring & Alert System
https://codewizardly.com/prometheus-on-aws-ec2-part1/

## Links & URLs

* [URL01] https://github.com/tuanpa2295/udacity-project-3
* [URL02] http://udapeople-9b4fb0c.s3-website-us-east-1.amazonaws.com
* [URL02 - cloudfront] http://d1dpsk237ddyly.cloudfront.net/#/employees

## Presentation file
