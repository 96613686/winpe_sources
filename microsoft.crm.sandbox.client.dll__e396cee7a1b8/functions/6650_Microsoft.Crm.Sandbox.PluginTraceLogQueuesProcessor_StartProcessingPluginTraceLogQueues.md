# Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::StartProcessingPluginTraceLogQueues

- ea: `0x6650`
- end: `0x6793`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::StartProcessingPluginTraceLogQueues`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1930`

## callees

- `0x6650`
- `0x9360`

## string_xrefs

- `0x6668`: `MaxThreadCountToDequeuePluginTraceLog`
- `0x6675`: `PluginTraceLogMaxTimeInSecondsToDequeue`
- `0x668c`: `StartProcessingPluginTraceLogQueues: Inside WritePluginTraceLog`
- `0x6740`: `StartProcessingPluginTraceLogQueues: Unhandled exception occurred when executing parallel operations - {0}`
- `0x675e`: `StartProcessingPluginTraceLogQueues: The parallel execution of WritePluginTraceLogRecords operations has been cancelled - {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6650  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x6655  stloc.0
0x6656  ldloc.0
0x6657  ldarg.0
0x6658  stfld    class Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor <>c__DisplayClass1_0::<>4__this
0x665d  ldloc.0
0x665e  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x6663  stfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass1_0::cts
0x6668  ldstr    aMaxthreadcount// "MaxThreadCountToDequeuePluginTraceLog"
0x666d  ldc.i4.s 0xA
0x666f  call     T0x2B000002
0x6674  stloc.1
0x6675  ldstr    aPlugintracelog_8// "PluginTraceLogMaxTimeInSecondsToDequeue"
0x667a  ldc.i4   0x12C
0x667f  call     T0x2B000002
0x6684  stloc.2
0x6685  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x668a  ldc.i4.s 0x21
0x668c  ldstr    aStartprocessin// "StartProcessingPluginTraceLogQueues: In"...
0x6691  ldc.i4.0
0x6692  newarr   [mscorlib]System.Object
0x6697  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x669c  ldloc.1
0x669d  newarr   [mscorlib]System.Threading.Tasks.Task
0x66a2  stloc.3
0x66a3  ldc.i4.0
0x66a4  stloc.s  4
0x66a6  br.s     loc_66EE
0x66a8  ldloc.3
0x66a9  ldloc.s  4
0x66ab  call     class [mscorlib]System.Threading.Tasks.TaskFactory [mscorlib]System.Threading.Tasks.Task::get_Factory()
0x66b0  ldloc.0
0x66b1  ldfld    class [mscorlib]System.Action <>c__DisplayClass1_0::<>9__0
0x66b6  dup
0x66b7  brtrue.s loc_66D1
0x66b9  pop
0x66ba  ldloc.0
0x66bb  ldloc.0
0x66bc  ldftn    instance void <>c__DisplayClass1_0::<StartProcessingPluginTraceLogQueues>b__0()
0x66c2  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x66c7  dup
0x66c8  stloc.s  5
0x66ca  stfld    class [mscorlib]System.Action <>c__DisplayClass1_0::<>9__0
0x66cf  ldloc.s  5
0x66d1  ldloc.0
0x66d2  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass1_0::cts
0x66d7  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x66dc  ldc.i4.1
0x66dd  call     class [mscorlib]System.Threading.Tasks.TaskScheduler [mscorlib]System.Threading.Tasks.TaskScheduler::get_Default()
0x66e2  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.TaskFactory::StartNew(class [mscorlib]System.Action, valuetype [mscorlib]System.Threading.CancellationToken, valuetype [mscorlib]System.Threading.Tasks.TaskCreationOptions, class [mscorlib]System.Threading.Tasks.TaskScheduler)
0x66e7  stelem.ref
0x66e8  ldloc.s  4
0x66ea  ldc.i4.1
0x66eb  add
0x66ec  stloc.s  4
0x66ee  ldloc.s  4
0x66f0  ldloc.1
0x66f1  blt.s    loc_66A8
0x66f3  ldloc.3
0x66f4  ldloc.2
0x66f5  ldc.i4   0x3E8
0x66fa  mul
0x66fb  call     bool [mscorlib]System.Threading.Tasks.Task::WaitAll(class [mscorlib]System.Threading.Tasks.Task[], int32)
0x6700  brtrue.s loc_670E
0x6702  ldloc.0
0x6703  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass1_0::cts
0x6708  ldc.i4.0
0x6709  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel(bool)
0x670e  leave.s  loc_678C
0x6710  pop
0x6711  leave.s  loc_678C
0x6713  stloc.s  6
0x6715  ldloc.s  6
0x6717  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0x671c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::GetEnumerator()
0x6721  stloc.s  7
0x6723  br.s     loc_6773
0x6725  ldloc.s  7
0x6727  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Exception>::get_Current()
0x672c  stloc.s  8
0x672e  ldloc.s  8
0x6730  isinst   [mscorlib]System.OperationCanceledException
0x6735  brtrue.s loc_6757
0x6737  ldloc.s  6
0x6739  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x673e  ldc.i4.s 0x14
0x6740  ldstr    aStartprocessin_0// "StartProcessingPluginTraceLogQueues: Un"...
0x6745  ldc.i4.1
0x6746  newarr   [mscorlib]System.Object
0x674b  dup
0x674c  ldc.i4.0
0x674d  ldloc.s  8
0x674f  stelem.ref
0x6750  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6755  rethrow
0x6757  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x675c  ldc.i4.s 0x14
0x675e  ldstr    aStartprocessin_1// "StartProcessingPluginTraceLogQueues: Th"...
0x6763  ldc.i4.1
0x6764  newarr   [mscorlib]System.Object
0x6769  dup
0x676a  ldc.i4.0
0x676b  ldloc.s  8
0x676d  stelem.ref
0x676e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6773  ldloc.s  7
0x6775  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x677a  brtrue.s loc_6725
0x677c  leave.s  loc_678A
0x677e  ldloc.s  7
0x6780  brfalse.s loc_6789
0x6782  ldloc.s  7
0x6784  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6789  endfinally
0x678a  leave.s  loc_678C
0x678c  ldloc.0
0x678d  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass1_0::cts
0x6792  ret
```
