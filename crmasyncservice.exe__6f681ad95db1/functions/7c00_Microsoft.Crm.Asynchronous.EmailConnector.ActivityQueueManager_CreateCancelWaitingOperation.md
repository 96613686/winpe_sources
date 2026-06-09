# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::CreateCancelWaitingOperation

- ea: `0x7c00`
- end: `0x7c26`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::CreateCancelWaitingOperation`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7bc0`

## pseudocode

```c

```

## disassembly

```asm
0x7c00  ldarg.0
0x7c01  ldftn    instance void Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::<CreateCancelWaitingOperation>b__8_0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x7c07  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x7c0c  stloc.0
0x7c0d  ldarg.0
0x7c0e  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x7c13  ldarg.0
0x7c14  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x7c19  ldstr    aCancelWaiting// "Cancel Waiting"
0x7c1e  ldloc.0
0x7c1f  ldnull
0x7c20  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x7c25  ret
```
