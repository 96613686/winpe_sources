# NetworkPropertyMaps::GetNetworkState(_GUID const &,uint)

- ea: `0x1800134b0`
- end: `0x18001373f`
- name: `?GetNetworkState@NetworkPropertyMaps@@SA?AW4tagNP_NETWORK_STATE@@AEBU_GUID@@I@Z`
- size: `655`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800837d0`
- `0x1800a4e30`

## callees

- `0x18000d7bc`
- `0x1800134b0`
- `0x180013748`
- `0x180015ae8`
- `0x180045f78`
- `0x180087698`
- `0x1800aba19`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013519`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001352b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013519`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001352b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800135c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001362b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800135c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001362b`

## string_xrefs

- `0x180013641`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`

## pseudocode

```c

```
