# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementACTProcessedPerfCounter

- ea: `0x59070`
- end: `0x590db`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementACTProcessedPerfCounter`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x6f6f0`

## callees

- `0x55bb0`
- `0x58df0`
- `0x59020`
- `0x59070`

## string_xrefs

- `0x59070`: `Server-Side Synchronization: ACTs Processed`
- `0x5907a`: `Server-Side Synchronization: ACTs Processed Throughput`
- `0x590ad`: `Server-Side Synchronization: Appointments Processed`
- `0x590b7`: `Server-Side Synchronization: Appointments Processed Throughput`
- `0x59094`: `Server-Side Synchronization: Contacts Processed`
- `0x5909e`: `Server-Side Synchronization: Contacts Processed Throughput`
- `0x590c6`: `Server-Side Synchronization: Tasks Processed`
- `0x590d0`: `Server-Side Synchronization: Tasks Processed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x59070  ldstr    aServerSideSync_48// "Server-Side Synchronization: ACTs Proce"...
0x59075  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x5907a  ldstr    aServerSideSync_49// "Server-Side Synchronization: ACTs Proce"...
0x5907f  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59084  ldarg.0
0x59085  call     valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetItemObjectType(class Microsoft.Crm.Asynchronous.EmailConnector.SyncData syncData)
0x5908a  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x5908f  stloc.0
0x59090  ldloc.0
0x59091  ldc.i4.1
0x59092  bne.un.s loc_590A9
0x59094  ldstr    aServerSideSync_52// "Server-Side Synchronization: Contacts P"...
0x59099  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x5909e  ldstr    aServerSideSync_53// "Server-Side Synchronization: Contacts P"...
0x590a3  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x590a8  ret
0x590a9  ldloc.0
0x590aa  ldc.i4.2
0x590ab  bne.un.s loc_590C2
0x590ad  ldstr    aServerSideSync_50// "Server-Side Synchronization: Appointmen"...
0x590b2  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x590b7  ldstr    aServerSideSync_51// "Server-Side Synchronization: Appointmen"...
0x590bc  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x590c1  ret
0x590c2  ldloc.0
0x590c3  ldc.i4.3
0x590c4  bne.un.s loc_590DA
0x590c6  ldstr    aServerSideSync_54// "Server-Side Synchronization: Tasks Proc"...
0x590cb  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x590d0  ldstr    aServerSideSync_55// "Server-Side Synchronization: Tasks Proc"...
0x590d5  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x590da  ret
```
