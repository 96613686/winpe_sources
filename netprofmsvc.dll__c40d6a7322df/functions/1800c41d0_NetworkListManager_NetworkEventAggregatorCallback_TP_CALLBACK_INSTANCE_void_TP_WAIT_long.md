# NetworkListManager::NetworkEventAggregatorCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800c41d0`
- end: `0x1800c46ec`
- name: `?NetworkEventAggregatorCallback@NetworkListManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `1308`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009990`
- `0x18000fab0`
- `0x180010340`
- `0x180013748`
- `0x18003d290`
- `0x180048710`
- `0x18004938c`
- `0x180049ba8`
- `0x180059334`
- `0x1800c0cf0`
- `0x1800c41d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c444e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c444e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c43f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c447c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c4569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c45cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c43f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c447c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c4569`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c45cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c4269`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c4269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c468f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c468f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c4688`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c4660`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c4660`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c445c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c44ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c451b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c445c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c44ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c451b`

## string_xrefs

- `0x1800c46da`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`

## pseudocode

```c

```
