# NetworkListManager::FirewallEventMgrCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180085d20`
- end: `0x1800860be`
- name: `?FirewallEventMgrCallback@NetworkListManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `926`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d428`
- `0x18000e6bc`
- `0x18000fab0`
- `0x180010340`
- `0x180013748`
- `0x180048710`
- `0x180049ba8`
- `0x180085d20`
- `0x1800c0cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085e02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085f8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085e02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085f8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085ec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085fdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085ec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085fdb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085dae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085dae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086064`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180085ed0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180085ed0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18008605d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180086037`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180086037`

## string_xrefs

- `0x1800860ac`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`

## pseudocode

```c

```
