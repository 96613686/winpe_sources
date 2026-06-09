# CSpJobMgr::_JobCleaner(void *)

- ea: `0x180060d10`
- end: `0x180061025`
- name: `?_JobCleaner@CSpJobMgr@@CAKPEAX@Z`
- size: `789`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x18000c644`
- `0x180028a20`
- `0x180029a40`
- `0x18002aa74`
- `0x18005f41c`
- `0x18005f500`
- `0x1800607b8`
- `0x180060d10`
- `0x18006102c`
- `0x180068a28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180060e56`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180060e56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060e06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060e06`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180060dd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180060dd7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180060f9d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180060f9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060e6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060fb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060e6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060fb6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180060f22`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180060f22`

## string_xrefs

- `0x180060f0c`: `Storage Job Removed`

## pseudocode

```c

```
