# Microsoft.Crm.Asynchronous.QueuePerformanceCounters::.ctor_0

- ea: `0x1ac0`
- end: `0x1ba0`
- name: `Microsoft.Crm.Asynchronous.QueuePerformanceCounters::.ctor_0`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1aa0`

## callees

- `0x800`
- `0x1fd0`
- `0x2070`
- `0x2090`

## string_xrefs

- `0x1b11`: `Threads in use`
- `0x1b59`: `Number of dequeue attempts`

## pseudocode

```c

```

## disassembly

```asm
0x1ac0  ldarg.0
0x1ac1  call     instance void [mscorlib]System.Object::.ctor()
0x1ac6  ldarg.0
0x1ac7  ldarg.s  4
0x1ac9  stfld    class [mscorlib]System.Type Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_supportedOperationTypesType
0x1ace  ldarg.0
0x1acf  ldarg.2
0x1ad0  ldarg.1
0x1ad1  ldarg.3
0x1ad2  call     instance void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::InitializeTotalCounters(string instanceName, string queueName, class Microsoft.Crm.Asynchronous.PerformanceCounters counters)
0x1ad7  ldarg.0
0x1ad8  ldarg.2
0x1ad9  ldarg.3
0x1ada  call     instance void Microsoft.Crm.Asynchronous.QueuePerformanceCounters::InitializeOperationTypeCounters(string instanceName, class Microsoft.Crm.Asynchronous.PerformanceCounters counters)
0x1adf  ldarg.0
0x1ae0  ldarg.3
0x1ae1  ldstr    aItemsInMemoryL// "Items in memory (Low)"
0x1ae6  ldarg.1
0x1ae7  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1aec  ldarg.2
0x1aed  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1af2  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_itemsInMemoryLow
0x1af7  ldarg.0
0x1af8  ldarg.3
0x1af9  ldstr    aItemsInMemoryH// "Items in memory (High)"
0x1afe  ldarg.1
0x1aff  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b04  ldarg.2
0x1b05  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b0a  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_itemsInMemoryHigh
0x1b0f  ldarg.0
0x1b10  ldarg.3
0x1b11  ldstr    aThreadsInUse// "Threads in use"
0x1b16  ldarg.1
0x1b17  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b1c  ldarg.2
0x1b1d  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b22  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_threadsInUse
0x1b27  ldarg.0
0x1b28  ldarg.3
0x1b29  ldstr    aCapacityPerOrg// "Capacity per organization"
0x1b2e  ldarg.1
0x1b2f  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b34  ldarg.2
0x1b35  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b3a  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_capacityPerOrganization
0x1b3f  ldarg.0
0x1b40  ldarg.3
0x1b41  ldstr    aItemsDequeuedP// "Items dequeued per organization"
0x1b46  ldarg.1
0x1b47  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b4c  ldarg.2
0x1b4d  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b52  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_itemsDequeuedPerOrganization
0x1b57  ldarg.0
0x1b58  ldarg.3
0x1b59  ldstr    aNumberOfDequeu// "Number of dequeue attempts"
0x1b5e  ldarg.1
0x1b5f  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b64  ldarg.2
0x1b65  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b6a  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_dequeueAttempts
0x1b6f  ldarg.0
0x1b70  ldarg.3
0x1b71  ldstr    aTotalOrganizat// "Total Organizations"
0x1b76  ldarg.1
0x1b77  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b7c  ldarg.2
0x1b7d  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b82  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_totalOrganizations
0x1b87  ldarg.0
0x1b88  ldarg.3
0x1b89  ldstr    aActiveOrganiza// "Active Organizations"
0x1b8e  ldarg.1
0x1b8f  call     string Microsoft.Crm.Asynchronous.QueuePerformanceCounters::GetQueueCounterName(string counterName, string queueName)
0x1b94  ldarg.2
0x1b95  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.PerformanceCounters::InitializeCounter(string counterName, string instanceName)
0x1b9a  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.Asynchronous.QueuePerformanceCounters::_activeOrganizations
0x1b9f  ret
```
