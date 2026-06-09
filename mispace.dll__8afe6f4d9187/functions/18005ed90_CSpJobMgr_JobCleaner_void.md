# CSpJobMgr::_JobCleaner(void *)

- ea: `0x18005ed90`
- end: `0x18005f074`
- name: `?_JobCleaner@CSpJobMgr@@CAKPEAX@Z`
- size: `740`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x18000c704`
- `0x180027f18`
- `0x180028ec0`
- `0x180029e44`
- `0x18005d58c`
- `0x18005d670`
- `0x18005e8d0`
- `0x18005ed90`
- `0x18005f07c`
- `0x1800668f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005eeca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005eeca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ee80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ee80`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ee57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ee57`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005eff9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005eff9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005efe9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005efe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eedb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f00c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005eedb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f00c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ef8a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005ef8a`

## string_xrefs

- `0x18005ef74`: `Storage Job Removed`

## pseudocode

```c

```
