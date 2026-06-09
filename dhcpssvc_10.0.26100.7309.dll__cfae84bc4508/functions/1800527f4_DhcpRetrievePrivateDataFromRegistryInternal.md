# DhcpRetrievePrivateDataFromRegistryInternal

- ea: `0x1800527f4`
- end: `0x1800528ff`
- name: `DhcpRetrievePrivateDataFromRegistryInternal`
- size: `267`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180052908`

## callees

- `0x180002854`
- `0x1800527f4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180052828`
- `ADVAPI32!RegQueryValueExW` at `0x18005288b`
- `ADVAPI32!RegQueryValueExW` at `0x180052828`
- `ADVAPI32!RegQueryValueExW` at `0x18005288b`
- `KERNEL32!LocalAlloc` at `0x180052857`
- `KERNEL32!LocalAlloc` at `0x180052857`
- `KERNEL32!LocalFree` at `0x1800528ac`
- `KERNEL32!LocalFree` at `0x1800528ac`

## pseudocode

```c

```
