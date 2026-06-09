# FTP_SERVICE::ReadRegistryDefaults(ulong *,ulong *)

- ea: `0x180005ef0`
- end: `0x180005fd8`
- name: `?ReadRegistryDefaults@FTP_SERVICE@@SAXPEAK0@Z`
- size: `232`
- prototype: `void __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180005940`

## callees

- `0x180005ef0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180005f32`
- `ADVAPI32!RegOpenKeyExW` at `0x180005f32`
- `ADVAPI32!RegQueryValueExW` at `0x180005f71`
- `ADVAPI32!RegQueryValueExW` at `0x180005fb1`
- `ADVAPI32!RegQueryValueExW` at `0x180005f71`
- `ADVAPI32!RegQueryValueExW` at `0x180005fb1`
- `ADVAPI32!RegCloseKey` at `0x180005fca`
- `ADVAPI32!RegCloseKey` at `0x180005fca`

## string_xrefs

- `0x180005f24`: `System\CurrentControlSet\Services\FTPSVC\Parameters`

## pseudocode

```c

```
