# CMFWinsockEventService::UnregisterEvent(long)

- ea: `0x18012af94`
- end: `0x18012b0a7`
- name: `?UnregisterEvent@CMFWinsockEventService@@QEAAJJ@Z`
- size: `275`
- prototype: `__int64 __fastcall(CMFWinsockEventService *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800e248c`
- `0x1801155b4`

## callees

- `0x1800214fc`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801250c8`
- `0x18012af94`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012aff6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012aff6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b078`
- `WS2_32!WSAEventSelect` at `0x18012b026`
- `WS2_32!WSAEventSelect` at `0x18012b026`
- `WS2_32!__imp_WSAGetLastError` at `0x18012b030`
- `WS2_32!__imp_WSAGetLastError` at `0x18012b030`

## string_xrefs

- `0x18012afa0`: `CMFWinsockEventService::UnregisterEvent`

## pseudocode

```c

```
