# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOnDatabaseOperationTimerOperation

- ea: `0x4cb0`
- end: `0x4cd4`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOnDatabaseOperationTimerOperation`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4c20`

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
0x4cb0  ldarg.0
0x4cb1  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4cb6  ldarg.0
0x4cb7  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4cbc  ldstr    aDatabaseOperat// "Database Operation Timer"
0x4cc1  ldarg.0
0x4cc2  ldftn    instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::<CreateOnDatabaseOperationTimerOperation>b__15_0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4cc8  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4ccd  ldnull
0x4cce  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4cd3  ret
```
