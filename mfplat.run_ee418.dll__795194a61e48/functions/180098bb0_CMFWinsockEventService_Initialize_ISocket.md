# CMFWinsockEventService::Initialize(ISocket *)

- ea: `0x180098bb0`
- end: `0x180098d52`
- name: `?Initialize@CMFWinsockEventService@@QEAAJPEAUISocket@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(CMFWinsockEventService *__hidden this, struct ISocket *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800f2d10`

## callees

- `0x1800214fc`
- `0x1800255b0`
- `0x180038bf0`
- `0x180098bb0`
- `0x1801250c8`
- `0x18012a7fc`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098c02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098c02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098d37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098d37`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180098c75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180098c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098d25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098d25`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180098ccf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180098ccf`

## string_xrefs

- `0x180098bbf`: `CMFWinsockEventService::Initialize`

## pseudocode

```c

```
