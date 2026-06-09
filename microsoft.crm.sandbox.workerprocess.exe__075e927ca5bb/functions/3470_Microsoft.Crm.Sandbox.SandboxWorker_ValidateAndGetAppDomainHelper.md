# Microsoft.Crm.Sandbox.SandboxWorker::ValidateAndGetAppDomainHelper

- ea: `0x3470`
- end: `0x35d8`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::ValidateAndGetAppDomainHelper`
- size: `360`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x3090`
- `0x3630`

## callees

- `0xfa0`
- `0x18b0`
- `0x2920`
- `0x2b70`
- `0x3470`
- `0x35f0`

## string_xrefs

- `0x348c`: `owningExtension`
- `0x34a4`: `pluginTypeName`
- `0x3523`: `SandboxWorker.ValidateAndGetAppDomainHelper.appDomain.LoadPluginAssembly`
- `0x355a`: `SandboxWorker.ValidateAndGetAppDomainHelper: Creating SandboxOrganizationServiceFactory`
- `0x356a`: `SandboxWorker.ValidateAndGetAppDomainHelper.new.SandboxOrganizationServiceFactory`

## pseudocode

```c

```

## disassembly

```asm
0x3470  ldarg.1
0x3471  ldstr    aCallinfo// "callInfo"
0x3476  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x347b  ldarg.2
0x347c  ldstr    aRequestcontext// "requestContext"
0x3481  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3486  ldarg.2
0x3487  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OwningExtension()
0x348c  ldstr    aOwningextensio// "owningExtension"
0x3491  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3496  ldarg.s  5
0x3498  ldstr    aAssemblyname// "assemblyName"
0x349d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x34a2  ldarg.s  6
0x34a4  ldstr    aPlugintypename// "pluginTypeName"
0x34a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x34ae  ldarg.1
0x34af  ldstr    aIsandboxworker_1// "ISandboxWorker.Execute"
0x34b4  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::Trace(string)
0x34b9  ldarg.s  7
0x34bb  ldarg.2
0x34bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x34c1  ldarg.s  5
0x34c3  ldarg.s  6
0x34c5  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid, string, string)
0x34ca  ldarg.s  7
0x34cc  ldarg.2
0x34cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x34d2  ldarg.1
0x34d3  ldarg.2
0x34d4  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0x34d9  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Enter(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, int32)
0x34de  ldarg.2
0x34df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x34e4  stloc.0
0x34e5  ldarg.2
0x34e6  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0x34eb  stloc.1
0x34ec  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorker::_executeCount
0x34f1  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x34f6  pop
0x34f7  call     void Microsoft.Crm.Sandbox.SandboxWorker::UpdateStartTimes()
0x34fc  ldstr    aSandboxworkerV// "SandboxWorker.ValidateAndGetAppDomainHe"...
0x3501  ldc.i4.3
0x3502  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x3507  stloc.s  6
0x3509  ldarg.2
0x350a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x350f  call     class Microsoft.Crm.Sandbox.SandboxAppDomain Microsoft.Crm.Sandbox.SandboxAppDomainManager::GetAppDomain(valuetype [mscorlib]System.Guid organizationId)
0x3514  stloc.2
0x3515  leave.s  loc_3523
0x3517  ldloc.s  6
0x3519  brfalse.s loc_3522
0x351b  ldloc.s  6
0x351d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3522  endfinally
0x3523  ldstr    aSandboxworkerV_0// "SandboxWorker.ValidateAndGetAppDomainHe"...
0x3528  ldc.i4.3
0x3529  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x352e  stloc.s  6
0x3530  ldloc.2
0x3531  ldarg.3
0x3532  ldarg.s  4
0x3534  ldarg.s  5
0x3536  ldloc.0
0x3537  ldloc.1
0x3538  ldarg.1
0x3539  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x353e  callvirt instance class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper Microsoft.Crm.Sandbox.SandboxAppDomain::LoadPluginAssembly(valuetype [mscorlib]System.Guid pluginAssemblyId, int32 pluginAssemblyHashCode, string assemblyName, valuetype [mscorlib]System.Guid trackingId, int32 depth, bool useDrawbridgeEnabled)
0x3543  stloc.3
0x3544  leave.s  loc_3552
0x3546  ldloc.s  6
0x3548  brfalse.s loc_3551
0x354a  ldloc.s  6
0x354c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3551  endfinally
0x3552  ldarg.2
0x3553  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x3558  ldc.i4.s 0x21
0x355a  ldstr    aSandboxworkerV_1// "SandboxWorker.ValidateAndGetAppDomainHe"...
0x355f  ldc.i4.0
0x3560  newarr   [mscorlib]System.Object
0x3565  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x356a  ldstr    aSandboxworkerV_2// "SandboxWorker.ValidateAndGetAppDomainHe"...
0x356f  ldc.i4.3
0x3570  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x3575  stloc.s  6
0x3577  ldarg.1
0x3578  ldarg.2
0x3579  ldloc.3
0x357a  callvirt instance class [mscorlib]System.Reflection.AssemblyName [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_AssemblyName()
0x357f  ldloc.3
0x3580  callvirt instance bool [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_IsStrongNameSigned()
0x3585  call     string [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveAssemblyName(class [mscorlib]System.Reflection.AssemblyName, bool)
0x358a  newobj   instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, string assemblyName)
0x358f  stloc.s  4
0x3591  leave.s  loc_359F
0x3593  ldloc.s  6
0x3595  brfalse.s loc_359E
0x3597  ldloc.s  6
0x3599  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x359e  endfinally
0x359f  ldarg.s  8
0x35a1  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter::.ctor()
0x35a6  stind.ref
0x35a7  ldloc.s  4
0x35a9  ldarg.s  8
0x35ab  ldind.ref
0x35ac  callvirt instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::set_WorkerCounter(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter value)
0x35b1  ldloc.3
0x35b2  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_CurrentTraceSettings()
0x35b7  call     valuetype [System]System.Diagnostics.TraceLevel [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_HighestTraceLevel()
0x35bc  callvirt instance void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::SetTraceContextSettings(object, valuetype [System]System.Diagnostics.TraceLevel)
0x35c1  ldloc.s  4
0x35c3  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_CurrentTraceSettings()
0x35c8  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory, object)
0x35cd  stloc.s  5
0x35cf  ldloc.3
0x35d0  ldloc.s  5
0x35d2  newobj   instance void class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper>::.ctor(var<u1>, !!T0)
0x35d7  ret
```
