# EnterpriseDataProtection::CreateEDPCleanupProcessAndWait(ActivityContext *,ushort const *,ushort const *,ulong)

- ea: `0x18006d4bc`
- end: `0x18006d5ad`
- name: `?CreateEDPCleanupProcessAndWait@EnterpriseDataProtection@@AEAAJPEAVActivityContext@@PEBG1K@Z`
- size: `241`
- prototype: `__int64 __fastcall(EnterpriseDataProtection *__hidden this, struct ActivityContext *, const unsigned __int16 *, const unsigned __int16 *, DWORD ExitCode)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006de08`

## callees

- `0x18001796c`
- `0x18001ab40`
- `0x18001aec8`
- `0x18006d4bc`
- `0x180070e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006d524`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006d524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d535`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18006d55d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18006d55d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d59a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d59a`

## pseudocode

```c

```
