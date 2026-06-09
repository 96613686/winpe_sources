# Microsoft.Crm.Sandbox.SandboxWorker::Execute

- ea: `0x3090`
- end: `0x32c4`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::Execute`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1d80`

## callees

- `0x2f30`
- `0x3090`
- `0x3300`
- `0x3470`
- `0x3a10`

## pseudocode

```c

```

## disassembly

```asm
0x3090  ldstr    aSandboxworkerE_0// "SandboxWorker.Execute"
0x3095  ldarg.1
0x3096  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x309b  ldarg.2
0x309c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x30a1  ldarg.2
0x30a2  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_RequestId()
0x30a7  stloc.1
0x30a8  ldloca.s 1
0x30aa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x30af  ldarg.2
0x30b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x30b5  ldarg.1
0x30b6  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x30bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x30c0  ldarg.1
0x30c1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0x30c6  stloc.1
0x30c7  ldloca.s 1
0x30c9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x30ce  ldarg.2
0x30cf  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_Depth()
0x30d4  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x30d9  stloc.0
0x30da  ldc.i4.1
0x30db  stloc.2
0x30dc  ldstr    aIsandboxworker_1// "ISandboxWorker.Execute"
0x30e1  ldarg.2
0x30e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_CorrelationId()
0x30e7  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x30ec  stloc.3
0x30ed  ldarg.1
0x30ee  ldarg.s  5
0x30f0  ldstr    asc_A34E// ":"
0x30f5  ldarg.s  7
0x30f7  call     string [mscorlib]System.String::Concat(string, string, string)
0x30fc  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_PluginInfo(string)
0x3101  ldstr    aWorker// "Worker"
0x3106  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ChaosExecution(string)
0x310b  call     bool Microsoft.Crm.Sandbox.SandboxWorker::get_Shutdown()
0x3110  brfalse.s loc_311D
0x3112  ldstr    aWorkerProcessI// "Worker process is shutting down."
0x3117  newobj   instance void [mscorlib]System.OperationCanceledException::.ctor(string)
0x311c  throw
0x311d  ldstr    aSandboxworkerE_1// "SandboxWorker.Execute.ValidateAndGetApp"...
0x3122  ldc.i4.3
0x3123  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x3128  stloc.s  7
0x312a  ldarg.0
0x312b  ldarg.1
0x312c  ldarg.2
0x312d  ldarg.3
0x312e  ldarg.s  4
0x3130  ldarg.s  5
0x3132  ldarg.s  7
0x3134  ldloc.3
0x3135  ldarg.s  0xA
0x3137  call     instance class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper> Microsoft.Crm.Sandbox.SandboxWorker::ValidateAndGetAppDomainHelper(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext requestContext, valuetype [mscorlib]System.Guid pluginAssemblyId, int32 sourceHash, string assemblyName, string pluginTypeName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, [out] class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter& workerCounter)
0x313c  stloc.s  5
0x313e  leave.s  loc_314C
0x3140  ldloc.s  7
0x3142  brfalse.s loc_314B
0x3144  ldloc.s  7
0x3146  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x314b  endfinally
0x314c  ldloc.s  5
0x314e  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper>::get_Item1()
0x3153  stloc.s  6
0x3155  ldloc.s  5
0x3157  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper>::get_Item2()
0x315c  stloc.s  8
0x315e  ldarg.2
0x315f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x3164  ldc.i4.s 0x21
0x3166  ldstr    aSandboxworkerE_2// "SandboxWorker.Execute: Calling SandboxA"...
0x316b  ldc.i4.0
0x316c  newarr   [mscorlib]System.Object
0x3171  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3176  ldarg.0
0x3177  ldarg.2
0x3178  ldloc.s  8
0x317a  ldloc.s  8
0x317c  ldloc.s  6
0x317e  ldarg.1
0x317f  ldarg.s  0xA
0x3181  ldind.ref
0x3182  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxWorker::InitializeSandboxServices(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext requestContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IServiceEndpointNotificationService serviceBusService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory organizationServiceFactory, class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper helper, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter)
0x3187  stloc.s  9
0x3189  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x318e  ldstr    a01_0// "{0}{1}"
0x3193  ldc.i4.2
0x3194  newarr   [mscorlib]System.Object
0x3199  dup
0x319a  ldc.i4.0
0x319b  ldc.i4.3
0x319c  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x31a1  stelem.ref
0x31a2  dup
0x31a3  ldc.i4.1
0x31a4  ldc.i4.s 0xF
0x31a6  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x31ab  stelem.ref
0x31ac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31b1  ldc.i4.0
0x31b2  box      [mscorlib]System.Int32
0x31b7  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x31bc  unbox.any [mscorlib]System.Int32
0x31c1  ldc.i4.0
0x31c2  cgt
0x31c4  stloc.s  0xA
0x31c6  ldc.i4.0
0x31c7  stloc.2
0x31c8  ldloc.s  6
0x31ca  ldloc.s  8
0x31cc  ldloc.s  9
0x31ce  ldarg.s  7
0x31d0  ldarg.s  8
0x31d2  ldarg.s  9
0x31d4  ldarg.2
0x31d5  ldloc.s  0xA
0x31d7  ldstr    aWorkerappdomai// "WorkerAppDomain"
0x31dc  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCommon.ChaosAgent::ShouldFail(string)
0x31e1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory, class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>, string, string, string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext, bool, bool)
0x31e6  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext
0x31eb  stloc.s  4
0x31ed  ldloc.s  4
0x31ef  ldstr    aResponsecontex// "responseContext"
0x31f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x31f9  ldloc.3
0x31fa  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodExit()
0x31ff  ldarg.s  0xB
0x3201  brfalse.s loc_3211
0x3203  ldloc.s  4
0x3205  ldloc.s  6
0x3207  callvirt instance string [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TraceInfo()
0x320c  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::set_TraceInfo(string)
0x3211  ldloc.s  4
0x3213  stloc.s  0xB
0x3215  leave    loc_32C1
0x321a  ldloc.s  8
0x321c  brfalse.s loc_3225
0x321e  ldloc.s  8
0x3220  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3225  endfinally
0x3226  stloc.s  0xC
0x3228  ldloc.s  0xC
0x322a  callvirt instance class [mscorlib]System.Collections.IDictionary [mscorlib]System.Exception::get_Data()
0x322f  ldstr    aExceptionretri// "ExceptionRetriable"
0x3234  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3239  stloc.s  0xD
0x323b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x3240  ldc.i4.s 0x23
0x3242  ldstr    aSandboxworkerE_3// "SandboxWorker.Execute: Retriable Sandbo"...
0x3247  ldc.i4.1
0x3248  newarr   [mscorlib]System.Object
0x324d  dup
0x324e  ldc.i4.0
0x324f  ldloc.s  0xD
0x3251  stelem.ref
0x3252  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3257  ldloc.s  0xD
0x3259  brfalse.s loc_3288
0x325b  ldloc.s  0xD
0x325d  isinst   [mscorlib]System.Boolean
0x3262  brfalse.s loc_3288
0x3264  ldloc.s  0xD
0x3266  unbox.any [mscorlib]System.Boolean
0x326b  stloc.2
0x326c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x3271  ldc.i4.s 0x23
0x3273  ldstr    aSandboxworkerE_4// "SandboxWorker.Execute: Retriable appDom"...
0x3278  ldc.i4.1
0x3279  newarr   [mscorlib]System.Object
0x327e  dup
0x327f  ldc.i4.0
0x3280  ldloc.s  0xD
0x3282  stelem.ref
0x3283  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3288  ldstr    aSandboxworkerE_5// "SandboxWorker.Execute.Exception"
0x328d  ldc.i4.3
0x328e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x3293  stloc.s  7
0x3295  ldarg.2
0x3296  brfalse.s loc_32A9
0x3298  ldarg.0
0x3299  ldloc.s  0xC
0x329b  ldloc.3
0x329c  ldarg.2
0x329d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OrganizationId()
0x32a2  ldarg.1
0x32a3  ldloc.2
0x32a4  call     instance void Microsoft.Crm.Sandbox.SandboxWorker::HandleException(class [mscorlib]System.Exception e, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, bool exceptionRetriable)
0x32a9  rethrow
0x32ab  ldloc.s  7
0x32ad  brfalse.s loc_32B6
0x32af  ldloc.s  7
0x32b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32b6  endfinally
0x32b7  ldloc.0
0x32b8  brfalse.s loc_32C0
0x32ba  ldloc.0
0x32bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32c0  endfinally
0x32c1  ldloc.s  0xB
0x32c3  ret
```
