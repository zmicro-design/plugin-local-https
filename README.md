# HTTPS for local development

## How to

```bash
# 1. generate ssl certificate for localhost
$ zmicro local-https generate

# 2. use ssl private key and certificate
# ssl key:          /opt/data/plugins/local-https/certs/localhost/localhost.key
# ssl certificate:  /opt/data/plugins/local-https/certs/localhost/localhost.crt

# 3. start server (using node.js serve => npm i -g serve)
$ serve -l 443 \
  --ssl-key /opt/data/plugins/local-https/certs/localhost/localhost.key \
  --ssl-cert /opt/data/plugins/local-https/certs/localhost/localhost.crt

# 4. visit browser => https://localhost
$ curl https://localhost
```

## Advance
* `Custom Domain`, such as: local.dev

```bash
# 1. generate ssl certificate for localhost
$ zmicro local-https generate local.dev

# 2. use ssl private key and certificate
# ssl key:          /opt/data/plugins/local-https/certs/local.dev/local.dev.key
# ssl certificate:  /opt/data/plugins/local-https/certs/local.dev/local.dev.crt

# 3. /etc/hosts add follow
127.0.0.1 local.dev

# 3. start server (using node.js serve => npm i -g serve)
$ serve -l 443 \
  --ssl-key /opt/data/plugins/local-https/certs/local.dev/local.dev.key \
  --ssl-cert /opt/data/plugins/local-https/certs/local.dev/local.dev.crt

# 4. visit browser => https://local.dev
$ curl https://local.dev
```

# FAQ
* Which platform support ?
  * Now, only `MacOS`

## Inspired by
* [kingkool68/generate-ssl-certs-for-local-development](https://github.com/kingkool68/generate-ssl-certs-for-local-development)