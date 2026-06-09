# CMFWinsockEventService::RegisterEvent(long,CAsyncResult *)

- ea: `0x18012ab18`
- end: `0x18012ac5f`
- name: `?RegisterEvent@CMFWinsockEventService@@QEAAJJPEAVCAsyncResult@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(CMFWinsockEventService *__hidden this, int, struct CAsyncResult *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800e248c`

## callees

- `0x1800214fc`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801250c8`
- `0x18012ab18`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ab95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ab95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ac26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ac26`
- `WS2_32!WSAEventSelect` at `0x18012abd4`
- `WS2_32!WSAEventSelect` at `0x18012abd4`
- `WS2_32!__imp_WSAGetLastError` at `0x18012abde`
- `WS2_32!__imp_WSAGetLastError` at `0x18012abde`

## string_xrefs

- `0x18012ab2d`: `CMFWinsockEventService::RegisterEvent`

## pseudocode

```c

```
