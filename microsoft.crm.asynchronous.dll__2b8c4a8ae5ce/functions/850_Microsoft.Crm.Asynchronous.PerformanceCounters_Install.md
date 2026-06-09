# Microsoft.Crm.Asynchronous.PerformanceCounters::Install

- ea: `0x850`
- end: `0x8bc`
- name: `Microsoft.Crm.Asynchronous.PerformanceCounters::Install`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x850`
- `0x8c0`
- `0x8f0`
- `0x1e90`
- `0x1fb0`

## string_xrefs

- `0x897`: `Microsoft CRM Asynchronous Service`

## pseudocode

```c

```

## disassembly

```asm
0x850  call     void Microsoft.Crm.Asynchronous.PerformanceCounters::Uninstall()
0x855  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x85a  stloc.0
0x85b  ldloc.0
0x85c  ldtoken  [Microsoft.Crm.Constants]Microsoft.Crm.AsyncOperationType
0x861  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x866  call     void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCommonCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection, class [mscorlib]System.Type operationTypesType)
0x86b  ldloc.0
0x86c  ldstr    aActivityqueue// "ActivityQueue"
0x871  call     void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection, string queueName)
0x876  ldloc.0
0x877  ldstr    aAsyncoperation// "AsyncOperationQueue"
0x87c  call     void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection, string queueName)
0x881  ldloc.0
0x882  ldstr    aMailboxqueue// "MailboxQueue"
0x887  call     void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection, string queueName)
0x88c  ldloc.0
0x88d  call     void Microsoft.Crm.Asynchronous.PerformanceCounters::AddHandlerSpecificCountersForInstall(class [System]System.Diagnostics.CounterCreationDataCollection collection)
0x892  ldsfld   string Microsoft.Crm.Asynchronous.PerformanceCounters::AsyncServiceCategoryName
0x897  ldstr    aMicrosoftCrmAs// "Microsoft CRM Asynchronous Service"
0x89c  ldc.i4.1
0x89d  ldloc.0
0x89e  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x8a3  pop
0x8a4  ldstr    aOutlooksync// "OutlookSync"
0x8a9  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x8ae  brtrue.s loc_8BB
0x8b0  ldc.i4.0
0x8b1  ldstr    aOutlooksync// "OutlookSync"
0x8b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::LoadCounters(valuetype [Microsoft.Crm.Core]Microsoft.Crm.PerformanceCounterLoadSetting, string)
0x8bb  ret
```
