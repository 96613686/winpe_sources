# JetRetrieveColumn(x,x,x,x,x,x,x,x)

- ea: `0x10016390`
- end: `0x10016406`
- name: `_JetRetrieveColumn@32`
- size: `118`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, void *pvData, unsigned int cbData, unsigned int *pcbActual, JET_GRBIT grbit, JET_RETINFO *pretinfo)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1008bd67`
- `0x10095158`

## callees

- `0x10016390`
- `0x1003e7e0`
- `0x10044a70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100163b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100163f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100163b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100163f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001639c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001639c`

## pseudocode

```c

```
