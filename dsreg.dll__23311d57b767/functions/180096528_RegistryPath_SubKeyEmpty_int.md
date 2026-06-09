# RegistryPath::SubKeyEmpty(int *)

- ea: `0x180096528`
- end: `0x180096669`
- name: `?SubKeyEmpty@RegistryPath@@QEBAKPEAH@Z`
- size: `321`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800b4014`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18001bd30`
- `0x180043e54`
- `0x180096528`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800965e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800965e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009663c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009663c`

## string_xrefs

- `0x18009664d`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x180096582`: `RegistryPath::OpenSubKey`
- `0x180096590`: `RegistryPath::SubKeyEmpty`
- `0x180096646`: `RegistryPath::SubKeyEmpty`
- `0x180096609`: `%s: Failed to query registry key info "%s". Error code: 0x%08x.`

## pseudocode

```c

```
