
# Terraform S3 Automation

## Project Overview

This project demonstrates how to automate AWS S3 bucket creation using Terraform.

It uses a reusable Terraform module to create and configure a secure S3 bucket with public access protection, server-side encryption, and versioning.

## Architecture

```text
       Terraform Configuration
                 |
                 v
            Root Module
                 |
                 v
            S3 Module
                 |
                 v
             AWS Provider
                 |
                 v
             AWS S3 Bucket
                 |
       +---------+----------+
       |         |          |
       v         v          v
    Public    Encryption  Versioning
    Access      AES256     Enabled
    Block
```

## AWS Resources Created

| Resource | Purpose |
|---|---|
| S3 Bucket | Stores objects and files |
| Public Access Block | Prevents public access |
| Encryption | Protects data using AES256 |
| Versioning | Maintains object versions |

## Project Structure

```text
terraform-s3-automation/
|
|-- modules/
|   |-- s3/
|       |-- main.tf
|       |-- variables.tf
|       |-- outputs.tf
|
|-- main.tf
|-- providers.tf
|-- variables.tf
|-- outputs.tf
|-- terraform.tfvars.example
|-- .gitignore
|-- .terraform.lock.hcl
|-- README.md
```

## Technologies Used

- Terraform
- AWS S3
- AWS Provider
- Git
- GitHub

## Prerequisites

Before running this project, install:

- Terraform
- AWS CLI
- Git
- AWS account with required S3 permissions

Configure AWS CLI:

```bash
aws configure
```

## Terraform Workflow

### 1. Initialize Terraform

```bash
terraform init
```

### 2. Format Terraform files

```bash
terraform fmt -recursive
```

### 3. Validate configuration

```bash
terraform validate
```

### 4. Preview infrastructure changes

```bash
terraform plan
```

### 5. Create AWS resources

```bash
terraform apply
```

Review the plan and confirm before applying.

## Configuration

Create a local `terraform.tfvars` file:

```hcl
bucket_name = "your-unique-s3-bucket-name"
```

S3 bucket names must be globally unique.

The actual `terraform.tfvars` file is excluded from Git using `.gitignore`.

## Security Features

- Blocks public access to the S3 bucket.
- Enables AES256 server-side encryption.
- Enables S3 bucket versioning.
- Uses Terraform variables for configuration.
- Uses a reusable child module.

## Terraform Module Benefits

The S3 module separates resource configuration from the root module.

This improves:

- Code reusability
- Maintainability
- Project organization
- Scalability

## Cleanup

After confirming that no required data remains and obtaining AWS account owner's approval, run:

```bash
terraform destroy
```

This removes the Terraform-managed AWS resources.

## Author

**Siddiq Shaik**

GitHub: [shaik-siddiq13](https://github.com/shaik-siddiq13)
