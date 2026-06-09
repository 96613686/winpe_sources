# CUserProfileService::ServiceHandler(ulong)

- ea: `0x18002712c`
- end: `0x1800271c0`
- name: `?ServiceHandler@CUserProfileService@@QEAAJK@Z`
- size: `148`
- prototype: `__int64 __fastcall(CUserProfileService *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025bf0`

## callees

- `0x1800253dc`
- `0x18002712c`
- `0x18002db38`
- `0x18004c0cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027147`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027147`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800271ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800271ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027175`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027175`

## string_xrefs

- `0x180027184`: `onecore\ds\security\gina\profile\profsvc\service.cpp`

## pseudocode

```c

```
