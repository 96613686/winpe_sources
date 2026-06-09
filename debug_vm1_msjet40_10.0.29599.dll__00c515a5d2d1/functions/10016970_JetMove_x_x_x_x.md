# JetMove(x,x,x,x)

- ea: `0x10016970`
- end: `0x10016a09`
- name: `_JetMove@16`
- size: `153`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_TABLEID tableid, int cRow, JET_GRBIT grbit)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1008bd67`
- `0x1008be3f`
- `0x10095158`

## callees

- `0x10016970`
- `0x1003e7e0`
- `0x10043890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100169d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100169fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10016995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100169d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100169fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001697c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001697c`

## pseudocode

```c

```
