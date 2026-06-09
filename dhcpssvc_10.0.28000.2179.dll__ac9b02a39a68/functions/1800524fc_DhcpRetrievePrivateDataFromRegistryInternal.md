# DhcpRetrievePrivateDataFromRegistryInternal

- ea: `0x1800524fc`
- end: `0x180052610`
- name: `DhcpRetrievePrivateDataFromRegistryInternal`
- size: `276`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180052618`

## callees

- `0x18000282c`
- `0x1800524fc`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180052536`
- `ADVAPI32!RegQueryValueExW` at `0x18005259c`
- `ADVAPI32!RegQueryValueExW` at `0x180052536`
- `ADVAPI32!RegQueryValueExW` at `0x18005259c`
- `KERNEL32!LocalAlloc` at `0x180052568`
- `KERNEL32!LocalAlloc` at `0x180052568`
- `KERNEL32!LocalFree` at `0x1800525bd`
- `KERNEL32!LocalFree` at `0x1800525bd`

## pseudocode

```c

```
