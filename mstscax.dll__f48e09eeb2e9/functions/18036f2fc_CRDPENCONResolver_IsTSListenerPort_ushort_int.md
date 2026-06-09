# CRDPENCONResolver::IsTSListenerPort(ushort,int *)

- ea: `0x18036f2fc`
- end: `0x18036f7dc`
- name: `?IsTSListenerPort@CRDPENCONResolver@@CAJGPEAH@Z`
- size: `1248`
- prototype: `__int64 __fastcall(unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18036eed0`

## callees

- `0x1800011f4`
- `0x180001e8c`
- `0x180039ce4`
- `0x1800f7748`
- `0x18025de7c`
- `0x18036f2fc`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18036f4f2`
- `KERNEL32!LocalAlloc` at `0x18036f4f2`
- `KERNEL32!LocalFree` at `0x18036f7b9`
- `KERNEL32!LocalFree` at `0x18036f7b9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18036f43e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18036f43e`
- `ADVAPI32!RegOpenKeyExW` at `0x18036f367`
- `ADVAPI32!RegOpenKeyExW` at `0x18036f5db`
- `ADVAPI32!RegOpenKeyExW` at `0x18036f367`
- `ADVAPI32!RegOpenKeyExW` at `0x18036f5db`
- `ADVAPI32!RegQueryValueExW` at `0x18036f664`
- `ADVAPI32!RegQueryValueExW` at `0x18036f664`
- `ADVAPI32!RegCloseKey` at `0x18036f5b8`
- `ADVAPI32!RegCloseKey` at `0x18036f794`
- `ADVAPI32!RegCloseKey` at `0x18036f7a7`
- `ADVAPI32!RegCloseKey` at `0x18036f5b8`
- `ADVAPI32!RegCloseKey` at `0x18036f794`
- `ADVAPI32!RegCloseKey` at `0x18036f7a7`
- `ADVAPI32!RegEnumKeyExW` at `0x18036f547`
- `ADVAPI32!RegEnumKeyExW` at `0x18036f547`

## string_xrefs

- `0x18036f389`: `RegOpenKeyEx failed: 0x%x`

## pseudocode

```c

```
