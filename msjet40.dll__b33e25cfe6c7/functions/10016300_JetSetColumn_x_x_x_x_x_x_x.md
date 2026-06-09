# JetSetColumn(x,x,x,x,x,x,x)

- ea: `0x10016300`
- end: `0x10016362`
- name: `_JetSetColumn@28`
- size: `98`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, const void *pvData, unsigned int cbData, JET_GRBIT grbit, JET_SETINFO *psetinfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x10016300`
- `0x1003e650`
- `0x10044c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016325`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016355`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016325`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016355`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001630c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001630c`

## pseudocode

```c

```
