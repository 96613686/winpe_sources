# RegQueryDWordW

- ea: `0x180031eac`
- end: `0x180031f76`
- name: `RegQueryDWordW`
- size: `202`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180031d70`
- `0x180031f7c`

## callees

- `0x180031eac`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180031f09`
- `ntdll!RtlSetLastWin32Error` at `0x180031f09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031efd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031efd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031f6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031f5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031f6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031f48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031f48`

## pseudocode

```c

```
