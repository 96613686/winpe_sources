# RegistryPath::Flush(void)

- ea: `0x180095f9c`
- end: `0x180096144`
- name: `?Flush@RegistryPath@@QEAAKXZ`
- size: `424`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003fbac`

## callees

- `0x180005ba0`
- `0x180006450`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180043e54`
- `0x18008bacc`
- `0x180095f9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18009603e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18009603e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800960cd`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800960cd`

## string_xrefs

- `0x180096126`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18009601f`: `%s: Failed to flush registry key "%s". Error code: 0x%08x.`
- `0x18009608b`: `%s: Failed to flush registry key "%s". Error code: 0x%08x.`
- `0x1800960fe`: `%s: Failed to flush registry key "%s". Error code: 0x%08x.`
- `0x180095fd9`: `RegistryPath::Flush`
- `0x18009611f`: `RegistryPath::Flush`

## pseudocode

```c

```
