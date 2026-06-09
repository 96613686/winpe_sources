# CCoreDispatcherTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180029dbc`
- end: `0x180029f59`
- name: `?Start@CCoreDispatcherTaskPoolHandler@@QEAAJPEAUIComPoolTask@Internal@Windows@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct Windows::Internal::IComPoolTask *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a7a0`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x180018b30`
- `0x1800260a0`
- `0x180029dbc`
- `0x180035b88`
- `0x18004da44`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029f24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029f24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029eac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029eac`

## pseudocode

```c

```
