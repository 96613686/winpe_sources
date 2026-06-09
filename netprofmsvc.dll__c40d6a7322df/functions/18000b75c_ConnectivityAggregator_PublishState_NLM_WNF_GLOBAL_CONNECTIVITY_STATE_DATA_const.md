# ConnectivityAggregator::PublishState(_NLM_WNF_GLOBAL_CONNECTIVITY_STATE_DATA const &)

- ea: `0x18000b75c`
- end: `0x18000b999`
- name: `?PublishState@ConnectivityAggregator@@AEAAXAEBU_NLM_WNF_GLOBAL_CONNECTIVITY_STATE_DATA@@@Z`
- size: `573`
- prototype: `void __fastcall(ConnectivityAggregator *__hidden this, const struct _NLM_WNF_GLOBAL_CONNECTIVITY_STATE_DATA *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800521c0`
- `0x180057ca0`
- `0x180080a88`
- `0x18012bbdc`

## callees

- `0x18000af4c`
- `0x18000b2c0`
- `0x18000b75c`
- `0x18000c018`
- `0x18004c5bc`
- `0x18012c220`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18000b79d`
- `ntdll!RtlPublishWnfStateData` at `0x18000b80a`
- `ntdll!RtlPublishWnfStateData` at `0x18000b79d`
- `ntdll!RtlPublishWnfStateData` at `0x18000b80a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b77c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b77c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b8d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b8d4`

## string_xrefs

- `0x18000b8fd`: `onecore\net\netprofiles\service\src\common\connectivityaggregator.cpp`
- `0x18000b91b`: `onecore\net\netprofiles\service\src\common\connectivityaggregator.cpp`
- `0x18000b939`: `onecore\net\netprofiles\service\src\common\connectivityaggregator.cpp`
- `0x18000b980`: `onecore\net\netprofiles\service\src\common\connectivityaggregator.cpp`

## pseudocode

```c

```
