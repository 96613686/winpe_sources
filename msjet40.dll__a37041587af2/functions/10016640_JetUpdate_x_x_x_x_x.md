# JetUpdate(x,x,x,x,x)

- ea: `0x10016640`
- end: `0x100166a3`
- name: `_JetUpdate@20`
- size: `99`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvBookmark, unsigned int cbBookmark, unsigned int *pcbActual)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callees

- `0x10016640`
- `0x1003e7e0`
- `0x10044f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016665`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016665`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016696`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001664c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001664c`

## pseudocode

```c

```
