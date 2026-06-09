# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x1800f8aa4`
- end: `0x1800f8bf8`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `340`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f8c00`

## callees

- `0x180008de0`
- `0x18000bef4`
- `0x18000da9c`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800bc9c8`
- `0x1800f8aa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f8b37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f8b37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f8afd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f8afd`
- `DMCmnUtils!UnicodeToMB` at `0x1800f8b84`
- `DMCmnUtils!UnicodeToMB` at `0x1800f8b84`

## pseudocode

```c

```
