# JetMove(x,x,x,x)

- ea: `0x10016830`
- end: `0x100168c9`
- name: `_JetMove@16`
- size: `153`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, int cRow, JET_GRBIT grbit)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1008bbd7`
- `0x1008bcaf`
- `0x10094fc8`

## callees

- `0x10016830`
- `0x1003e650`
- `0x10043700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100168bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100168bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001683c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001683c`

## pseudocode

```c

```
