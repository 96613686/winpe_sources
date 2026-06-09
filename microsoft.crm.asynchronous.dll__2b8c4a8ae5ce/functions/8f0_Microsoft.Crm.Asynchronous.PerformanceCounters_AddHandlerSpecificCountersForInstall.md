# Microsoft.Crm.Asynchronous.PerformanceCounters::AddHandlerSpecificCountersForInstall

- ea: `0x8f0`
- end: `0x9a5`
- name: `Microsoft.Crm.Asynchronous.PerformanceCounters::AddHandlerSpecificCountersForInstall`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x850`

## callees

- `0x9b0`
- `0xa90`
- `0xf90`

## string_xrefs

- `0x978`: `Total Workflow state writes`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldarg.0
0x8f1  ldstr    aParsingProcess// "Parsing processing Rate (Throughput)"
0x8f6  ldstr    aNumberOfRecord// "Number of records parsed per second"
0x8fb  ldc.i4   0x10410500
0x900  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x905  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x90a  pop
0x90b  ldarg.0
0x90c  ldstr    aTransformProce// "Transform processing Rate (Throughput)"
0x911  ldstr    aNumberOfRecord_0// "Number of records transformed per secon"...
0x916  ldc.i4   0x10410500
0x91b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x920  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x925  pop
0x926  ldarg.0
0x927  ldstr    aImportProcessi// "Import processing Rate (Throughput)"
0x92c  ldstr    aNumberOfRecord_1// "Number of records imported per second"
0x931  ldc.i4   0x10410500
0x936  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x93b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x940  pop
0x941  ldarg.0
0x942  ldstr    aRulePublishPro// "Rule publish Processing Rate (Throughpu"...
0x947  ldstr    aNumberOfRecord_2// "Number of records published per second"
0x94c  ldc.i4   0x10410500
0x951  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x956  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x95b  pop
0x95c  ldarg.0
0x95d  ldstr    aBulkDetectDupl// "Bulk Detect Duplicate Rate (Throughput)"
0x962  ldstr    aNumberOfRecord_3// "Number of records processed for duplica"...
0x967  ldc.i4   0x10410500
0x96c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x971  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x976  pop
0x977  ldarg.0
0x978  ldstr    aTotalWorkflowS// "Total Workflow state writes"
0x97d  ldstr    aTheNumberOfTim// "The number of times workflow state save"...
0x982  ldc.i4   0x10100
0x987  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x98c  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x991  pop
0x992  ldarg.0
0x993  call     void Microsoft.Crm.Asynchronous.PerformanceCounters::AddRollupCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection)
0x998  ldarg.0
0x999  call     void Microsoft.Crm.Asynchronous.PerformanceCounters::AddEmailConnectorCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection)
0x99e  ldarg.0
0x99f  call     void Microsoft.Crm.Asynchronous.PerformanceCounters::AddExchangeSyncCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection)
0x9a4  ret
```
