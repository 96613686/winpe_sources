# CWSStream::HandleReceivedData(uchar const *,unsigned __int64,bool)

- ea: `0x18010cb60`
- end: `0x18010cd37`
- name: `?HandleReceivedData@CWSStream@@AEAAXPEBE_K_N@Z`
- size: `471`
- prototype: `void __fastcall(CWSStream *this, const unsigned __int8 *, const char *, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18010e770`
- `0x18010fa68`

## callees

- `0x1800018a4`
- `0x1800022f4`
- `0x180002550`
- `0x18001b3f8`
- `0x180040750`
- `0x180078c20`
- `0x1801093b0`
- `0x180109934`
- `0x18010cb60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010cbe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010cbe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010cc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010cd2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010cc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010cd2c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18010cc3f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18010cc3f`

## string_xrefs

- `0x18010cc05`: `Websocket read queue is full, need to block further receives.`

## pseudocode

```c

```
