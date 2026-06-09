# Microsoft.Crm.Asynchronous.QueueManager::CreateSelectTimerOperation

- ea: `0x9de0`
- end: `0x9e06`
- name: `Microsoft.Crm.Asynchronous.QueueManager::CreateSelectTimerOperation`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x9d30`
- `0xec00`

## callees

- `0x2790`
- `0x27f0`
- `0x156e0`
- `0x157c0`

## pseudocode

```c

```

## disassembly

```asm
0x9de0  ldarg.0
0x9de1  ldftn    instance void Microsoft.Crm.Asynchronous.QueueManager::<CreateSelectTimerOperation>b__4_0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x9de7  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x9dec  stloc.0
0x9ded  ldarg.0
0x9dee  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x9df3  ldarg.0
0x9df4  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x9df9  ldstr    aSelect// "Select"
0x9dfe  ldloc.0
0x9dff  ldnull
0x9e00  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x9e05  ret
```
