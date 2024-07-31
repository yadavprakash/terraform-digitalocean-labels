# Terraform-digitalocean-labels

# Terraform DigitalOcean cloud Labels Module

## Table of Contents

- [Introduction](#introduction)
- [Usage](#usage)
- [EXAMPLES](#examples)
- [License](#license)
- [Author](#author)
- [Inputs](#inputs)
- [Outputs](#outputs)


## Introduction
This Terraform module creates labels for resources on DigitalOcean. Labels provide metadata and organization for resources to help you manage and identify them more effectively.

## Usage

To use this module, you can include it in your Terraform configuration. Here's an example of how to do that:
This configuration includes a custom "labels" module for managing resource labels. The module is used as follows:
# Example: labels

```hcl
module "labels" {
  source      = "git::https://github.com/yadavprakash/terraform-digitalocean-labels.git"
  name        = "app"
  environment = "test"
  label_order = ["name", "environment"]
  attributes  = ["private"]
  extra_tags = {
    Application = "Demo"
  }
}
```

Make sure to replace "your_module_source" with the actual source URL or path to your module.


## Examples
For detailed examples on how to use this module, please refer to the [Examples](https://github.com/yadavprakash/terraform-digitalocean-labels/tree/master/_examples) directory within this repository.

## Author
Your Name Replace **MIT** and **yadavprakash** with the appropriate license and your information. Feel free to expand this README with additional details or usage instructions as needed for your specific use case.

## License
This project is licensed under the **MIT** License - see the [LICENSE](https://github.com/yadavprakash/terraform-digitalocean-labels/blob/master/LICENSE) file for details.
<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.6.6 |
| <a name="requirement_digitalocean"></a> [digitalocean](#requirement\_digitalocean) | >= 2.34.1 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_digitalocean"></a> [digitalocean](#provider\_digitalocean) | >= 2.34.1 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [digitalocean_tag.environment](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/tag) | resource |
| [digitalocean_tag.id](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/tag) | resource |
| [digitalocean_tag.managedby](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/tag) | resource |
| [digitalocean_tag.name](https://registry.terraform.io/providers/digitalocean/digitalocean/latest/docs/resources/tag) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_attributes"></a> [attributes](#input\_attributes) | Additional attributes (e.g. `1`). | `list(any)` | `[]` | no |
| <a name="input_delimiter"></a> [delimiter](#input\_delimiter) | Delimiter to be used between `organization`, `name`, `environment` and `attributes`. | `string` | `"-"` | no |
| <a name="input_enabled"></a> [enabled](#input\_enabled) | Set to false to prevent the module from creating any resources. | `bool` | `true` | no |
| <a name="input_environment"></a> [environment](#input\_environment) | Environment (e.g. `prod`, `dev`, `staging`). | `string` | `""` | no |
| <a name="input_label_order"></a> [label\_order](#input\_label\_order) | Label order, e.g. `name`,`application`. | `list(any)` | <pre>[<br>  "name",<br>  "environment"<br>]</pre> | no |
| <a name="input_managedby"></a> [managedby](#input\_managedby) | ManagedBy, eg 'terraform-do-modules' or 'yadavprakash.com' | `string` | `"yadavprakash"` | no |
| <a name="input_name"></a> [name](#input\_name) | Name  (e.g. `app` or `cluster`). | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_environment"></a> [environment](#output\_environment) | Normalized environment. |
| <a name="output_id"></a> [id](#output\_id) | Disambiguated ID. |
| <a name="output_managedby"></a> [managedby](#output\_managedby) | 'managedby' ,'yadavprakash' |
| <a name="output_name"></a> [name](#output\_name) | Normalized name. |
<!-- END_TF_DOCS -->
