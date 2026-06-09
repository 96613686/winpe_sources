# <>c__DisplayClass6_0::<ExecuteAndReturnTraceInfo>b__0

- ea: `0xba70`
- end: `0xbf4d`
- name: `<>c__DisplayClass6_0::<ExecuteAndReturnTraceInfo>b__0`
- size: `1245`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x4130`
- `0x4210`
- `0x4240`
- `0x4670`
- `0x6320`
- `0x6330`
- `0x7370`
- `0x9720`
- `0x9790`
- `0x9840`
- `0x9860`
- `0xa960`
- `0xba70`

## string_xrefs

- `0xbd72`: `Plugin`
- `0xbe9e`: `Plugin`
- `0xbe0c`: `validateInput: {0} ; getWorker: {1} ; wcf call {2} ; initialize {3} ; trackCall {4} ; trackGoodReturn {5} ; wait {6} ; threadStartDelay {7}`

## pseudocode

```c

```

## disassembly

```asm
0xba70  ldstr    aSandboxhostExe_2// "SandboxHost.ExecuteAndReturnTraceInfo"
0xba75  ldarg.0
0xba76  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xba7b  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0xba80  ldarg.0
0xba81  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xba86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xba8b  ldarg.0
0xba8c  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xba91  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_RequestId()
0xba96  stloc.1
0xba97  ldloca.s 1
0xba99  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xba9e  ldarg.0
0xba9f  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbaa4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0xbaa9  ldarg.0
0xbaaa  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xbaaf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0xbab4  ldarg.0
0xbab5  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xbaba  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0xbabf  stloc.1
0xbac0  ldloca.s 1
0xbac2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xbac7  ldarg.0
0xbac8  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbacd  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0xbad2  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0xbad7  stloc.0
0xbad8  ldstr    aIsandboxhostEx// "ISandboxHost.Execute"
0xbadd  ldarg.0
0xbade  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbae3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0xbae8  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0xbaed  dup
0xbaee  ldarg.0
0xbaef  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbaf4  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_IsTelemetryFeatureEnabled()
0xbaf9  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::set_IsTelemetryFeatureEnabled(bool)
0xbafe  stloc.2
0xbaff  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xbb04  stloc.3
0xbb05  ldnull
0xbb06  stloc.s  4
0xbb08  ldnull
0xbb09  stloc.s  5
0xbb0b  ldnull
0xbb0c  stloc.s  6
0xbb0e  ldc.i4.0
0xbb0f  stloc.s  7
0xbb11  ldc.i4.1
0xbb12  stloc.s  8
0xbb14  ldc.i4.0
0xbb15  stloc.s  9
0xbb17  ldc.i4.0
0xbb18  stloc.s  0xA
0xbb1a  ldc.i4.0
0xbb1b  stloc.s  0xB
0xbb1d  ldc.i4.0
0xbb1e  stloc.s  0xC
0xbb20  ldc.i4.0
0xbb21  stloc.s  0xD
0xbb23  ldc.i4.0
0xbb24  conv.i8
0xbb25  stloc.s  0xE
0xbb27  ldc.i4.0
0xbb28  conv.i8
0xbb29  stloc.s  0xF
0xbb2b  ldc.i4.0
0xbb2c  conv.i8
0xbb2d  stloc.s  0x10
0xbb2f  ldc.i4.0
0xbb30  conv.i8
0xbb31  stloc.s  0x11
0xbb33  ldc.i4.0
0xbb34  conv.i8
0xbb35  stloc.s  0x12
0xbb37  ldc.i4.0
0xbb38  conv.i8
0xbb39  stloc.s  0x13
0xbb3b  ldstr    aHost// "Host"
0xbb40  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosExecution(string)
0xbb45  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xbb4a  stloc.s  5
0xbb4c  ldstr    aSandboxhostExe_3// "SandboxHost.ExecuteAndReturnTraceInfo.V"...
0xbb51  ldc.i4.3
0xbb52  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xbb57  stloc.s  0x14
0xbb59  ldarg.0
0xbb5a  ldfld    class Microsoft.Crm.Sandbox.SandboxHost <>c__DisplayClass6_0::<>4__this
0xbb5f  ldarg.0
0xbb60  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xbb65  ldarg.0
0xbb66  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbb6b  ldarg.0
0xbb6c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::pluginAssemblyId
0xbb71  ldarg.0
0xbb72  ldfld    int32 <>c__DisplayClass6_0::sourceHash
0xbb77  ldarg.0
0xbb78  ldfld    string <>c__DisplayClass6_0::assemblyName
0xbb7d  ldarg.0
0xbb7e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::pluginTypeId
0xbb83  ldarg.0
0xbb84  ldfld    string <>c__DisplayClass6_0::pluginTypeName
0xbb89  ldarg.0
0xbb8a  ldfld    string <>c__DisplayClass6_0::assemblyContents
0xbb8f  ldloc.2
0xbb90  call     instance void Microsoft.Crm.Sandbox.SandboxHost::ValidateInputs(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext requestContext, valuetype [mscorlib]System.Guid pluginAssemblyId, int32 sourceHash, string assemblyName, valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, string assemblyContents, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker)
0xbb95  leave.s  loc_BBA3
0xbb97  ldloc.s  0x14
0xbb99  brfalse.s loc_BBA2
0xbb9b  ldloc.s  0x14
0xbb9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbba2  endfinally
0xbba3  ldloc.s  5
0xbba5  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xbbaa  ldc.i4.0
0xbbab  stloc.s  0x15
0xbbad  br       loc_BD25
0xbbb2  ldc.i4.1
0xbbb3  stloc.s  8
0xbbb5  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xbbba  stloc.s  4
0xbbbc  ldstr    aSandboxhostExe_4// "SandboxHost.ExecuteAndReturnTraceInfo.G"...
0xbbc1  ldc.i4.3
0xbbc2  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xbbc7  stloc.s  0x14
0xbbc9  ldarg.0
0xbbca  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbbcf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0xbbd4  ldarg.0
0xbbd5  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xbbda  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0xbbdf  ldloca.s 9
0xbbe1  ldloca.s 0xA
0xbbe3  ldloca.s 0xB
0xbbe5  ldloca.s 0xC
0xbbe7  ldloca.s 0xD
0xbbe9  call     class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcess(valuetype [mscorlib]System.Guid organizationId, bool useDrawbridgeIsolation, [out] int32& orgCleanBucketsCount, [out] int32& orgReadyBucketsCount, [out] int32& orgInitializingBucketsCount, [out] int32& orgWaitingInitializingBucketCount, [out] int32& orgInactiveBucketCount)
0xbbee  stloc.s  6
0xbbf0  leave.s  loc_BBFE
0xbbf2  ldloc.s  0x14
0xbbf4  brfalse.s loc_BBFD
0xbbf6  ldloc.s  0x14
0xbbf8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbbfd  endfinally
0xbbfe  ldloc.s  6
0xbc00  ldstr    aWorker// "worker"
0xbc05  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbc0a  ldloc.s  4
0xbc0c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xbc11  ldloc.3
0xbc12  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xbc17  ldstr    aSandboxhostExe_5// "SandboxHost.ExecuteAndReturnTraceInfo.t"...
0xbc1c  ldc.i4.3
0xbc1d  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xbc22  stloc.s  0x14
0xbc24  ldloc.2
0xbc25  ldstr    aWaitforworker// "WaitForWorker"
0xbc2a  ldloc.3
0xbc2b  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xbc30  stloc.s  0x17
0xbc32  ldloca.s 0x17
0xbc34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc39  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0xbc3e  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(string, string)
0xbc43  leave.s  loc_BC51
0xbc45  ldloc.s  0x14
0xbc47  brfalse.s loc_BC50
0xbc49  ldloc.s  0x14
0xbc4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc50  endfinally
0xbc51  ldloc.3
0xbc52  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0xbc57  ldarg.0
0xbc58  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbc5d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_SharedVariables()
0xbc62  ldstr    aExecutetimesta// "ExecuteTimeStamp"
0xbc67  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xbc6c  box      [mscorlib]System.DateTime
0xbc71  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xbc76  ldstr    aSandboxhostExe_6// "SandboxHost.ExecuteAndReturnTraceInfo.w"...
0xbc7b  ldc.i4.3
0xbc7c  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xbc81  stloc.s  0x14
0xbc83  ldc.i4.0
0xbc84  stloc.s  8
0xbc86  ldloc.s  6
0xbc88  ldarg.0
0xbc89  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xbc8e  ldarg.0
0xbc8f  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbc94  ldarg.0
0xbc95  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::pluginAssemblyId
0xbc9a  ldarg.0
0xbc9b  ldfld    int32 <>c__DisplayClass6_0::sourceHash
0xbca0  ldarg.0
0xbca1  ldfld    string <>c__DisplayClass6_0::assemblyName
0xbca6  ldarg.0
0xbca7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::pluginTypeId
0xbcac  ldarg.0
0xbcad  ldfld    string <>c__DisplayClass6_0::pluginTypeName
0xbcb2  ldarg.0
0xbcb3  ldfld    string <>c__DisplayClass6_0::pluginConfiguration
0xbcb8  ldarg.0
0xbcb9  ldfld    string <>c__DisplayClass6_0::pluginSecureConfig
0xbcbe  ldarg.0
0xbcbf  ldfld    bool <>c__DisplayClass6_0::returnTraceInfo
0xbcc4  ldloca.s 0xE
0xbcc6  ldloca.s 0xF
0xbcc8  ldloca.s 0x10
0xbcca  ldloca.s 0x11
0xbccc  ldloca.s 0x12
0xbcce  ldloca.s 0x13
0xbcd0  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext Microsoft.Crm.Sandbox.SandboxWorkerProcess::Execute(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext requestContext, valuetype [mscorlib]System.Guid pluginAssemblyId, int32 sourceHash, string assemblyName, valuetype [mscorlib]System.Guid pluginTypeId, string pluginTypeName, string pluginConfiguration, string pluginSecureConfig, bool returnTraceInfo, [out] int64& wcfExecInMs, [out] int64& initializeInMs, [out] int64& trackCallInMs, [out] int64& trackGoodReturnInMs, [out] int64& waitInMs, [out] int64& taskStartDelay)
0xbcd5  stloc.s  0x16
0xbcd7  leave.s  loc_BCFF
0xbcd9  stloc.s  0x18
0xbcdb  ldarg.0
0xbcdc  ldfld    class Microsoft.Crm.Sandbox.SandboxHost <>c__DisplayClass6_0::<>4__this
0xbce1  ldloc.s  6
0xbce3  ldloc.s  0x18
0xbce5  ldloc.s  0x15
0xbce7  call     instance bool Microsoft.Crm.Sandbox.SandboxHost::CheckIfHostShouldFailAndDiscardWorker(class Microsoft.Crm.Sandbox.SandboxWorkerProcess worker, class [mscorlib]System.Exception e, int32 retryCount)
0xbcec  brfalse.s loc_BCFD
0xbcee  ldloc.s  8
0xbcf0  brtrue.s loc_BCFB
0xbcf2  ldloc.s  0x18
0xbcf4  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsSafeToRetry(class [mscorlib]System.Exception)
0xbcf9  stloc.s  8
0xbcfb  rethrow
0xbcfd  leave.s  loc_BD1F
0xbcff  leave.s  loc_BD0D
0xbd01  ldloc.s  0x14
0xbd03  brfalse.s loc_BD0C
0xbd05  ldloc.s  0x14
0xbd07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbd0c  endfinally
0xbd0d  ldloc.2
0xbd0e  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodExit()
0xbd13  ldc.i4.1
0xbd14  stloc.s  7
0xbd16  ldloc.s  0x16
0xbd18  stloc.s  0x19
0xbd1a  leave    loc_BF4A
0xbd1f  ldloc.s  0x15
0xbd21  ldc.i4.1
0xbd22  add
0xbd23  stloc.s  0x15
0xbd25  ldloc.s  0x15
0xbd27  ldarg.0
0xbd28  ldfld    class Microsoft.Crm.Sandbox.SandboxHost <>c__DisplayClass6_0::<>4__this
0xbd2d  call     instance int32 Microsoft.Crm.Sandbox.SandboxHost::get_MaxWorkerCallRetry()
0xbd32  blt      loc_BBB2
0xbd37  ldstr    aRetryLogicShou// "Retry logic should not reach this code."
0xbd3c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xbd41  throw
0xbd42  stloc.s  0x1A
0xbd44  ldstr    aSandboxhostExe_7// "SandboxHost.ExecuteAndReturnTraceInfo.E"...
0xbd49  ldc.i4.3
0xbd4a  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xbd4f  stloc.s  0x14
0xbd51  ldarg.0
0xbd52  ldfld    class Microsoft.Crm.Sandbox.SandboxHost <>c__DisplayClass6_0::<>4__this
0xbd57  ldloc.s  0x1A
0xbd59  ldloc.2
0xbd5a  ldarg.0
0xbd5b  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext <>c__DisplayClass6_0::requestContext
0xbd60  ldarg.0
0xbd61  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo <>c__DisplayClass6_0::callInfo
0xbd66  ldarg.0
0xbd67  ldfld    string <>c__DisplayClass6_0::assemblyName
0xbd6c  ldarg.0
0xbd6d  ldfld    string <>c__DisplayClass6_0::pluginTypeName
0xbd72  ldstr    aPlugin// "Plugin"
0xbd77  ldloc.s  6
0xbd79  ldloc.s  9
0xbd7b  ldloc.s  0xA
0xbd7d  ldloc.s  0xB
0xbd7f  ldloc.s  0xC
0xbd81  ldloc.s  0xD
0xbd83  ldloc.s  8
0xbd85  call     instance void Microsoft.Crm.Sandbox.SandboxHost::HandleException(class [mscorlib]System.Exception e, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, string assemblyName, string pluginTypeName, string sandboxCodeUnitType, class Microsoft.Crm.Sandbox.SandboxWorkerProcess worker, int32 orgCleanBucketsCount, int32 orgReadyBucketsCount, int32 orgInitializingBucketsCount, int32 orgWaitingInitializingBucketCount, int32 orgInactiveBucketCount, bool exceptionRetriable)
0xbd8a  rethrow
0xbd8c  ldloc.s  0x14
0xbd8e  brfalse.s loc_BD97
0xbd90  ldloc.s  0x14
0xbd92  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbd97  endfinally
0xbd98  ldstr    aSandboxhostExe_8// "SandboxHost.ExecuteAndReturnTraceInfo.F"...
0xbd9d  ldc.i4.3
0xbd9e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0xbda3  stloc.s  0x14
0xbda5  ldloc.3
0xbda6  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xbdab  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::ExitExecute()
0xbdb0  ldloc.s  7
0xbdb2  brfalse  loc_BF12
0xbdb7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::get_Instance()
  ... truncated ...
```
