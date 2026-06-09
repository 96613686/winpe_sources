# WriteLogToDisk(ushort const *)

- ea: `0x18009e200`
- end: `0x18009e436`
- name: `?WriteLogToDisk@@YA_NPEBG@Z`
- size: `566`
- prototype: `bool __fastcall(LPCWSTR lpString)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18009dadc`
- `0x180111454`

## callees

- `0x180022120`
- `0x180025688`
- `0x18009e200`
- `0x180110558`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009e298`
- `KERNEL32!LeaveCriticalSection` at `0x18009e298`
- `KERNEL32!GetLastError` at `0x18009e3ac`
- `KERNEL32!GetLastError` at `0x18009e3ac`
- `KERNEL32!ReleaseMutex` at `0x18009e42b`
- `KERNEL32!ReleaseMutex` at `0x18009e42b`
- `KERNEL32!EnterCriticalSection` at `0x18009e239`
- `KERNEL32!EnterCriticalSection` at `0x18009e239`
- `KERNEL32!WaitForSingleObject` at `0x18009e2f0`
- `KERNEL32!WaitForSingleObject` at `0x18009e3dc`
- `KERNEL32!WaitForSingleObject` at `0x18009e2f0`
- `KERNEL32!WaitForSingleObject` at `0x18009e3dc`
- `KERNEL32!lstrlenW` at `0x18009e242`
- `KERNEL32!lstrlenW` at `0x18009e251`
- `KERNEL32!lstrlenW` at `0x18009e380`
- `KERNEL32!lstrlenW` at `0x18009e242`
- `KERNEL32!lstrlenW` at `0x18009e251`
- `KERNEL32!lstrlenW` at `0x18009e380`
- `KERNEL32!GlobalFree` at `0x18009e2a8`
- `KERNEL32!GlobalFree` at `0x18009e2a8`
- `KERNEL32!WriteFile` at `0x18009e3a2`
- `KERNEL32!WriteFile` at `0x18009e3a2`
- `KERNEL32!GetOverlappedResult` at `0x18009e3f9`
- `KERNEL32!GetOverlappedResult` at `0x18009e3f9`
- `KERNEL32!FlushFileBuffers` at `0x18009e415`
- `KERNEL32!FlushFileBuffers` at `0x18009e415`

## pseudocode

```c

```
