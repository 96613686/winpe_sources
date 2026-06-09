# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOnKeepAliveTimerOperation

- ea: `0x4c70`
- end: `0x4ca8`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOnKeepAliveTimerOperation`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4c20`

## callees

- `0x2790`
- `0x27f0`
- `0x156e0`
- `0x157c0`
- `0x17370`

## pseudocode

```c

```

## disassembly

```asm
0x4c70  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x4c75  stloc.0
0x4c76  ldloc.0
0x4c77  ldarg.0
0x4c78  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase <>c__DisplayClass14_0::<>4__this
0x4c7d  ldloc.0
0x4c7e  ldc.i4.1
0x4c7f  stfld    bool <>c__DisplayClass14_0::useParallelExecution
0x4c84  ldarg.0
0x4c85  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4c8a  ldarg.0
0x4c8b  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4c90  ldstr    aKeepAlive// "Keep Alive"
0x4c95  ldloc.0
0x4c96  ldftn    instance void <>c__DisplayClass14_0::<CreateOnKeepAliveTimerOperation>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4c9c  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4ca1  ldnull
0x4ca2  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4ca7  ret
```
