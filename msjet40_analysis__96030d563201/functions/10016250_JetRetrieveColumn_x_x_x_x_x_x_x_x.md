# JetRetrieveColumn(x,x,x,x,x,x,x,x)

- ea: `0x10016250`
- end: `0x100162c6`
- name: `_JetRetrieveColumn@32`
- size: `118`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, void *pvData, unsigned int cbData, unsigned int *pcbActual, JET_GRBIT grbit, JET_RETINFO *pretinfo)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1008bbd7`
- `0x10094fc8`

## callees

- `0x10016250`
- `0x1003e650`
- `0x100448f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100162b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100162b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001625c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001625c`

## pseudocode

```c

```
