# terraform-s3-cf-website
Terraform module to create S3 static website, along with CloudFormation distribution for it to enable serving through SSL

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| host |  Host for the website | string | `""` | yes |
| certificate\_arn | Certificate ARN from AWS Certificate Manager | string | `""` | yes |

## Outputs

| Name | Description |
|------|-------------|
| cf\_domain\_name | CloudFront Domain name (for use in DNS) |

## Examples

```hcl
module "my-website" {
  providers = {
    aws = aws.production
  }
  source ="git@github.com:SequoiaConsulting/terraform-s3-cf-website.git?ref=v1.0"
  host  = "thenextbigthingto.com"
  certificate_arn = "arn:aws:acm:us-east-1:111111111111:certificate/59b6cdef-5911-09e8-3i9d-ck0370p3e812"
}
```
