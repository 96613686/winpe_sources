# JetRetrieveKey(x,x,x,x,x,x)

- ea: `0x10016dd0`
- end: `0x10016e2f`
- name: `_JetRetrieveKey@24`
- size: `95`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, void *pvKey, unsigned int cbMax, unsigned int *pcbActual, JET_GRBIT grbit)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x10016dd0`
- `0x1003e7e0`
- `0x10044c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016df5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016e22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016df5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016e22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10016ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10016ddc`

## pseudocode

```c

```
