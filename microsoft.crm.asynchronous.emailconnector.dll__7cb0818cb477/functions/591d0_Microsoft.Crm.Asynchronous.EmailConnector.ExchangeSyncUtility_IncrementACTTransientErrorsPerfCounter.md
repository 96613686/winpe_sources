# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementACTTransientErrorsPerfCounter

- ea: `0x591d0`
- end: `0x59236`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementACTTransientErrorsPerfCounter`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x55bb0`
- `0x58df0`
- `0x591d0`

## string_xrefs

- `0x591d0`: `Server-Side Synchronization: Transient Errors for ACTs`
- `0x591da`: `Server-Side Synchronization: ACTs Transient Errors Throughput`
- `0x59208`: `Server-Side Synchronization: Transient Errors for Appointments`
- `0x59212`: `Server-Side Synchronization: Appointments Transient Errors Throughput`
- `0x591ef`: `Server-Side Synchronization: Transient Errors for Contacts`
- `0x591f9`: `Server-Side Synchronization: Contacts Transient Errors Throughput`
- `0x59221`: `Server-Side Synchronization: Transient Errors for Tasks`
- `0x5922b`: `Server-Side Synchronization: Tasks Transient Errors Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x591d0  ldstr    aServerSideSync_72// "Server-Side Synchronization: Transient "...
0x591d5  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591da  ldstr    aServerSideSync_73// "Server-Side Synchronization: ACTs Trans"...
0x591df  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591e4  ldarg.0
0x591e5  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::GetExchangeItemType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x591ea  stloc.0
0x591eb  ldloc.0
0x591ec  ldc.i4.1
0x591ed  bne.un.s loc_59204
0x591ef  ldstr    aServerSideSync_76// "Server-Side Synchronization: Transient "...
0x591f4  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x591f9  ldstr    aServerSideSync_77// "Server-Side Synchronization: Contacts T"...
0x591fe  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59203  ret
0x59204  ldloc.0
0x59205  ldc.i4.2
0x59206  bne.un.s loc_5921D
0x59208  ldstr    aServerSideSync_74// "Server-Side Synchronization: Transient "...
0x5920d  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59212  ldstr    aServerSideSync_75// "Server-Side Synchronization: Appointmen"...
0x59217  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x5921c  ret
0x5921d  ldloc.0
0x5921e  ldc.i4.3
0x5921f  bne.un.s loc_59235
0x59221  ldstr    aServerSideSync_78// "Server-Side Synchronization: Transient "...
0x59226  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x5922b  ldstr    aServerSideSync_79// "Server-Side Synchronization: Tasks Tran"...
0x59230  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x59235  ret
```
