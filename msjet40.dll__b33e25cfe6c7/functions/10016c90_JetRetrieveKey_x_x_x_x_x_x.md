# JetRetrieveKey(x,x,x,x,x,x)

- ea: `0x10016c90`
- end: `0x10016cef`
- name: `_JetRetrieveKey@24`
- size: `95`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvKey, unsigned int cbMax, unsigned int *pcbActual, JET_GRBIT grbit)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x10016c90`
- `0x1003e650`
- `0x10044ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016cb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016ce2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016cb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016ce2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10016c9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10016c9c`

## pseudocode

```c

```
