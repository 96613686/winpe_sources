# CUserObjectList::RemoveUser(void *,CUserObject * *)

- ea: `0x18007088c`
- end: `0x18007096a`
- name: `?RemoveUser@CUserObjectList@@QEAAJPEAXPEAPEAVCUserObject@@@Z`
- size: `222`
- prototype: `int(CUserObjectList *__hidden this, void *, struct CUserObject **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c7ac`

## callees

- `0x18007088c`
- `0x180070970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007094a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007094a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800708d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800708d3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800708f5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800708f5`

## pseudocode

```c

```
