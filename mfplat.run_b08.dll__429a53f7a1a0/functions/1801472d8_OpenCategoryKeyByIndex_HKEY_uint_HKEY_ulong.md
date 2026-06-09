# OpenCategoryKeyByIndex(HKEY__ *,uint,HKEY__ * *,ulong)

- ea: `0x1801472d8`
- end: `0x180147433`
- name: `?OpenCategoryKeyByIndex@@YAJPEAUHKEY__@@IPEAPEAU1@K@Z`
- size: `347`
- prototype: `__int64 __fastcall(HKEY, DWORD dwIndex, PHKEY phkResult, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801453cc`

## callees

- `0x180094d38`
- `0x1801200d0`
- `0x180120ecc`
- `0x1801472d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801473b7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801473b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147411`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180147411`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801473f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801473f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180147370`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180147370`

## pseudocode

```c

```
