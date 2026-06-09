# Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateOnMoveSuspendedToReadyTimerOperation

- ea: `0x4a80`
- end: `0x4aa4`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateOnMoveSuspendedToReadyTimerOperation`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4a00`

## callees

- `0x2790`
- `0x27f0`
- `0x156e0`
- `0x157c0`

## string_xrefs

- `0x4a8c`: `Move to Ready`

## pseudocode

```c

```

## disassembly

```asm
0x4a80  ldarg.0
0x4a81  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4a86  ldarg.0
0x4a87  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4a8c  ldstr    aMoveToReady// "Move to Ready"
0x4a91  ldarg.0
0x4a92  ldftn    instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::<CreateOnMoveSuspendedToReadyTimerOperation>b__4_0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4a98  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4a9d  ldnull
0x4a9e  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4aa3  ret
```
