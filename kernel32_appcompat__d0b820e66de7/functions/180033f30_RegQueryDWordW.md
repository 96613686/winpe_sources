# RegQueryDWordW

- ea: `0x180033f30`
- end: `0x18003401c`
- name: `RegQueryDWordW`
- size: `236`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180033de4`
- `0x180034024`

## callees

- `0x180033f30`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180033f93`
- `ntdll!RtlSetLastWin32Error` at `0x180033f93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033f81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033f81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033ff4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034009`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033ff4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034009`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033fd9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033fd9`

## pseudocode

```c

```
