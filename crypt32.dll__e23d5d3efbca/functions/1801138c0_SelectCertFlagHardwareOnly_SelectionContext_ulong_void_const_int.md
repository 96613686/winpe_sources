# SelectCertFlagHardwareOnly(SelectionContext *,ulong,void const * *,int *)

- ea: `0x1801138c0`
- end: `0x180113a8b`
- name: `?SelectCertFlagHardwareOnly@@YAKPEAUSelectionContext@@KPEAPEBXPEAH@Z`
- size: `459`
- prototype: `unsigned int __fastcall(struct SelectionContext *, unsigned int, const void **, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180068730`
- `0x1801138c0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113952`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113944`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113981`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113944`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113981`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180113928`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180113928`
- `CRYPTSP!CryptGetProvParam` at `0x180113a2e`
- `CRYPTSP!CryptGetProvParam` at `0x180113a2e`
- `CRYPTSP!CryptAcquireContextW` at `0x180113a04`
- `CRYPTSP!CryptAcquireContextW` at `0x180113a04`
- `CRYPTSP!CryptReleaseContext` at `0x180113a74`
- `CRYPTSP!CryptReleaseContext` at `0x180113a74`

## string_xrefs

- `0x180113921`: `ncrypt.dll`
- `0x18011393a`: `NCryptOpenStorageProvider`

## pseudocode

```c

```
