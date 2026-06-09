# Microsoft.Crm.Asynchronous.SynchronousQueueManager`1::CreateQueueManagementOperationForAllOrganization

- ea: `0x10450`
- end: `0x10542`
- name: `Microsoft.Crm.Asynchronous.SynchronousQueueManager`1::CreateQueueManagementOperationForAllOrganization`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x2790`
- `0x27f0`
- `0xb370`
- `0xd200`
- `0xe4d0`
- `0x10450`
- `0x13690`
- `0x156e0`
- `0x15710`
- `0x157c0`

## string_xrefs

- `0x10537`: `Composite operation should implement IServiceOperation`

## pseudocode

```c

```

## disassembly

```asm
0x10450  newobj   instance void class <>c__DisplayClass5_0<var<u1>>::.ctor()
0x10455  stloc.0
0x10456  ldloc.0
0x10457  ldarg.0
0x10458  stfld    class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<var<u1>> class <>c__DisplayClass5_0<var<u1>>::<>4__this
0x1045d  ldloc.0
0x1045e  ldarg.2
0x1045f  stfld    class OrganizationQueueDataAccessHandler<var<u1>> class <>c__DisplayClass5_0<var<u1>>::handler
0x10464  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::.ctor()
0x10469  stloc.1
0x1046a  ldarg.0
0x1046b  call     instance class Microsoft.Crm.Asynchronous.IQueueConfiguration Microsoft.Crm.Asynchronous.QueueManager::get_Configuration()
0x10470  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x10475  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Values()
0x1047a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0x1047f  stloc.3
0x10480  br.s     loc_104D3
0x10482  ldloc.3
0x10483  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0x10488  stloc.s  4
0x1048a  ldarg.0
0x1048b  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x10490  ldarg.0
0x10491  call     instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x10496  ldstr    aOrganizationOp// "Organization Operation: "
0x1049b  ldarg.1
0x1049c  call     string [mscorlib]System.String::Concat(string, string)
0x104a1  ldloc.0
0x104a2  ldfld    class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction class <>c__DisplayClass5_0<var<u1>>::<>9__0
0x104a7  dup
0x104a8  brtrue.s loc_104C2
0x104aa  pop
0x104ab  ldloc.0
0x104ac  ldloc.0
0x104ad  ldftn    instance void class <>c__DisplayClass5_0<var<u1>>::<CreateQueueManagementOperationForAllOrganization>b__0(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation)
0x104b3  newobj   instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object object, native int method)
0x104b8  dup
0x104b9  stloc.s  6
0x104bb  stfld    class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction class <>c__DisplayClass5_0<var<u1>>::<>9__0
0x104c0  ldloc.s  6
0x104c2  ldloc.s  4
0x104c4  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string queueName, string eventName, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration)
0x104c9  stloc.s  5
0x104cb  ldloc.1
0x104cc  ldloc.s  5
0x104ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0x104d3  ldloc.3
0x104d4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x104d9  brtrue.s loc_10482
0x104db  leave.s  loc_104E7
0x104dd  ldloc.3
0x104de  brfalse.s loc_104E6
0x104e0  ldloc.3
0x104e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x104e6  endfinally
0x104e7  newobj   instance void [mscorlib]System.Threading.Tasks.ParallelOptions::.ctor()
0x104ec  dup
0x104ed  ldarg.0
0x104ee  ldfld    class Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<var<u1>>::_config
0x104f3  callvirt instance int32 Microsoft.Crm.Asynchronous.ISynchronousQueueConfiguration::get_SelectParallelism()
0x104f8  callvirt instance void [mscorlib]System.Threading.Tasks.ParallelOptions::set_MaxDegreeOfParallelism(int32)
0x104fd  dup
0x104fe  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x10503  callvirt instance void [mscorlib]System.Threading.Tasks.ParallelOptions::set_CancellationToken(valuetype [mscorlib]System.Threading.CancellationToken)
0x10508  stloc.2
0x10509  ldarg.3
0x1050a  brtrue.s loc_10520
0x1050c  ldarg.0
0x1050d  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x10512  ldarg.1
0x10513  ldloc.1
0x10514  newobj   instance void Microsoft.Crm.Asynchronous.SequentialExecutionEngine::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation> steps)
0x10519  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateCompositeOperation(string name, class Microsoft.Crm.Asynchronous.ICancellableEngine executionEngine)
0x1051e  br.s     loc_10533
0x10520  ldarg.0
0x10521  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x10526  ldarg.1
0x10527  ldloc.2
0x10528  ldloc.1
0x10529  newobj   instance void Microsoft.Crm.Asynchronous.ParallelTasksExecutionEngine::.ctor(class [mscorlib]System.Threading.Tasks.ParallelOptions options, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.Operations.IServiceOperation> operations)
0x1052e  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateCompositeOperation(string name, class Microsoft.Crm.Asynchronous.ICancellableEngine executionEngine)
0x10533  dup
0x10534  ldnull
0x10535  cgt.un
0x10537  ldstr    aCompositeOpera_0// "Composite operation should implement IS"...
0x1053c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x10541  ret
```
