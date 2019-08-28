# Docker Logging Plugin Tee

A docker logging plugin that send logs to multiple log drivers.

## Plugin build

```

make all


```


## Deploy

```

docker plugin install sunnywalden/logging-plugin-tee:latest --alias tee

```


## Example

```
> docker run --rm --log-driver tee:latest \
	--log-opt tee-drivers=json-file,syslog \
    --log-opt syslog:syslog-address=tcp://172.17.0.1:1514 \
    --log-opt syslog:syslog-format=rfc5424 \
    ubuntu:bionic sh -c 'while :; do date; sleep 2; done'
```

## License

MIT
