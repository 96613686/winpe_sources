# Microsoft.Crm.Asynchronous.QueueManager::CreateSemaphoreDiagnosticTimerOperation

- ea: `0x9e10`
- end: `0x9e36`
- name: `Microsoft.Crm.Asynchronous.QueueManager::CreateSemaphoreDiagnosticTimerOperation`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x9d70`

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
0x9e10  ldarg.0
0x9e11  ldftn    instance void Microsoft.Crm.Asynchronous.QueueManager::<CreateSemaphoreDiagnosticTimerOperation>b__5_0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x9e17  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x9e1c  stloc.0
0x9e1d  ldarg.0
0x9e1e  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x9e23  ldarg.0
0x9e24  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x9e29  ldstr    aSemaphorediagn// "SemaphoreDiagnostic"
0x9e2e  ldloc.0
0x9e2f  ldnull
0x9e30  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x9e35  ret
```
