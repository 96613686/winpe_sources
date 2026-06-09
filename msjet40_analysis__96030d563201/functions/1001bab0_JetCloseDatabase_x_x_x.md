# JetCloseDatabase(x,x,x)

- ea: `0x1001bab0`
- end: `0x1001bb06`
- name: `_JetCloseDatabase@12`
- size: `86`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_DBID dbid, JET_GRBIT grbit)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1001e230`

## callees

- `0x1001bab0`
- `0x1003e650`
- `0x100429d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bad5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001baf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bad5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001baf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001babc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001babc`

## pseudocode

```c

```
