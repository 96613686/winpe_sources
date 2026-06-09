# JetGetCursorInfo(x,x,x,x,x)

- ea: `0x100167e0`
- end: `0x1001683c`
- name: `_JetGetCursorInfo@20`
- size: `92`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvResult, unsigned int cbMax, unsigned int InfoLevel)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x100167e0`
- `0x1003e7e0`
- `0x10044160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001682f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001682f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100167ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100167ec`

## pseudocode

```c

```
