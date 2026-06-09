# EfsResolveProcessInfo

- ea: `0x180067890`
- end: `0x1800679ba`
- name: `EfsResolveProcessInfo`
- size: `298`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180090228`

## callees

- `0x180066a24`
- `0x180067890`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067995`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067995`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800679a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800679a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800678fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800678fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800678c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800678c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800678f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800678f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006797e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006797e`
- `ext-ms-win-security-efs-l1-1-0!EfsPlatform_GetCallerID` at `0x18006794d`
- `ext-ms-win-security-efs-l1-1-0!EfsPlatform_GetCallerID` at `0x18006794d`

## pseudocode

```c

```
