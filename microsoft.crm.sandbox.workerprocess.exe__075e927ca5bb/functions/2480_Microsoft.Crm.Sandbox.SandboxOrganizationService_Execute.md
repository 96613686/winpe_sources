# Microsoft.Crm.Sandbox.SandboxOrganizationService::Execute

- ea: `0x2480`
- end: `0x2674`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::Execute`
- size: `500`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x2010`
- `0x2030`
- `0x22d0`
- `0x2480`

## string_xrefs

- `0x2487`: `SandboxOrganizationServices.Execute`
- `0x251d`: `SandboxOrganizationServices.Execute.client_Initialize()`
- `0x256a`: `SandboxOrganizationService.Execute: _sdkContext.UserId: {0}`
- `0x258d`: `SandboxOrganizationServices.Execute.wcfCall`
- `0x259a`: `SdkClientCommmunication`
- `0x2606`: `SandboxOrganizationService.Execute: Attempt {0} of {1}. Retrying. Error: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x2480  ldarg.3
0x2481  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings
0x2486  stloc.0
0x2487  ldstr    aSandboxorganiz_2// "SandboxOrganizationServices.Execute"
0x248c  ldloc.0
0x248d  ldc.i4.0
0x248e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings, bool)
0x2493  stloc.1
0x2494  ldarg.1
0x2495  ldstr    aOperation// "operation"
0x249a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x249f  ldarg.2
0x24a0  ldstr    aSerializedrequ// "serializedRequest"
0x24a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x24aa  ldnull
0x24ab  stloc.2
0x24ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24b1  ldstr    a01_0// "{0}{1}"
0x24b6  ldc.i4.2
0x24b7  newarr   [mscorlib]System.Object
0x24bc  dup
0x24bd  ldc.i4.0
0x24be  ldc.i4.2
0x24bf  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x24c4  stelem.ref
0x24c5  dup
0x24c6  ldc.i4.1
0x24c7  ldc.i4.s 0x1F
0x24c9  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxProperty
0x24ce  stelem.ref
0x24cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24d4  ldc.i4.8
0x24d5  call     int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetValueFromRegkeyOrgDefault(string, int32)
0x24da  stloc.3
0x24db  ldc.i4.0
0x24dc  stloc.s  4
0x24de  br       loc_2654
0x24e3  ldstr    aIsandboxsdklis// "ISandboxSdkListener.Execute\\"
0x24e8  ldarg.1
0x24e9  call     string [mscorlib]System.String::Concat(string, string)
0x24ee  ldarg.0
0x24ef  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x24f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x24f9  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x24fe  stloc.s  5
0x2500  ldloc.s  5
0x2502  ldarg.0
0x2503  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x2508  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x250d  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid)
0x2512  ldc.i4.1
0x2513  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x2518  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x251d  ldstr    aSandboxorganiz_3// "SandboxOrganizationServices.Execute.cli"...
0x2522  ldc.i4.3
0x2523  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x2528  stloc.s  7
0x252a  ldarg.0
0x252b  call     instance class Microsoft.Crm.Sandbox.SandboxSdkClient Microsoft.Crm.Sandbox.SandboxCallbackService::Initialize()
0x2530  stloc.2
0x2531  leave.s  loc_253F
0x2533  ldloc.s  7
0x2535  brfalse.s loc_253E
0x2537  ldloc.s  7
0x2539  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x253e  endfinally
0x253f  ldloc.s  5
0x2541  ldloc.2
0x2542  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Destination()
0x2547  ldarg.0
0x2548  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x254d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x2552  ldarg.0
0x2553  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCallbackService::workerCounter
0x2558  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Call(string, int32, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0x255d  ldarg.0
0x255e  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x2563  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x2568  ldc.i4.s 0x21
0x256a  ldstr    aSandboxorganiz_4// "SandboxOrganizationService.Execute: _sd"...
0x256f  ldc.i4.1
0x2570  newarr   [mscorlib]System.Object
0x2575  dup
0x2576  ldc.i4.0
0x2577  ldarg.0
0x2578  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxCallbackService::sdkContext
0x257d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_UserId()
0x2582  box      [mscorlib]System.Guid
0x2587  stelem.ref
0x2588  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x258d  ldstr    aSandboxorganiz_5// "SandboxOrganizationServices.Execute.wcf"...
0x2592  ldc.i4.3
0x2593  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x2598  stloc.s  7
0x259a  ldstr    aSdkclientcommm// "SdkClientCommmunication"
0x259f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosClientCall(string)
0x25a4  ldloc.2
0x25a5  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Proxy()
0x25aa  ldarg.0
0x25ab  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x25b0  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x25b5  ldarg.0
0x25b6  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxCallbackService::sdkContext
0x25bb  ldarg.1
0x25bc  ldarg.2
0x25bd  callvirt instance unsigned int8[] [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener::Execute(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext, string, unsigned int8[])
0x25c2  stloc.s  6
0x25c4  leave.s  loc_25D2
0x25c6  ldloc.s  7
0x25c8  brfalse.s loc_25D1
0x25ca  ldloc.s  7
0x25cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25d1  endfinally
0x25d2  ldloc.s  5
0x25d4  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodReturn()
0x25d9  ldloc.s  6
0x25db  stloc.s  8
0x25dd  leave    loc_2671
0x25e2  stloc.s  9
0x25e4  ldloc.s  5
0x25e6  ldloc.s  9
0x25e8  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadReturn(class [mscorlib]System.Exception)
0x25ed  ldloc.s  9
0x25ef  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsSafeToRetry(class [mscorlib]System.Exception)
0x25f4  brfalse.s loc_263E
0x25f6  ldloc.s  4
0x25f8  ldloc.3
0x25f9  ldc.i4.1
0x25fa  sub
0x25fb  bge.s    loc_263E
0x25fd  ldloc.s  9
0x25ff  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x2604  ldc.i4.s 0x2D
0x2606  ldstr    aSandboxorganiz_6// "SandboxOrganizationService.Execute: Att"...
0x260b  ldc.i4.3
0x260c  newarr   [mscorlib]System.Object
0x2611  dup
0x2612  ldc.i4.0
0x2613  ldloc.s  4
0x2615  ldc.i4.1
0x2616  add
0x2617  box      [mscorlib]System.Int32
0x261c  stelem.ref
0x261d  dup
0x261e  ldc.i4.1
0x261f  ldc.i4.8
0x2620  box      [mscorlib]System.Int32
0x2625  stelem.ref
0x2626  dup
0x2627  ldc.i4.2
0x2628  ldloc.s  9
0x262a  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ExpandException(class [mscorlib]System.Exception)
0x262f  stelem.ref
0x2630  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2635  ldloc.s  4
0x2637  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::ExponentialBackOffInMilliseconds(int32)
0x263c  leave.s  loc_264E
0x263e  ldarg.0
0x263f  ldloc.s  9
0x2641  ldloc.2
0x2642  call     instance class [mscorlib]System.Exception Microsoft.Crm.Sandbox.SandboxCallbackService::ProcessException(class [mscorlib]System.Exception e, class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x2647  throw
0x2648  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x264d  endfinally
0x264e  ldloc.s  4
0x2650  ldc.i4.1
0x2651  add
0x2652  stloc.s  4
0x2654  ldloc.s  4
0x2656  ldloc.3
0x2657  blt      loc_24E3
0x265c  ldstr    aRetryLogicShou// "Retry logic should not reach this point"...
0x2661  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2666  throw
0x2667  ldloc.1
0x2668  brfalse.s loc_2670
0x266a  ldloc.1
0x266b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2670  endfinally
0x2671  ldloc.s  8
0x2673  ret
```
