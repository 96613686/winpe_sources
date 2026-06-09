# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOperationToExecuteAllOutstandingDatabaseOperations

- ea: `0x4eb0`
- end: `0x4fb2`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOperationToExecuteAllOutstandingDatabaseOperations`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4ff0`
- `0x5590`

## callees

- `0x2790`
- `0x27f0`
- `0x45b0`
- `0x4eb0`
- `0x5000`
- `0xe4d0`
- `0x156e0`
- `0x15710`
- `0x157c0`
- `0x17490`
- `0x174f0`

## string_xrefs

- `0x4f01`: `State and Status Update`
- `0x4f41`: `Execute Queued Database Commands`
- `0x4fa7`: `Composite operations should allow cacellation`

## pseudocode

```c

```

## disassembly

```asm
0x4eb0  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x4eb5  stloc.0
0x4eb6  ldloc.0
0x4eb7  ldarg.0
0x4eb8  stfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase <>c__DisplayClass22_0::<>4__this
0x4ebd  ldloc.0
0x4ebe  ldarg.1
0x4ebf  stfld    bool <>c__DisplayClass22_0::isShuttingDown
0x4ec4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::.ctor()
0x4ec9  stloc.1
0x4eca  ldnull
0x4ecb  stloc.2
0x4ecc  ldloc.0
0x4ecd  newobj   instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::.ctor()
0x4ed2  stfld    class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> <>c__DisplayClass22_0::retryQueue
0x4ed7  ldloc.0
0x4ed8  ldc.i4.0
0x4ed9  stfld    valuetype CommandResult <>c__DisplayClass22_0::result
0x4ede  br.s     loc_4F22
0x4ee0  newobj   instance void <>c__DisplayClass22_1::.ctor()
0x4ee5  stloc.3
0x4ee6  ldloc.3
0x4ee7  ldloc.0
0x4ee8  stfld    class <>c__DisplayClass22_0 <>c__DisplayClass22_1::CS$<>8__locals1
0x4eed  ldloc.3
0x4eee  ldloc.2
0x4eef  stfld    class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand <>c__DisplayClass22_1::currentCommand
0x4ef4  ldloc.1
0x4ef5  ldarg.0
0x4ef6  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4efb  ldarg.0
0x4efc  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4f01  ldstr    aStateAndStatus// "State and Status Update"
0x4f06  ldloc.3
0x4f07  ldftn    instance void <>c__DisplayClass22_1::<CreateOperationToExecuteAllOutstandingDatabaseOperations>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation serviceOperation)
0x4f0d  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4f12  ldloc.2
0x4f13  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x4f18  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4f1d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0x4f22  ldarg.0
0x4f23  call     instance class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::DequeueDatabaseCommand()
0x4f28  dup
0x4f29  stloc.2
0x4f2a  brtrue.s loc_4EE0
0x4f2c  ldloc.0
0x4f2d  ldfld    bool <>c__DisplayClass22_0::isShuttingDown
0x4f32  brtrue.s loc_4F5F
0x4f34  ldloc.1
0x4f35  ldarg.0
0x4f36  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4f3b  ldarg.0
0x4f3c  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4f41  ldstr    aExecuteQueuedD// "Execute Queued Database Commands"
0x4f46  ldloc.0
0x4f47  ldftn    instance void <>c__DisplayClass22_0::<CreateOperationToExecuteAllOutstandingDatabaseOperations>b__1(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation serviceOperation)
0x4f4d  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4f52  ldnull
0x4f53  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4f58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0x4f5d  br.s     loc_4F88
0x4f5f  ldloc.1
0x4f60  ldarg.0
0x4f61  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4f66  ldarg.0
0x4f67  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x4f6c  ldstr    aAssertion// "Assertion"
0x4f71  ldloc.0
0x4f72  ldftn    instance void <>c__DisplayClass22_0::<CreateOperationToExecuteAllOutstandingDatabaseOperations>b__2(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x4f78  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x4f7d  ldnull
0x4f7e  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x4f83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0x4f88  ldarg.0
0x4f89  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x4f8e  ldstr    aExecuteAllOuts// "Execute all outstanding database operat"...
0x4f93  ldloc.1
0x4f94  newobj   instance void Microsoft.Crm.Asynchronous.SequentialExecutionEngine::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation> steps)
0x4f99  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateCompositeOperation(string name, class Microsoft.Crm.Asynchronous.ICancellableEngine executionEngine)
0x4f9e  isinst   Microsoft.Crm.Asynchronous.Operations.CompositeOperation
0x4fa3  dup
0x4fa4  ldnull
0x4fa5  cgt.un
0x4fa7  ldstr    aCompositeOpera// "Composite operations should allow cacel"...
0x4fac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x4fb1  ret
```
