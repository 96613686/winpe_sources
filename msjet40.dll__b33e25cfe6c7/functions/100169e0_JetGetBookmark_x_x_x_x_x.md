# JetGetBookmark(x,x,x,x,x)

- ea: `0x100169e0`
- end: `0x10016a43`
- name: `_JetGetBookmark@20`
- size: `99`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvBookmark, unsigned int cbMax, unsigned int *pcbActual)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x100169e0`
- `0x1003e650`
- `0x10043e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016a36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100169ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100169ec`

## pseudocode

```c

```
