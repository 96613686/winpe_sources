# JetSetColumn(x,x,x,x,x,x,x)

- ea: `0x10016440`
- end: `0x100164a2`
- name: `_JetSetColumn@28`
- size: `98`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, const void *pvData, unsigned int cbData, JET_GRBIT grbit, JET_SETINFO *psetinfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x10016440`
- `0x1003e7e0`
- `0x10044d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016495`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016495`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001644c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001644c`

## pseudocode

```c

```
