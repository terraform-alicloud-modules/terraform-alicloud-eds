Terraform Module for creating Elastic Desktop Service on Alibaba Cloud.

terraform-alicloud-eds
=====================================================================

English | [简体中文](README-CN.md)

This module is used to create a Elastic Desktop Service under Alibaba Cloud.

These types of resources are supported:

* [alicloud_ecd_desktop](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_desktop)
* [alicloud_ecd_image](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_image)
* [alicloud_ecd_nas_file_system](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_nas_file_system)
* [alicloud_ecd_network_package](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_network_package)
* [alicloud_ecd_policy_group](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_policy_group)
* [alicloud_ecd_simple_office_site](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_simple_office_site)
* [alicloud_ecd_user](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs/resources/ecd_user)

## Usage

```hcl
module "default" {
  source                      = "terraform-alicloud-modules/eds/alicloud"
  bundle_id                   = "bundle_1234567xxx"
  #alicloud_ecd_simple_office_site
  create_office_site          = true
  office_site_name            = "tf-name"
  cidr_block                  = "172.16.0.0/12"
  desktop_access_type         = "Internet"
  #alicloud_ecd_policy_group
  create_policy_group         = true
  policy_group_name           = "tf-name"
  #alicloud_ecd_user
  create_user                 = true
  end_user_id                 = "tf-user-test"
  user_email                  = "hello123456.abc@abc.com"
  user_phone                  = "15800000011"
  #alicloud_ecd_desktop
  create_desktop              = true
  desktop_name                = "tf-name"
  #alicloud_ecd_network_package
  create_network_package      = true
  bandwidth                   = "10"
  #alicloud_ecd_nas_file_system
  create_nas_file_system      = true
  nas_file_system_name        = "tf_nas_file_system_name"
  create_image                = true
  image_name                  = "tf-name"
}
```

## Examples

* [complete example](https://github.com/terraform-alicloud-modules/terraform-alicloud-eds/tree/main/examples/complete)

## Notes

* This module using AccessKey and SecretKey are from `profile` and `shared_credentials_file`. If you have not set them
  yet, please install [aliyun-cli](https://github.com/aliyun/aliyun-cli#installation) and configure it.

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | > = 0.13.0 |
| <a name="requirement_alicloud"></a> [alicloud](#requirement\_alicloud) | > = 1.146.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_alicloud"></a> [alicloud](#provider\_alicloud) | > = 1.146.0 |

## Submit Issues

If you have any problems when using this module, please opening
a [provider issue](https://github.com/aliyun/terraform-provider-alicloud/issues/new) and let us know.

**Note:** There does not recommend opening an issue on this repo.

## Authors

Created and maintained by Alibaba Cloud Terraform Team(terraform@alibabacloud.com).

## License

MIT Licensed. See LICENSE for full details.

## Reference

* [Terraform-Provider-Alicloud Github](https://github.com/aliyun/terraform-provider-alicloud)
* [Terraform-Provider-Alicloud Release](https://releases.hashicorp.com/terraform-provider-alicloud/)
* [Terraform-Provider-Alicloud Docs](https://registry.terraform.io/providers/aliyun/alicloud/latest/docs)
