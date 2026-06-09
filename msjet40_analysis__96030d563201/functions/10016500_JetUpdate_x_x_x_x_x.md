# JetUpdate(x,x,x,x,x)

- ea: `0x10016500`
- end: `0x10016563`
- name: `_JetUpdate@20`
- size: `99`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvBookmark, unsigned int cbBookmark, unsigned int *pcbActual)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callees

- `0x10016500`
- `0x1003e650`
- `0x10044e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016525`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016525`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001650c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001650c`

## pseudocode

```c

```
