# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementACTFailedPerfCounter

- ea: `0x59160`
- end: `0x591c6`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementACTFailedPerfCounter`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x55bb0`
- `0x58df0`
- `0x59160`

## string_xrefs

- `0x59160`: `Server-Side Synchronization: ACTs Failed`
- `0x5916a`: `Server-Side Synchronization: ACTs Failed Throughput`
- `0x59198`: `Server-Side Synchronization: Appointments Failed`
- `0x591a2`: `Server-Side Synchronization: Appointments Failed Throughput`
- `0x5917f`: `Server-Side Synchronization: Contacts Failed`
- `0x59189`: `Server-Side Synchronization: Contacts Failed Throughput`
- `0x591b1`: `Server-Side Synchronization: Tasks Failed`
- `0x591bb`: `Server-Side Synchronization: Tasks Failed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x59160  ldstr    aServerSideSync_64// "Server-Side Synchronization: ACTs Faile"...
0x59165  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x5916a  ldstr    aServerSideSync_65// "Server-Side Synchronization: ACTs Faile"...
0x5916f  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59174  ldarg.0
0x59175  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x5917a  stloc.0
0x5917b  ldloc.0
0x5917c  ldc.i4.1
0x5917d  bne.un.s loc_59194
0x5917f  ldstr    aServerSideSync_68// "Server-Side Synchronization: Contacts F"...
0x59184  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59189  ldstr    aServerSideSync_69// "Server-Side Synchronization: Contacts F"...
0x5918e  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59193  ret
0x59194  ldloc.0
0x59195  ldc.i4.2
0x59196  bne.un.s loc_591AD
0x59198  ldstr    aServerSideSync_66// "Server-Side Synchronization: Appointmen"...
0x5919d  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591a2  ldstr    aServerSideSync_67// "Server-Side Synchronization: Appointmen"...
0x591a7  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591ac  ret
0x591ad  ldloc.0
0x591ae  ldc.i4.3
0x591af  bne.un.s loc_591C5
0x591b1  ldstr    aServerSideSync_70// "Server-Side Synchronization: Tasks Fail"...
0x591b6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591bb  ldstr    aServerSideSync_71// "Server-Side Synchronization: Tasks Fail"...
0x591c0  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591c5  ret
```
