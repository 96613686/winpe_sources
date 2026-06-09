# SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)

- ea: `0x1800193a0`
- end: `0x180019504`
- name: `?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z`
- size: `356`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int *, int)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800130c8`
- `0x180017f60`
- `0x180029dbc`
- `0x18002a02c`
- `0x18002a1d0`
- `0x18002a4b0`
- `0x18002f280`
- `0x1800384b8`
- `0x1800391fc`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800193a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019470`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019470`

## string_xrefs

- `0x1800193c7`: `SxRegReadDWORD`

## pseudocode

```c

```
