# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementExternalChangesPerfCounter

- ea: `0x590e0`
- end: `0x59153`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::IncrementExternalChangesPerfCounter`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5e6f0`

## callees

- `0x55c40`
- `0x590e0`

## string_xrefs

- `0x590e4`: `Server-Side Synchronization: ACTs Synchronized`
- `0x590f0`: `Server-side Synchronization: ACTs Synchronized Throughput`
- `0x5911d`: `Server-Side Synchronization: Appointments Synchronized`
- `0x59129`: `Server-side Synchronization: Appointments Synchronized Throughput`
- `0x59100`: `Server-Side Synchronization: Contacts Synchronized`
- `0x5910c`: `Server-side Synchronization: Contacts Synchronized Throughput`
- `0x5913a`: `Server-Side Synchronization: Tasks Synchronized`
- `0x59146`: `Server-side Synchronization: Tasks Synchronized Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x590e0  ldarg.0
0x590e1  brtrue.s loc_590E4
0x590e3  ret
0x590e4  ldstr    aServerSideSync_56// "Server-Side Synchronization: ACTs Synch"...
0x590e9  ldarg.1
0x590ea  conv.i8
0x590eb  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x590f0  ldstr    aServerSideSync_57// "Server-side Synchronization: ACTs Synch"...
0x590f5  ldarg.1
0x590f6  conv.i8
0x590f7  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x590fc  ldarg.0
0x590fd  ldc.i4.1
0x590fe  bne.un.s loc_59119
0x59100  ldstr    aServerSideSync_60// "Server-Side Synchronization: Contacts S"...
0x59105  ldarg.1
0x59106  conv.i8
0x59107  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x5910c  ldstr    aServerSideSync_61// "Server-side Synchronization: Contacts S"...
0x59111  ldarg.1
0x59112  conv.i8
0x59113  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x59118  ret
0x59119  ldarg.0
0x5911a  ldc.i4.2
0x5911b  bne.un.s loc_59136
0x5911d  ldstr    aServerSideSync_58// "Server-Side Synchronization: Appointmen"...
0x59122  ldarg.1
0x59123  conv.i8
0x59124  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x59129  ldstr    aServerSideSync_59// "Server-side Synchronization: Appointmen"...
0x5912e  ldarg.1
0x5912f  conv.i8
0x59130  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x59135  ret
0x59136  ldarg.0
0x59137  ldc.i4.3
0x59138  bne.un.s loc_59152
0x5913a  ldstr    aServerSideSync_62// "Server-Side Synchronization: Tasks Sync"...
0x5913f  ldarg.1
0x59140  conv.i8
0x59141  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x59146  ldstr    aServerSideSync_63// "Server-side Synchronization: Tasks Sync"...
0x5914b  ldarg.1
0x5914c  conv.i8
0x5914d  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName, int64 increment)
0x59152  ret
```
