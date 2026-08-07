## Usage
### Please copy paste below code

```
module demo {
    source         = "ryanahkiong/gke/gcp"
    gke_config = {
      cluster_name   = "project-cluster"
      location       = "us-west1"
      node_count     = 1
      min_node_count = 1
      max_node_count = 2
      machine_type   = "e2-medium"
      disk_size_gb   = 100
      disk_type      = "pd-balanced"
  }
}

```
### Run

```
terraform init
terraform apply
```

## Outputs

| Name | Description |
|------|-------------|
| `cluster_name` | The name of the GKE cluster. |
| `cluster_location` | The location of the GKE cluster. |

<br><br>

#### You can expose the module outputs from a root configuration like this:

### Output examples

```
output "gke_cluster_name" {
  value = module.demo.cluster_name
}

output "gke_cluster_location" {
  value = module.demo.cluster_location
}
```

### Push Test