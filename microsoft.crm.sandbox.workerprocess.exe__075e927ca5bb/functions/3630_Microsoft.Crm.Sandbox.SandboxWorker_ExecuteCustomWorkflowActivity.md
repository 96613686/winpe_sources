# Microsoft.Crm.Sandbox.SandboxWorker::ExecuteCustomWorkflowActivity

- ea: `0x3630`
- end: `0x381f`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::ExecuteCustomWorkflowActivity`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d80`

## callees

- `0x2f30`
- `0x3300`
- `0x3470`
- `0x3630`
- `0x4810`

## string_xrefs

- `0x36f5`: `SandboxWorker.ExecuteCustomWorkflowActivity.InitializeSandboxServices`

## pseudocode

```c

```

## disassembly

```asm
0x3630  ldstr    aSandboxworkerE_6// "SandboxWorker.ExecuteCustomWorkflowActi"...
0x3635  ldarg.1
0x3636  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x363b  ldarg.2
0x363c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x3641  ldarg.2
0x3642  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_RequestId()
0x3647  stloc.1
0x3648  ldloca.s 1
0x364a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x364f  ldarg.2
0x3650  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x3655  ldarg.1
0x3656  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x365b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x3660  ldarg.1
0x3661  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0x3666  stloc.1
0x3667  ldloca.s 1
0x3669  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x366e  ldarg.2
0x366f  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0x3674  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x3679  stloc.0
0x367a  ldc.i4.1
0x367b  stloc.2
0x367c  ldstr    aIsandboxworker_1// "ISandboxWorker.Execute"
0x3681  ldarg.2
0x3682  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x3687  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x368c  stloc.3
0x368d  ldarg.1
0x368e  ldarg.s  5
0x3690  ldstr    asc_A34E// ":"
0x3695  ldarg.s  7
0x3697  call     string [mscorlib]System.String::Concat(string, string, string)
0x369c  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_PluginInfo(string)
0x36a1  call     int32 Microsoft.Crm.Sandbox.SandboxWorkerMain::get_Port()
0x36a6  ldc.i4.2
0x36a7  rem
0x36a8  brtrue.s loc_36B4
0x36aa  ldstr    aWorker// "Worker"
0x36af  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosExecution(string)
0x36b4  ldstr    aSandboxworkerE_7// "SandboxWorker.ExecuteCustomWorkflowActi"...
0x36b9  ldc.i4.3
0x36ba  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x36bf  stloc.s  8
0x36c1  ldarg.0
0x36c2  ldarg.1
0x36c3  ldarg.2
0x36c4  ldarg.3
0x36c5  ldarg.s  4
0x36c7  ldarg.s  5
0x36c9  ldarg.s  7
0x36cb  ldloc.3
0x36cc  ldarg.s  8
0x36ce  call     instance class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper> Microsoft.Crm.Sandbox.SandboxWorker::ValidateAndGetAppDomainHelper(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, valuetype [mscorlib]System.Guid pluginAssemblyId, int32 sourceHash, string assemblyName, string pluginTypeName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, [out] class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter& workerCounter)
0x36d3  stloc.s  5
0x36d5  leave.s  loc_36E3
0x36d7  ldloc.s  8
0x36d9  brfalse.s loc_36E2
0x36db  ldloc.s  8
0x36dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36e2  endfinally
0x36e3  ldloc.s  5
0x36e5  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper>::get_Item1()
0x36ea  stloc.s  6
0x36ec  ldloc.s  5
0x36ee  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper>::get_Item2()
0x36f3  stloc.s  9
0x36f5  ldstr    aSandboxworkerE_8// "SandboxWorker.ExecuteCustomWorkflowActi"...
0x36fa  ldc.i4.3
0x36fb  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x3700  stloc.s  8
0x3702  ldarg.0
0x3703  ldarg.2
0x3704  ldloc.s  9
0x3706  ldloc.s  9
0x3708  ldloc.s  6
0x370a  ldarg.1
0x370b  ldarg.s  8
0x370d  ldind.ref
0x370e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxWorker::InitializeSandboxServices(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext requestContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService serviceBusService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper helper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0x3713  stloc.s  7
0x3715  leave.s  loc_3723
0x3717  ldloc.s  8
0x3719  brfalse.s loc_3722
0x371b  ldloc.s  8
0x371d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3722  endfinally
0x3723  ldstr    aSandboxworkerE_9// "SandboxWorker.ExecuteCustomWorkflowActi"...
0x3728  ldc.i4.3
0x3729  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x372e  stloc.s  8
0x3730  ldc.i4.0
0x3731  stloc.2
0x3732  ldloc.s  6
0x3734  ldloc.s  9
0x3736  ldarg.s  7
0x3738  ldarg.2
0x3739  ldloc.s  7
0x373b  ldarg.1
0x373c  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3741  ldstr    aWorkerappdomai// "WorkerAppDomain"
0x3746  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ShouldFail(string)
0x374b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory, string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext, class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>, bool, bool)
0x3750  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCustomActivityExecutionContext
0x3755  stloc.s  4
0x3757  leave.s  loc_3765
0x3759  ldloc.s  8
0x375b  brfalse.s loc_3764
0x375d  ldloc.s  8
0x375f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3764  endfinally
0x3765  leave.s  loc_3773
0x3767  ldloc.s  9
0x3769  brfalse.s loc_3772
0x376b  ldloc.s  9
0x376d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3772  endfinally
0x3773  ldloc.s  4
0x3775  ldstr    aResponsecontex// "responseContext"
0x377a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x377f  ldloc.3
0x3780  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodExit()
0x3785  ldarg.s  9
0x3787  brfalse.s loc_3797
0x3789  ldloc.s  4
0x378b  ldloc.s  6
0x378d  callvirt instance string [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TraceInfo()
0x3792  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::set_TraceInfo(string)
0x3797  ldloc.s  4
0x3799  stloc.s  0xA
0x379b  leave.s  loc_381C
0x379d  stloc.s  0xB
0x379f  ldloc.s  0xB
0x37a1  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x37a6  ldstr    aExceptionretri// "ExceptionRetriable"
0x37ab  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x37b0  stloc.s  0xC
0x37b2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x37b7  ldc.i4.s 0x23
0x37b9  ldstr    aSandboxworkerE_3// "SandboxWorker.Execute: Retriable Sandbo"...
0x37be  ldc.i4.1
0x37bf  newarr   [mscorlib]System.Object
0x37c4  dup
0x37c5  ldc.i4.0
0x37c6  ldloc.s  0xC
0x37c8  stelem.ref
0x37c9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37ce  ldloc.s  0xC
0x37d0  brfalse.s loc_37FF
0x37d2  ldloc.s  0xC
0x37d4  isinst   [mscorlib]System.Boolean
0x37d9  brfalse.s loc_37FF
0x37db  ldloc.s  0xC
0x37dd  unbox.any [mscorlib]System.Boolean
0x37e2  stloc.2
0x37e3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x37e8  ldc.i4.s 0x23
0x37ea  ldstr    aSandboxworkerE_4// "SandboxWorker.Execute: Retriable appDom"...
0x37ef  ldc.i4.1
0x37f0  newarr   [mscorlib]System.Object
0x37f5  dup
0x37f6  ldc.i4.0
0x37f7  ldloc.s  0xC
0x37f9  stelem.ref
0x37fa  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37ff  ldarg.0
0x3800  ldloc.s  0xB
0x3802  ldloc.3
0x3803  ldarg.2
0x3804  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x3809  ldarg.1
0x380a  ldloc.2
0x380b  call     instance void Microsoft.Crm.Sandbox.SandboxWorker::HandleException(class [mscorlib]System.Exception e, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, bool exceptionRetriable)
0x3810  rethrow
0x3812  ldloc.0
0x3813  brfalse.s loc_381B
0x3815  ldloc.0
0x3816  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x381b  endfinally
0x381c  ldloc.s  0xA
0x381e  ret
```
