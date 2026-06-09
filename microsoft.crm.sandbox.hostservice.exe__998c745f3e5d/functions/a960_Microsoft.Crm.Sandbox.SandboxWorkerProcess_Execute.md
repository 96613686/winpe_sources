# Microsoft.Crm.Sandbox.SandboxWorkerProcess::Execute

- ea: `0xa960`
- end: `0xad73`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::Execute`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0xba70`

## callees

- `0xa810`
- `0xa920`
- `0xa960`
- `0xad80`
- `0xae00`
- `0xaf80`
- `0xd130`
- `0xd2b0`

## string_xrefs

- `0xaae5`: `SandboxWorkerProcess.Execute.TimeToStartTask`

## pseudocode

```c

```

## disassembly

```asm
0xa960  newobj   instance void <>c__DisplayClass72_1::.ctor()
0xa965  stloc.0
0xa966  ldloc.0
0xa967  ldarg.2
0xa968  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xa96d  ldloc.0
0xa96e  ldarg.3
0xa96f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginAssemblyId
0xa974  ldloc.0
0xa975  ldarg.s  4
0xa977  stfld    int32 <>c__DisplayClass72_1::sourceHash
0xa97c  ldloc.0
0xa97d  ldarg.s  5
0xa97f  stfld    string <>c__DisplayClass72_1::assemblyName
0xa984  ldloc.0
0xa985  ldarg.s  6
0xa987  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginTypeId
0xa98c  ldloc.0
0xa98d  ldarg.s  7
0xa98f  stfld    string <>c__DisplayClass72_1::pluginTypeName
0xa994  ldloc.0
0xa995  ldarg.s  8
0xa997  stfld    string <>c__DisplayClass72_1::pluginConfiguration
0xa99c  ldloc.0
0xa99d  ldarg.s  9
0xa99f  stfld    string <>c__DisplayClass72_1::pluginSecureConfig
0xa9a4  ldloc.0
0xa9a5  ldarg.s  0xA
0xa9a7  stfld    bool <>c__DisplayClass72_1::returnTraceInfo
0xa9ac  ldloc.0
0xa9ad  ldnull
0xa9ae  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::returnedContext
0xa9b3  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xa9b8  stloc.1
0xa9b9  ldstr    aSandboxworkerp_35// "SandboxWorkerProcess.Execute.Initialize"
0xa9be  ldc.i4.3
0xa9bf  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xa9c4  stloc.s  6
0xa9c6  ldarg.0
0xa9c7  ldarg.1
0xa9c8  ldloc.0
0xa9c9  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xa9ce  ldloc.0
0xa9cf  ldfld    string <>c__DisplayClass72_1::assemblyName
0xa9d4  ldloc.0
0xa9d5  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginTypeId
0xa9da  ldloc.0
0xa9db  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xa9e0  call     instance class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient> Microsoft.Crm.Sandbox.SandboxWorkerProcess::Initialize(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, string assemblyName, valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName)
0xa9e5  stloc.2
0xa9e6  leave.s  loc_A9F4
0xa9e8  ldloc.s  6
0xa9ea  brfalse.s loc_A9F3
0xa9ec  ldloc.s  6
0xa9ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa9f3  endfinally
0xa9f4  ldloc.1
0xa9f5  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa9fa  ldarg.s  0xC
0xa9fc  ldloc.1
0xa9fd  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xaa02  stind.i8
0xaa03  ldloc.2
0xaa04  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::get_Item1()
0xaa09  stloc.3
0xaa0a  ldloc.2
0xaa0b  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::get_Item2()
0xaa10  stloc.s  4
0xaa12  ldloc.0
0xaa13  ldloc.2
0xaa14  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord, class Microsoft.Crm.Sandbox.SandboxWorkerClient>::get_Item3()
0xaa19  stfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient <>c__DisplayClass72_1::workerClient
0xaa1e  ldloc.0
0xaa1f  ldnull
0xaa20  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter <>c__DisplayClass72_1::workerCounter
0xaa25  ldloc.0
0xaa26  ldarg.1
0xaa27  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0xaa2c  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass72_1::newCallInfo
0xaa31  ldc.i4.0
0xaa32  stloc.s  5
0xaa34  ldloc.0
0xaa35  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xaa3a  stfld    class [System]System.Diagnostics.Stopwatch <>c__DisplayClass72_1::taskStartStopwatch
0xaa3f  ldloc.0
0xaa40  ldc.i4.0
0xaa41  conv.i8
0xaa42  stfld    int64 <>c__DisplayClass72_1::elapsedExecInMs
0xaa47  newobj   instance void <>c__DisplayClass72_0::.ctor()
0xaa4c  stloc.s  7
0xaa4e  ldloc.s  7
0xaa50  ldloc.0
0xaa51  stfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaa56  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xaa5b  stloc.s  8
0xaa5d  ldarg.0
0xaa5e  ldloc.3
0xaa5f  ldloc.s  7
0xaa61  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaa66  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient <>c__DisplayClass72_1::workerClient
0xaa6b  ldloc.s  4
0xaa6d  ldloc.s  7
0xaa6f  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaa74  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xaa79  ldloc.s  7
0xaa7b  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaa80  ldfld    string <>c__DisplayClass72_1::assemblyName
0xaa85  ldloc.s  7
0xaa87  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaa8c  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xaa91  ldloc.s  7
0xaa93  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaa98  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginAssemblyId
0xaa9d  ldloc.s  7
0xaa9f  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaaa4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass72_1::pluginTypeId
0xaaa9  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TrackCall(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, class Microsoft.Crm.Sandbox.SandboxWorkerClient workerClient, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord pluginExecutionRecord, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, string assemblyName, string pluginTypeName, valuetype [mscorlib]System.Guid pluginAssemblyId, valuetype [mscorlib]System.Guid pluginTypeId)
0xaaae  ldloc.s  8
0xaab0  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xaab5  ldarg.s  0xD
0xaab7  ldloc.s  8
0xaab9  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xaabe  stind.i8
0xaabf  ldarg.0
0xaac0  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_executionTimeoutInSec
0xaac5  stloc.s  9
0xaac7  ldloc.s  7
0xaac9  ldc.i4.0
0xaaca  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0xaacf  stfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass72_0::ExecuteComplete
0xaad4  ldloc.s  7
0xaad6  ldnull
0xaad7  stfld    class [mscorlib]System.Exception <>c__DisplayClass72_0::executeException
0xaadc  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0xaae1  stloc.s  0xA
0xaae3  ldloc.s  7
0xaae5  ldstr    aSandboxworkerp_36// "SandboxWorkerProcess.Execute.TimeToStar"...
0xaaea  ldc.i4.3
0xaaeb  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xaaf0  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext <>c__DisplayClass72_0::timeToStartTask
0xaaf5  ldloc.s  7
0xaaf7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_CurrentTraceSettings()
0xaafc  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings <>c__DisplayClass72_0::traceSettings
0xab01  call     class [mscorlib]System.Threading.Tasks.TaskFactory [mscorlib]System.Threading.Tasks.Task::get_Factory()
0xab06  ldloc.s  7
0xab08  ldftn    instance void <>c__DisplayClass72_0::<Execute>b__0()
0xab0e  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xab13  ldloc.s  0xA
0xab15  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0xab1a  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.TaskFactory::StartNew(class [mscorlib]System.Action, valuetype [mscorlib]System.Threading.CancellationToken)
0xab1f  pop
0xab20  ldloc.s  7
0xab22  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xab27  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xab2c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_SharedVariables()
0xab31  ldstr    aExecutetimesta// "ExecuteTimeStamp"
0xab36  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xab3b  brfalse  loc_AC42
0xab40  ldloc.s  7
0xab42  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xab47  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xab4c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_SharedVariables()
0xab51  ldstr    aExecutetimesta// "ExecuteTimeStamp"
0xab56  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xab5b  unbox.any [mscorlib]System.DateTime
0xab60  stloc.s  0xD
0xab62  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xab67  stloc.s  0xE
0xab69  ldloca.s 0xE
0xab6b  ldloc.s  0xD
0xab6d  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0xab72  stloc.s  0xF
0xab74  ldloca.s 0xF
0xab76  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0xab7b  stloc.s  5
0xab7d  ldloc.s  7
0xab7f  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xab84  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xab89  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_SharedVariables()
0xab8e  ldstr    aExecutetimesta// "ExecuteTimeStamp"
0xab93  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Remove(var<u1>)
0xab98  pop
0xab99  ldloc.s  5
0xab9b  ldc.i4.s 0xA
0xab9d  ble.s    loc_ABDB
0xab9f  ldloc.s  7
0xaba1  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xaba6  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xabab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xabb0  ldc.i4.s 0x21
0xabb2  ldstr    aSandboxworkerp_37// "SandboxWorkerProcess.Execute: {0} was i"...
0xabb7  ldc.i4.2
0xabb8  newarr   [mscorlib]System.Object
0xabbd  dup
0xabbe  ldc.i4.0
0xabbf  ldloc.s  7
0xabc1  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xabc6  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xabcb  stelem.ref
0xabcc  dup
0xabcd  ldc.i4.1
0xabce  ldloc.s  5
0xabd0  box      [mscorlib]System.Int32
0xabd5  stelem.ref
0xabd6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xabdb  ldloc.s  5
0xabdd  ldloc.s  9
0xabdf  ble.s    loc_AC42
0xabe1  ldloc.s  9
0xabe3  call     string Microsoft.Crm.Sandbox.SandboxWorkerProcess::FormatTimeoutSpan(int32 executionTimeout)
0xabe8  stloc.s  0x10
0xabea  ldnull
0xabeb  ldloc.s  7
0xabed  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xabf2  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xabf7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xabfc  ldc.i4.s 0x21
0xabfe  ldstr    aSandboxworkerp_38// "SandboxWorkerProcess.Execute: Didn’t re"...
0xac03  ldc.i4.2
0xac04  newarr   [mscorlib]System.Object
0xac09  dup
0xac0a  ldc.i4.0
0xac0b  ldloc.s  7
0xac0d  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xac12  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xac17  stelem.ref
0xac18  dup
0xac19  ldc.i4.1
0xac1a  ldloc.s  0x10
0xac1c  stelem.ref
0xac1d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xac22  ldc.i4   0x80081111
0xac27  ldc.i4.1
0xac28  newarr   [mscorlib]System.Object
0xac2d  dup
0xac2e  ldc.i4.0
0xac2f  ldloc.s  7
0xac31  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xac36  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xac3b  stelem.ref
0xac3c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xac41  throw
0xac42  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xac47  stloc.s  0xB
0xac49  ldc.i4.1
0xac4a  newarr   [mscorlib]System.Threading.WaitHandle
0xac4f  dup
0xac50  ldc.i4.0
0xac51  ldloc.s  7
0xac53  ldfld    class [mscorlib]System.Threading.AutoResetEvent <>c__DisplayClass72_0::ExecuteComplete
0xac58  stelem.ref
0xac59  ldc.i4.0
0xac5a  ldc.i4.0
0xac5b  ldloc.s  9
0xac5d  ldloc.s  5
0xac5f  sub
0xac60  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xac65  call     int32 [mscorlib]System.Threading.WaitHandle::WaitAny(class [mscorlib]System.Threading.WaitHandle[], valuetype [mscorlib]System.TimeSpan)
0xac6a  ldloc.s  0xB
0xac6c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xac71  ldarg.s  0xF
0xac73  ldloc.s  0xB
0xac75  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xac7a  stind.i8
0xac7b  ldc.i4   0x102
0xac80  bne.un.s loc_ACEA
0xac82  ldloc.s  9
0xac84  call     string Microsoft.Crm.Sandbox.SandboxWorkerProcess::FormatTimeoutSpan(int32 executionTimeout)
0xac89  stloc.s  0x11
0xac8b  ldloc.s  0xA
0xac8d  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0xac92  ldnull
0xac93  ldloc.s  7
0xac95  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xac9a  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass72_1::requestContext
0xac9f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xaca4  ldc.i4.s 0x21
0xaca6  ldstr    aSandboxworkerp_38// "SandboxWorkerProcess.Execute: Didn’t re"...
0xacab  ldc.i4.2
0xacac  newarr   [mscorlib]System.Object
0xacb1  dup
0xacb2  ldc.i4.0
0xacb3  ldloc.s  7
0xacb5  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xacba  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xacbf  stelem.ref
0xacc0  dup
0xacc1  ldc.i4.1
0xacc2  ldloc.s  0x11
0xacc4  stelem.ref
0xacc5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xacca  ldc.i4   0x80081111
0xaccf  ldc.i4.1
0xacd0  newarr   [mscorlib]System.Object
0xacd5  dup
0xacd6  ldc.i4.0
0xacd7  ldloc.s  7
0xacd9  ldfld    class <>c__DisplayClass72_1 <>c__DisplayClass72_0::CS$<>8__locals1
0xacde  ldfld    string <>c__DisplayClass72_1::pluginTypeName
0xace3  stelem.ref
  ... truncated ...
```
