# JetCloseDatabase(x,x,x)

- ea: `0x1001bc00`
- end: `0x1001bc56`
- name: `_JetCloseDatabase@12`
- size: `86`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_DBID dbid, JET_GRBIT grbit)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1001e380`

## callees

- `0x1001bc00`
- `0x1003e7e0`
- `0x10042b60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bc25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bc49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bc25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bc49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bc0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bc0c`

## pseudocode

```c

```
