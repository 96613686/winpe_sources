# Microsoft.Crm.Asynchronous.PerformanceCounters::AddEmailConnectorCountersForInstall

- ea: `0xa90`
- end: `0xf86`
- name: `Microsoft.Crm.Asynchronous.PerformanceCounters::AddEmailConnectorCountersForInstall`
- size: `1270`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x8f0`

## string_xrefs

- `0xa91`: `Server-Side Synchronization: Synchronous Delays`
- `0xaac`: `Server-Side Synchronization (Incoming): Emails Processed`
- `0xab1`: `Total number of incoming emails processed`
- `0xac7`: `Server-Side Synchronization (Incoming): Items Processed Throughput`
- `0xacc`: `Throughput of processed incoming mail items`
- `0xae2`: `Server-Side Synchronization (Incoming): Emails Delivered`
- `0xae7`: `Total number of incoming emails delivered`
- `0xafd`: `Server-Side Synchronization (Incoming): Items Delivered Throughput`
- `0xb02`: `Throughput of delivered incoming mail items`
- `0xb18`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0xb1d`: `Total number of incoming mail items discarded`
- `0xb33`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0xb38`: `Throughput of discarded incoming mail items`
- `0xb4e`: `Server-Side Synchronization (Incoming): Items Failed`
- `0xb53`: `Total number of incoming mail items failed`
- `0xb69`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0xb6e`: `Throughput of failed incoming mail items`
- `0xb84`: `Server-Side Synchronization (Incoming): Items Suspected`
- `0xb89`: `Total number of incoming mail items potentially corrupted`
- `0xb9f`: `Server-Side Synchronization (Incoming): Items Suspected Throughput`
- `0xba4`: `Throughput of potentially corrupted incoming mail items`
- `0xbba`: `Server-Side Synchronization (Incoming): Transient Errors`
- `0xbbf`: `Total number of transient errors in incoming mail items`
- `0xbd5`: `Server-Side Synchronization (Incoming): Transient Errors Throughput`
- `0xbda`: `Throughput of transient errors in incoming mail items`
- `0xbf0`: `Server-Side Synchronization (Incoming): Throughput of bytes sent in EWS requests`
- `0xbf5`: `Throughput of bytes sent in EWS requests while processing incoming mail items`
- `0xc0b`: `Server-Side Synchronization (Incoming): Throughput of bytes received in EWS responses`
- `0xc10`: `Throughput of bytes received in EWS responses while processing incoming mail items`
- `0xc26`: `Server-Side Synchronization (Incoming): Current number of EWS Connections`
- `0xc2b`: `Current number of EWS connections being used for processing incoming mail items`
- `0xc41`: `Server-Side Synchronization (Incoming): Average duration of an EWS connection`
- `0xc46`: `Average duration of an EWS connection for incoming email`
- `0xc5c`: `Server-Side Synchronization (Incoming): Average duration of an EWS connection base`
- `0xc61`: `Average duration of an EWS connection for incoming email (base)`
- `0xc77`: `Server-Side Synchronization (Incoming): Throughput of bytes sent via POP3 protocol`
- `0xc7c`: `Throughput of bytes sent via POP3 protocol while processing incoming mail items`
- `0xc92`: `Server-Side Synchronization (Incoming): Throughput of bytes received via POP3 protocol`
- `0xc97`: `Throughput of bytes received via POP3 protocol while processing incoming mail items`
- `0xcad`: `Server-Side Synchronization (Incoming): Current number of POP3 Connections`
- `0xcb2`: `Current number of POP3 connections being used for processing incoming mail items`
- `0xcc8`: `Server-Side Synchronization (Incoming): Average duration of a POP3 connection`
- `0xce3`: `Server-Side Synchronization (Incoming): Average duration of a POP3 connection base`
- `0xcfe`: `Server-Side Synchronization (Outgoing): Items Processed`
- `0xd19`: `Server-Side Synchronization (Outgoing): Items Processed Throughput`
- `0xd34`: `Server-Side Synchronization (Outgoing): Items Delivered`
- `0xd4f`: `Server-Side Synchronization (Outgoing): Items Delivered Throughput`
- `0xd6a`: `Server-Side Synchronization (Outgoing): Items Failed`
- `0xd85`: `Server-Side Synchronization (Outgoing): Items Failed Throughput`
- `0xda0`: `Server-Side Synchronization (Outgoing): Transient Errors`
- `0xdbb`: `Server-Side Synchronization (Outgoing): Transient Errors Throughput`
- `0xdd6`: `Server-Side Synchronization (Outgoing): Throughput of bytes sent in EWS requests`
- `0xdf1`: `Server-Side Synchronization (Outgoing): Throughput of bytes received in EWS responses`
- `0xe0c`: `Server-Side Synchronization (Outgoing): Current number of EWS Connections`
- `0xe27`: `Server-Side Synchronization (Outgoing): Average duration of an EWS connection`
- `0xe42`: `Server-Side Synchronization (Outgoing): Average duration of an EWS connection base`
- `0xe5d`: `Server-Side Synchronization (Outgoing): Throughput of bytes sent via SMTP protocol`
- `0xe62`: `Approximate throughput of bytes sent via SMTP protocol while sending outgoing email`
- `0xe78`: `Server-Side Synchronization (Outgoing): Current number of SMTP Connections`
- `0xe93`: `Server-Side Synchronization (Outgoing): Average duration of an SMTP connection`
- `0xeae`: `Server-Side Synchronization (Outgoing): Average duration of an SMTP connection base`
- `0xec9`: `Server-Side Synchronization (Exchange Auto-discover): Cache Hit`
- `0xece`: `Total number of auto discover requests that were fulfilled using the cache`
- `0xee4`: `Server-Side Synchronization (Exchange Auto-discover): Cache Miss`
- `0xee9`: `Total number of auto discover requests that could not be fulfilled using the cache`
- `0xeff`: `Server-Side Synchronization (Exchange Auto-discover): Discoveries Failed`
- `0xf1a`: `Server-Side Synchronization (Exchange Auto-discover): Discoveries Successful`
- `0xf35`: `Server-Side Synchronization (Exchange Auto-discover): Current number of connections`
- `0xf50`: `Server-Side Synchronization (Exchange Auto-discover): Average time taken for auto-discovery`
- `0xf6b`: `Server-Side Synchronization (Exchange Auto-discover): Average time taken for auto-discovery base`

## pseudocode

```c

```

## disassembly

```asm
0xa90  ldarg.0
0xa91  ldstr    aServerSideSync// "Server-Side Synchronization: Synchronou"...
0xa96  ldstr    aTotalNumberOfT// "Total number of times a synchronous del"...
0xa9b  ldc.i4   0x10100
0xaa0  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xaa5  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xaaa  pop
0xaab  ldarg.0
0xaac  ldstr    aServerSideSync_0// "Server-Side Synchronization (Incoming):"...
0xab1  ldstr    aTotalNumberOfI// "Total number of incoming emails process"...
0xab6  ldc.i4   0x10100
0xabb  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xac0  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xac5  pop
0xac6  ldarg.0
0xac7  ldstr    aServerSideSync_1// "Server-Side Synchronization (Incoming):"...
0xacc  ldstr    aThroughputOfPr// "Throughput of processed incoming mail i"...
0xad1  ldc.i4   0x10410500
0xad6  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xadb  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xae0  pop
0xae1  ldarg.0
0xae2  ldstr    aServerSideSync_2// "Server-Side Synchronization (Incoming):"...
0xae7  ldstr    aTotalNumberOfI_0// "Total number of incoming emails deliver"...
0xaec  ldc.i4   0x10100
0xaf1  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xaf6  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xafb  pop
0xafc  ldarg.0
0xafd  ldstr    aServerSideSync_3// "Server-Side Synchronization (Incoming):"...
0xb02  ldstr    aThroughputOfDe// "Throughput of delivered incoming mail i"...
0xb07  ldc.i4   0x10410500
0xb0c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xb11  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xb16  pop
0xb17  ldarg.0
0xb18  ldstr    aServerSideSync_4// "Server-Side Synchronization (Incoming):"...
0xb1d  ldstr    aTotalNumberOfI_1// "Total number of incoming mail items dis"...
0xb22  ldc.i4   0x10100
0xb27  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xb2c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xb31  pop
0xb32  ldarg.0
0xb33  ldstr    aServerSideSync_5// "Server-Side Synchronization (Incoming):"...
0xb38  ldstr    aThroughputOfDi// "Throughput of discarded incoming mail i"...
0xb3d  ldc.i4   0x10410500
0xb42  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xb47  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xb4c  pop
0xb4d  ldarg.0
0xb4e  ldstr    aServerSideSync_6// "Server-Side Synchronization (Incoming):"...
0xb53  ldstr    aTotalNumberOfI_2// "Total number of incoming mail items fai"...
0xb58  ldc.i4   0x10100
0xb5d  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xb62  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xb67  pop
0xb68  ldarg.0
0xb69  ldstr    aServerSideSync_7// "Server-Side Synchronization (Incoming):"...
0xb6e  ldstr    aThroughputOfFa// "Throughput of failed incoming mail item"...
0xb73  ldc.i4   0x10410500
0xb78  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xb7d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xb82  pop
0xb83  ldarg.0
0xb84  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0xb89  ldstr    aTotalNumberOfI_3// "Total number of incoming mail items pot"...
0xb8e  ldc.i4   0x10100
0xb93  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xb98  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xb9d  pop
0xb9e  ldarg.0
0xb9f  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0xba4  ldstr    aThroughputOfPo// "Throughput of potentially corrupted inc"...
0xba9  ldc.i4   0x10410500
0xbae  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xbb3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xbb8  pop
0xbb9  ldarg.0
0xbba  ldstr    aServerSideSync_10// "Server-Side Synchronization (Incoming):"...
0xbbf  ldstr    aTotalNumberOfT_0// "Total number of transient errors in inc"...
0xbc4  ldc.i4   0x10100
0xbc9  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xbce  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xbd3  pop
0xbd4  ldarg.0
0xbd5  ldstr    aServerSideSync_11// "Server-Side Synchronization (Incoming):"...
0xbda  ldstr    aThroughputOfTr// "Throughput of transient errors in incom"...
0xbdf  ldc.i4   0x10410500
0xbe4  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xbe9  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xbee  pop
0xbef  ldarg.0
0xbf0  ldstr    aServerSideSync_12// "Server-Side Synchronization (Incoming):"...
0xbf5  ldstr    aThroughputOfBy// "Throughput of bytes sent in EWS request"...
0xbfa  ldc.i4   0x10410500
0xbff  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xc04  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xc09  pop
0xc0a  ldarg.0
0xc0b  ldstr    aServerSideSync_13// "Server-Side Synchronization (Incoming):"...
0xc10  ldstr    aThroughputOfBy_0// "Throughput of bytes received in EWS res"...
0xc15  ldc.i4   0x10410500
0xc1a  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xc1f  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xc24  pop
0xc25  ldarg.0
0xc26  ldstr    aServerSideSync_14// "Server-Side Synchronization (Incoming):"...
0xc2b  ldstr    aCurrentNumberO// "Current number of EWS connections being"...
0xc30  ldc.i4   0x10000
0xc35  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xc3a  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xc3f  pop
0xc40  ldarg.0
0xc41  ldstr    aServerSideSync_15// "Server-Side Synchronization (Incoming):"...
0xc46  ldstr    aAverageDuratio// "Average duration of an EWS connection f"...
0xc4b  ldc.i4   0x30020400
0xc50  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xc55  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xc5a  pop
0xc5b  ldarg.0
0xc5c  ldstr    aServerSideSync_16// "Server-Side Synchronization (Incoming):"...
0xc61  ldstr    aAverageDuratio_0// "Average duration of an EWS connection f"...
0xc66  ldc.i4   0x40030402
0xc6b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xc70  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xc75  pop
0xc76  ldarg.0
0xc77  ldstr    aServerSideSync_17// "Server-Side Synchronization (Incoming):"...
0xc7c  ldstr    aThroughputOfBy_1// "Throughput of bytes sent via POP3 proto"...
0xc81  ldc.i4   0x10410500
0xc86  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xc8b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xc90  pop
0xc91  ldarg.0
0xc92  ldstr    aServerSideSync_18// "Server-Side Synchronization (Incoming):"...
0xc97  ldstr    aThroughputOfBy_2// "Throughput of bytes received via POP3 p"...
0xc9c  ldc.i4   0x10410500
0xca1  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xca6  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xcab  pop
0xcac  ldarg.0
0xcad  ldstr    aServerSideSync_19// "Server-Side Synchronization (Incoming):"...
0xcb2  ldstr    aCurrentNumberO_0// "Current number of POP3 connections bein"...
0xcb7  ldc.i4   0x10000
0xcbc  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xcc1  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xcc6  pop
0xcc7  ldarg.0
0xcc8  ldstr    aServerSideSync_20// "Server-Side Synchronization (Incoming):"...
0xccd  ldstr    aAverageDuratio_1// "Average duration of a POP3 connection"
0xcd2  ldc.i4   0x30020400
0xcd7  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xcdc  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xce1  pop
0xce2  ldarg.0
0xce3  ldstr    aServerSideSync_21// "Server-Side Synchronization (Incoming):"...
0xce8  ldstr    aAverageDuratio_2// "Average duration of a POP3 connection ("...
0xced  ldc.i4   0x40030402
0xcf2  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xcf7  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xcfc  pop
0xcfd  ldarg.0
0xcfe  ldstr    aServerSideSync_22// "Server-Side Synchronization (Outgoing):"...
0xd03  ldstr    aTotalNumberOfO// "Total number of outgoing mail items pro"...
0xd08  ldc.i4   0x10100
0xd0d  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xd12  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xd17  pop
0xd18  ldarg.0
0xd19  ldstr    aServerSideSync_23// "Server-Side Synchronization (Outgoing):"...
0xd1e  ldstr    aThroughputOfPr_0// "Throughput of processed outgoing mail i"...
0xd23  ldc.i4   0x10410500
0xd28  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xd2d  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xd32  pop
0xd33  ldarg.0
0xd34  ldstr    aServerSideSync_24// "Server-Side Synchronization (Outgoing):"...
0xd39  ldstr    aTotalNumberOfO_0// "Total number of outgoing mail items del"...
0xd3e  ldc.i4   0x10100
0xd43  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xd48  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xd4d  pop
0xd4e  ldarg.0
0xd4f  ldstr    aServerSideSync_25// "Server-Side Synchronization (Outgoing):"...
0xd54  ldstr    aThroughputOfDe_0// "Throughput of delivered outgoing mail i"...
0xd59  ldc.i4   0x10410500
0xd5e  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xd63  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xd68  pop
0xd69  ldarg.0
0xd6a  ldstr    aServerSideSync_26// "Server-Side Synchronization (Outgoing):"...
0xd6f  ldstr    aTotalNumberOfO_1// "Total number of outgoing mail items fai"...
0xd74  ldc.i4   0x10100
0xd79  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xd7e  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xd83  pop
0xd84  ldarg.0
0xd85  ldstr    aServerSideSync_27// "Server-Side Synchronization (Outgoing):"...
0xd8a  ldstr    aThroughputOfFa_0// "Throughput of failed outgoing mail item"...
0xd8f  ldc.i4   0x10410500
0xd94  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xd99  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xd9e  pop
0xd9f  ldarg.0
0xda0  ldstr    aServerSideSync_28// "Server-Side Synchronization (Outgoing):"...
0xda5  ldstr    aTotalNumberOfT_1// "Total number of transient errors in out"...
0xdaa  ldc.i4   0x10100
0xdaf  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xdb4  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xdb9  pop
0xdba  ldarg.0
0xdbb  ldstr    aServerSideSync_29// "Server-Side Synchronization (Outgoing):"...
0xdc0  ldstr    aThroughputOfTr_0// "Throughput of transient errors in outgo"...
0xdc5  ldc.i4   0x10410500
0xdca  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xdcf  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xdd4  pop
0xdd5  ldarg.0
0xdd6  ldstr    aServerSideSync_30// "Server-Side Synchronization (Outgoing):"...
0xddb  ldstr    aThroughputOfBy_3// "Throughput of bytes sent in EWS request"...
0xde0  ldc.i4   0x10410500
0xde5  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xdea  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xdef  pop
0xdf0  ldarg.0
0xdf1  ldstr    aServerSideSync_31// "Server-Side Synchronization (Outgoing):"...
0xdf6  ldstr    aThroughputOfBy_4// "Throughput of bytes received in EWS res"...
0xdfb  ldc.i4   0x10410500
0xe00  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xe05  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xe0a  pop
0xe0b  ldarg.0
0xe0c  ldstr    aServerSideSync_32// "Server-Side Synchronization (Outgoing):"...
0xe11  ldstr    aCurrentNumberO_1// "Current number of EWS connections being"...
0xe16  ldc.i4   0x10000
0xe1b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xe20  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xe25  pop
0xe26  ldarg.0
0xe27  ldstr    aServerSideSync_33// "Server-Side Synchronization (Outgoing):"...
0xe2c  ldstr    aAverageDuratio_3// "Average duration of an EWS connection f"...
0xe31  ldc.i4   0x30020400
0xe36  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xe3b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xe40  pop
0xe41  ldarg.0
0xe42  ldstr    aServerSideSync_34// "Server-Side Synchronization (Outgoing):"...
0xe47  ldstr    aAverageDuratio_4// "Average duration of an EWS connection f"...
0xe4c  ldc.i4   0x40030402
0xe51  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xe56  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xe5b  pop
0xe5c  ldarg.0
0xe5d  ldstr    aServerSideSync_35// "Server-Side Synchronization (Outgoing):"...
0xe62  ldstr    aApproximateThr// "Approximate throughput of bytes sent vi"...
0xe67  ldc.i4   0x10410500
0xe6c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xe71  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xe76  pop
0xe77  ldarg.0
0xe78  ldstr    aServerSideSync_36// "Server-Side Synchronization (Outgoing):"...
0xe7d  ldstr    aCurrentNumberO_2// "Current number of SMTP connections bein"...
0xe82  ldc.i4   0x10000
0xe87  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xe8c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xe91  pop
0xe92  ldarg.0
0xe93  ldstr    aServerSideSync_37// "Server-Side Synchronization (Outgoing):"...
0xe98  ldstr    aAverageDuratio_5// "Average duration of an SMTP connection"
0xe9d  ldc.i4   0x30020400
0xea2  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xea7  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xeac  pop
0xead  ldarg.0
0xeae  ldstr    aServerSideSync_38// "Server-Side Synchronization (Outgoing):"...
0xeb3  ldstr    aAverageDuratio_6// "Average duration of an SMTP connection "...
0xeb8  ldc.i4   0x40030402
0xebd  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xec2  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xec7  pop
0xec8  ldarg.0
0xec9  ldstr    aServerSideSync_39// "Server-Side Synchronization (Exchange A"...
0xece  ldstr    aTotalNumberOfA// "Total number of auto discover requests "...
0xed3  ldc.i4   0x10100
0xed8  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xedd  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xee2  pop
0xee3  ldarg.0
0xee4  ldstr    aServerSideSync_40// "Server-Side Synchronization (Exchange A"...
0xee9  ldstr    aTotalNumberOfA_0// "Total number of auto discover requests "...
0xeee  ldc.i4   0x10100
0xef3  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xef8  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0xefd  pop
0xefe  ldarg.0
0xeff  ldstr    aServerSideSync_41// "Server-Side Synchronization (Exchange A"...
0xf04  ldstr    aTotalNumberOfA_1// "Total number of auto discover calls tha"...
0xf09  ldc.i4   0x10100
0xf0e  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0xf13  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
  ... truncated ...
```
