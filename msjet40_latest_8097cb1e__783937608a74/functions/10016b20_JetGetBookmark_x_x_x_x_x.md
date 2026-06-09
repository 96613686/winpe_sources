# JetGetBookmark(x,x,x,x,x)

- ea: `0x10016b20`
- end: `0x10016b83`
- name: `_JetGetBookmark@20`
- size: `99`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvBookmark, unsigned int cbMax, unsigned int *pcbActual)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x10016b20`
- `0x1003e7e0`
- `0x10044020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016b76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016b76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10016b2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10016b2c`

## pseudocode

```c

```
