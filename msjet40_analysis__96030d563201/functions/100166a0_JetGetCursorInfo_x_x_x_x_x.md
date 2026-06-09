# JetGetCursorInfo(x,x,x,x,x)

- ea: `0x100166a0`
- end: `0x100166fc`
- name: `_JetGetCursorInfo@20`
- size: `92`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvResult, unsigned int cbMax, unsigned int InfoLevel)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x100166a0`
- `0x1003e650`
- `0x10043fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100166c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100166ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100166c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100166ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100166ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100166ac`

## pseudocode

```c

```
