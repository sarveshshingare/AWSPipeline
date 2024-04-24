# AWSPipeline

## Overview
This project demonstrates how to set up a continuous integration (CI) pipeline using AWS CodeBuild with an EC2 environment running Ubuntu. The pipeline is configured to automatically build and test code stored in a CodeCommit repository whenever changes are pushed.

## Features
- **Automated Builds**: The CI pipeline triggers automatically on code changes, ensuring that code is built and tested consistently.
- **Ubuntu Environment**: The CodeBuild environment runs on Ubuntu, allowing for flexibility in configuring build dependencies and tools.
- **CodeCommit Integration**: The pipeline fetches source code from a CodeCommit repository, providing seamless integration with AWS services.
- **Customizable Build Process**: The build process can be customized using a `buildspec.yml` file, allowing for specific build and test commands to be executed.

## Getting Started
To get started with this project, follow these steps:

1. **Clone the Repository**: Clone this repository to your local machine.
   ```bash
   git clone <repository-url>
2. **Install AWS CLI**: Install the AWS Command Line Interface (CLI) if you haven't already. You'll need it to interact with AWS services.
   ```bash
   # For example, using pip
   pip install awscli --upgrade --user
3. **Configure AWS CLI**: Configure the AWS CLI with your AWS credentials.
   ```bash
   aws configure
4. **Deploy the CloudFormation Stack**: Deploy the provided CloudFormation template to set up the CodeBuild project and associated resources in your AWS account.
   ```bash
   aws cloudformation create-stack --stack-name <stack-name> --template-body file://path/to/cloudformation-template.yaml --parameters ParameterKey=RepoName,ParameterValue=<repo-name> ParameterKey=ProjectName,ParameterValue=<project-name> --capabilities CAPABILITY_NAMED_IAM
5. **Push Code Changes**: Push changes to the CodeCommit repository to trigger the CI pipeline.
   ```bash
   git add .
   git commit -m "Add new feature"
   git push origin master

## Resources
- [AWS CodeBuild Documentation](https://docs.aws.amazon.com/codebuild/)
- [AWS CodeCommit Documentation](https://docs.aws.amazon.com/codecommit/)
- [AWS CloudFormation Documentation](https://docs.aws.amazon.com/cloudformation/)

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
