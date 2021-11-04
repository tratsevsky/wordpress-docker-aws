# wordpress-docker-aws
Deploy wordpress container in AWS

TESTED ENVIRONMENT
- Windows 10
- Docker Desktop 4.1.1 (69879) (docker version 20.10.8, build 3967b7d)
  
PREREQUISITES
- AWS credentials are present in $HOME directory
- IAM account must have admin privileges

SETUP - Create a new docker context for working with AWS, set is as default
- docker context create ecs myecscontext
- Create a Docker context using: An existing AWS profile
- Select AWS Profile default
- Successfully created ecs context "myecscontext"

SETUP - Run
1. Create a new folder, clone the provided yaml file
2. Go to folder, run "docker compose up"

SETUP - Get a public DNS name to proceed with Wordpress configuration
- docker context ps

RESULT
Docker converts the provided YAML file into AWS CloudFormation template and deploys the infrastructure with ECS in Fargate mode.


FAQ
1. If get a 503 error immediately after stack created, just wait for 1-2 minutes and refresh the page. The reason for such behavior is incomplete DB setup task. It remains in "IN PROGRESS" state after main CF template is finished.
