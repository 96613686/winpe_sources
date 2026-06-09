# Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateOnTimeoutLockedTimerOperation

- ea: `0x4ab0`
- end: `0x4ad4`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateOnTimeoutLockedTimerOperation`
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

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  ldarg.0
0x4ab1  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4ab6  ldarg.0
0x4ab7  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4abc  ldstr    aTimeoutLocked// "Timeout Locked"
0x4ac1  ldarg.0
0x4ac2  ldftn    instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::<CreateOnTimeoutLockedTimerOperation>b__5_0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4ac8  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4acd  ldnull
0x4ace  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4ad3  ret
```
