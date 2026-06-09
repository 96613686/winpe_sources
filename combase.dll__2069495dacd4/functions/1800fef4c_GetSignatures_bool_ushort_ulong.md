# GetSignatures(bool,ushort * * *,ulong *)

- ea: `0x1800fef4c`
- end: `0x1800ff247`
- name: `?GetSignatures@@YAX_NPEAPEAPEAGPEAK@Z`
- size: `763`
- prototype: `void __fastcall(bool includeSignaturesWithMaximumSnapshotsCaptured, wchar_t ***signatures, unsigned int *numSignaturesReturned)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800fe734`
- `0x180169dfc`

## callees

- `0x1800fef4c`
- `0x1800ff250`
- `0x1800ff384`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ff0b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ff0b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ff1bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ff1bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ff072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ff07c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ff1d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ff072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ff07c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ff1d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ff22d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ff22d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ff051`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ff16e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ff051`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ff16e`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800ff01e`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800ff01e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ff10a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ff10a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ff126`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ff126`

## pseudocode

```c

```
