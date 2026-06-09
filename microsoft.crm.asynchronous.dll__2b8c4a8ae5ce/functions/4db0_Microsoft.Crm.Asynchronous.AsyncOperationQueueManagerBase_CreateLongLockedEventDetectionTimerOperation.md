# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateLongLockedEventDetectionTimerOperation

- ea: `0x4db0`
- end: `0x4de8`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateLongLockedEventDetectionTimerOperation`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4d70`

## callees

- `0x2790`
- `0x27f0`
- `0x156e0`
- `0x157c0`
- `0x17430`

## pseudocode

```c

```

## disassembly

```asm
0x4db0  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x4db5  stloc.0
0x4db6  ldloc.0
0x4db7  ldarg.0
0x4db8  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase <>c__DisplayClass19_0::<>4__this
0x4dbd  ldloc.0
0x4dbe  ldc.i4.1
0x4dbf  stfld    bool <>c__DisplayClass19_0::useParallelExecution
0x4dc4  ldarg.0
0x4dc5  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4dca  ldarg.0
0x4dcb  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4dd0  ldstr    aLongLockedEven// "Long Locked Event Detection"
0x4dd5  ldloc.0
0x4dd6  ldftn    instance void <>c__DisplayClass19_0::<CreateLongLockedEventDetectionTimerOperation>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4ddc  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4de1  ldnull
0x4de2  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4de7  ret
```
