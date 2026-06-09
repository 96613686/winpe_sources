# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCountersForInstall

- ea: `0x1e90`
- end: `0x1faa`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::AddCountersForInstall`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x850`

## callees

- `0x1fd0`
- `0x160e0`

## string_xrefs

- `0x1ee4`: `Threads in use`
- `0x1f47`: `Number of dequeue attempts`
- `0x1eef`: `The number of threads currently employed in the processing of asynchronous operations.`
- `0x1f52`: `The number of dequeue attempts across all organizations for the current time-slice.`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.0
0x1e91  ldstr    aTotal// "Total"
0x1e96  ldarg.1
0x1e97  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1e9c  call     void AsyncOperationPerformanceCounters::PopulateCollection(class [System]System.Diagnostics.CounterCreationDataCollection collection, string operationName)
0x1ea1  ldarg.0
0x1ea2  ldstr    aItemsInMemoryL// "Items in memory (Low)"
0x1ea7  ldarg.1
0x1ea8  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1ead  ldstr    aTheThresholdOf// "The threshold of asynchronous operation"...
0x1eb2  ldc.i4   0x10100
0x1eb7  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1ebc  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1ec1  pop
0x1ec2  ldarg.0
0x1ec3  ldstr    aItemsInMemoryH// "Items in memory (High)"
0x1ec8  ldarg.1
0x1ec9  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1ece  ldstr    aTheMaximumNumb// "The maximum number of asynchronous oper"...
0x1ed3  ldc.i4   0x10100
0x1ed8  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1edd  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1ee2  pop
0x1ee3  ldarg.0
0x1ee4  ldstr    aThreadsInUse// "Threads in use"
0x1ee9  ldarg.1
0x1eea  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1eef  ldstr    aTheNumberOfThr// "The number of threads currently employe"...
0x1ef4  ldc.i4   0x10100
0x1ef9  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1efe  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1f03  pop
0x1f04  ldarg.0
0x1f05  ldstr    aCapacityPerOrg// "Capacity per organization"
0x1f0a  ldarg.1
0x1f0b  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1f10  ldstr    aTheNumberOfAsy// "The number of asynchronous operations t"...
0x1f15  ldc.i4   0x10100
0x1f1a  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1f1f  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1f24  pop
0x1f25  ldarg.0
0x1f26  ldstr    aItemsDequeuedP// "Items dequeued per organization"
0x1f2b  ldarg.1
0x1f2c  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1f31  ldstr    aTheNumberOfAsy_0// "The number of asynchronous operations a"...
0x1f36  ldc.i4   0x10100
0x1f3b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1f40  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1f45  pop
0x1f46  ldarg.0
0x1f47  ldstr    aNumberOfDequeu// "Number of dequeue attempts"
0x1f4c  ldarg.1
0x1f4d  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1f52  ldstr    aTheNumberOfDeq// "The number of dequeue attempts across a"...
0x1f57  ldc.i4   0x400500
0x1f5c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1f61  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1f66  pop
0x1f67  ldarg.0
0x1f68  ldstr    aTotalOrganizat// "Total Organizations"
0x1f6d  ldarg.1
0x1f6e  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1f73  ldstr    aTheNumberOfOrg// "The number of organizations being monit"...
0x1f78  ldc.i4   0x10100
0x1f7d  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1f82  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1f87  pop
0x1f88  ldarg.0
0x1f89  ldstr    aActiveOrganiza// "Active Organizations"
0x1f8e  ldarg.1
0x1f8f  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1f94  ldstr    aTheNumberOfOrg_0// "The number of organizations being activ"...
0x1f99  ldc.i4   0x10100
0x1f9e  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1fa3  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1fa8  pop
0x1fa9  ret
```
