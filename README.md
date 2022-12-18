# json-conf

## Install

1. Clone repo.
2. Install jq from your distro.

## Usage

```sh
jsonFile=<path to json file> jsonPath="jq style path w/o first ." json-conf
```

## Examples

`/usr/local/etc/backup-remote.conf.json`:

```json
{
  "user": "user",
  "group": "user",

  "src": "/home/user/__BACKUPS/",
  "dst": "user@server:~/__BACKUPS/",

  "log": {
    "file": "/var/log/backup-remote.log",
    "access": 0660
    },

  "status": {
    "file": "/tmp/backup-remote.status",
    "access": 0660
    }
}
```

Execute:
```sh
jsonFile=/usr/local/etc/backup-remote.conf.json jsonPath="log.file" json-conf
``` 

Result:
```sh
/var/log/backup-remote.log
```