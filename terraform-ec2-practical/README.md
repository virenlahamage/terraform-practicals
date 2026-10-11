# Practical 01: Create an AWS EC2 Instance Using Terraform

## Objective

Create an AWS EC2 instance using Terraform to understand Infrastructure as Code and the Terraform resource lifecycle.

## Prerequisites

- Terraform CLI installed
- AWS CLI configured
- Appropriate AWS IAM permissions
- AWS region: `ap-south-1`

## Files

- `main.tf` — Terraform configuration for the AWS provider, Ubuntu AMI lookup, EC2 instance, tags, and outputs.

## Steps

### 1. Initialize Terraform

```bash
terraform init
```

Downloads the required provider and initializes the working directory.

### 2. Format the configuration

```bash
terraform fmt
```

Formats Terraform files consistently.

### 3. Validate the configuration

```bash
terraform validate
```

Checks the Terraform configuration for syntax and structural errors.

### 4. Review the execution plan

```bash
terraform plan
```

Previews the proposed infrastructure changes without creating the instance.

### 5. Create the EC2 instance

```bash
terraform apply
```

Review the plan and type `yes` when prompted.

### 6. Verify the resource

```bash
terraform state list
terraform state show aws_instance.my_ec2
```

Check the instance state in the AWS Management Console as well.

### 7. Clean up

```bash
terraform destroy
```

Review the deletion plan and confirm when you are ready to remove the instance.

## Expected Outcome

An EC2 instance is provisioned using Terraform, its details are exposed through outputs, and the resource can be tracked and destroyed using Terraform.
<img width="1908" height="1115" alt="Screenshot 2026-10-11 191844" src="https://github.com/user-attachments/assets/a30c5acb-4f63-4d8e-a169-3db04ed9ace8" />
<img width="1842" height="1087" alt="Screenshot 2026-10-11 192309" src="https://github.com/user-attachments/assets/c18ad77f-b66f-4b5e-953e-7bc06ad8a210" />
<img width="1830" height="1107" alt="Screenshot 2026-10-11 192339" src="https://github.com/user-attachments/assets/31ff9cbf-f5df-47aa-9112-0c156405a605" />



## Key Learnings

- Provider configuration
- AMI data sources
- EC2 resource provisioning
- Terraform plan and apply
- Outputs and state
- Infrastructure cleanup

## Important Notes

- The instance type and availability depend on the AWS region, quotas, and account eligibility.
- This configuration does not create SSH access rules.
- AWS charges may apply.
- Never commit Terraform state files or AWS credentials.
