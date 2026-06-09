# RunProcess

- ea: `0x180074fac`
- end: `0x1800750dc`
- name: `RunProcess`
- size: `304`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800718e0`

## callees

- `0x180047330`
- `0x180074fac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007507c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007507c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007506a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800750c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007506a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800750c4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180075060`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180075060`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180075095`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180075095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800750a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800750b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800750a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800750b1`
- `SPOOLSS!RevertToPrinterSelf` at `0x180074fda`
- `SPOOLSS!RevertToPrinterSelf` at `0x180074fda`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800750ba`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800750ba`

## pseudocode

```c

```
