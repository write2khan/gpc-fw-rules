
A feature to implement FW rules for a given vpc in a given project.

## Requirements

Please note that state file for npe project has been synchronized as well as the input for this feature

## Providers

No provider.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| firewall\_rules | VPC firewall rules inputs | <pre>list(object({<br>    name                    = string<br>    description             = string<br>    direction               = string<br>    priority                = number<br>    ranges                  = list(string)<br>    source_tags             = list(string)<br>    source_service_accounts = list(string)<br>    target_tags             = list(string)<br>    target_service_accounts = list(string)<br>    allow = list(object({<br>      protocol = string<br>      ports    = list(string)<br>    }))<br>    deny = list(object({<br>      protocol = string<br>      ports    = list(string)<br>    }))<br>    log_config = object({<br>      metadata = string<br>    })<br>  }))</pre> | n/a | yes |
| project\_id | Project id that has the target vpc | `string` | n/a | yes |
| vpc\_name | Target vpc where the fw rules will be applied | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| firewall\_rules | The created firewall rule resources |

