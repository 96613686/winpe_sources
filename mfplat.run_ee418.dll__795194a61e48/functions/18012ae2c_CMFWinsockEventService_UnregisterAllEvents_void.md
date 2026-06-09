# CMFWinsockEventService::UnregisterAllEvents(void)

- ea: `0x18012ae2c`
- end: `0x18012af8b`
- name: `?UnregisterAllEvents@CMFWinsockEventService@@QEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(CMFWinsockEventService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180128e00`

## callees

- `0x1800214fc`
- `0x1800255b0`
- `0x180038bf0`
- `0x180120ecc`
- `0x1801250c8`
- `0x18012ae2c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012aea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012aea7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012af3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012af3a`
- `WS2_32!WSAEventSelect` at `0x18012aee8`
- `WS2_32!WSAEventSelect` at `0x18012aee8`
- `WS2_32!__imp_WSAGetLastError` at `0x18012aef2`
- `WS2_32!__imp_WSAGetLastError` at `0x18012aef2`

## string_xrefs

- `0x18012ae41`: `CMFWinsockEventService::UnregisterAllEvents`

## pseudocode

```c

```
