## Nginx Helm Chart Example

1. A helm chart which deploys NGINX in HA mode (3 instances) and supports either HTTP or HTTPS based traffic.
2. Can have multiple upstream servers configured through configuration in values.yaml:

```
## Add more upstream services into the config block
serverBlockHTTPS:
  default.conf:
...
```

3. Control HTTP/HTTPS based on config block:
```
## NGINX Service properties
service:
  ## Service type
  type: LoadBalancer
  ## Service Port
  port: 8080
  tls:
    ## Controls if SSL is enabled or not
    enabled: true
    hostname: example.local
 ```
 
 4. Generates self-signed CA and leaf certificates for NGINX in case of HTTPS based configuration is enabled.
