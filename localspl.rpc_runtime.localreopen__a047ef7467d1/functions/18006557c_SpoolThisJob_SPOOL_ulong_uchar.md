# SpoolThisJob(_SPOOL *,ulong,uchar *)

- ea: `0x18006557c`
- end: `0x180065ad5`
- name: `?SpoolThisJob@@YAHPEAU_SPOOL@@KPEAE@Z`
- size: `1369`
- prototype: `__int64 __fastcall(struct _SPOOL *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18006499c`

## callees

- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x18000d0d8`
- `0x18000ee90`
- `0x180011f00`
- `0x18001fb10`
- `0x1800237b0`
- `0x18002ea64`
- `0x18002fb3c`
- `0x180031f90`
- `0x180032fd4`
- `0x1800344ac`
- `0x180034ad0`
- `0x180034f24`
- `0x18003e984`
- `0x180042b3c`
- `0x180043adc`
- `0x180046650`
- `0x18004e5a4`
- `0x180054638`
- `0x1800602a8`
- `0x18006557c`
- `0x180065e24`
- `0x180072a40`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180065624`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006565c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180065624`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006565c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800659ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800659ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006586b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006586b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006569e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800656d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800659c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006569e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800656d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800659c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800659ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800659ff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065a09`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065a09`
- `SPOOLSS!RevertToPrinterSelf` at `0x180065766`
- `SPOOLSS!RevertToPrinterSelf` at `0x180065766`
- `SPOOLSS!CheckLocalCall` at `0x1800658b7`
- `SPOOLSS!CheckLocalCall` at `0x1800658b7`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180065861`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180065861`

## string_xrefs

- `0x180065874`: `ImpersonatePrinterClient failed:  Error %d`
- `0x18006589f`: `CreateFile( %ws ) GENERIC_WRITE failed: Error %d`

## pseudocode

```c

```
