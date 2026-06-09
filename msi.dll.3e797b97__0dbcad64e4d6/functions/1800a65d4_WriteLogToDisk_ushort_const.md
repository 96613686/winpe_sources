# WriteLogToDisk(ushort const *)

- ea: `0x1800a65d4`
- end: `0x1800a685d`
- name: `?WriteLogToDisk@@YA_NPEBG@Z`
- size: `649`
- prototype: `bool __fastcall(LPCWSTR lpString)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004ccbc`
- `0x1800a5e58`

## callees

- `0x180010ac0`
- `0x180014288`
- `0x1800a65d4`
- `0x18011975c`
- `0x180265240`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800a667e`
- `KERNEL32!LeaveCriticalSection` at `0x1800a667e`
- `KERNEL32!GetLastError` at `0x1800a67b5`
- `KERNEL32!GetLastError` at `0x1800a67b5`
- `KERNEL32!ReleaseMutex` at `0x1800a684c`
- `KERNEL32!ReleaseMutex` at `0x1800a684c`
- `KERNEL32!EnterCriticalSection` at `0x1800a660d`
- `KERNEL32!EnterCriticalSection` at `0x1800a660d`
- `KERNEL32!WaitForSingleObject` at `0x1800a66e3`
- `KERNEL32!WaitForSingleObject` at `0x1800a67eb`
- `KERNEL32!WaitForSingleObject` at `0x1800a66e3`
- `KERNEL32!WaitForSingleObject` at `0x1800a67eb`
- `KERNEL32!lstrlenW` at `0x1800a661c`
- `KERNEL32!lstrlenW` at `0x1800a6631`
- `KERNEL32!lstrlenW` at `0x1800a677d`
- `KERNEL32!lstrlenW` at `0x1800a661c`
- `KERNEL32!lstrlenW` at `0x1800a6631`
- `KERNEL32!lstrlenW` at `0x1800a677d`
- `KERNEL32!GlobalFree` at `0x1800a6694`
- `KERNEL32!GlobalFree` at `0x1800a6694`
- `KERNEL32!WriteFile` at `0x1800a67a5`
- `KERNEL32!WriteFile` at `0x1800a67a5`
- `KERNEL32!GetOverlappedResult` at `0x1800a680e`
- `KERNEL32!GetOverlappedResult` at `0x1800a680e`
- `KERNEL32!FlushFileBuffers` at `0x1800a6830`
- `KERNEL32!FlushFileBuffers` at `0x1800a6830`

## pseudocode

```c

```
