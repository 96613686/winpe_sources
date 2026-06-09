# InterfaceIdentifier::GetMapping(_GUID const &)

- ea: `0x180015b10`
- end: `0x180015d40`
- name: `?GetMapping@InterfaceIdentifier@@SA?AV?$tuple@KUIdentity@InterfaceIdentifier@@@std@@AEBU_GUID@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(int, GUID *InterfaceGuid)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ee14`
- `0x180057ca0`
- `0x18005cc90`
- `0x180084d90`
- `0x18008e210`
- `0x1801069f8`

## callees

- `0x18000e190`
- `0x180013748`
- `0x180015608`
- `0x180015ae8`
- `0x180015b10`
- `0x1800a88a0`
- `0x18012c550`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cec`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180015c09`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180015c09`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180015bed`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180015bed`

## string_xrefs

- `0x180015c73`: `onecore\net\netprofiles\service\src\common\interfaceidentifier.cpp`
- `0x180015cfa`: `onecore\net\netprofiles\service\src\common\interfaceidentifier.cpp`
- `0x180015d27`: `onecore\net\netprofiles\service\src\common\interfaceidentifier.cpp`

## pseudocode

```c

```
