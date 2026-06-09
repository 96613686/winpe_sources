# Microsoft.Crm.Sdk.InProcessCrmService::Execute

- ea: `0x2e20`
- end: `0x2fc8`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::Execute`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x81e0`

## callees

- `0x550`
- `0x5a0`
- `0x2e20`
- `0x2fd0`
- `0x30e0`
- `0x30f0`
- `0x3130`
- `0x3200`
- `0x3310`
- `0x33c0`
- `0x45f0`
- `0xfb40`

## string_xrefs

- `0x2f59`: `InProcessCrmService finished processing request {0} for user {1} as user {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x2e20  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x2e25  stloc.0
0x2e26  ldloc.0
0x2e27  ldarg.1
0x2e28  stfld    object <>c__DisplayClass2_0::request
0x2e2d  ldloc.0
0x2e2e  ldarg.0
0x2e2f  stfld    class Microsoft.Crm.Sdk.InProcessCrmService <>c__DisplayClass2_0::<>4__this
0x2e34  ldarg.0
0x2e35  ldloc.0
0x2e36  ldfld    object <>c__DisplayClass2_0::request
0x2e3b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext Microsoft.Crm.Sdk.InProcessCrmService::CreateSoapContext(object request)
0x2e40  stloc.1
0x2e41  ldnull
0x2e42  stloc.2
0x2e43  ldarg.0
0x2e44  ldloc.1
0x2e45  ldloc.0
0x2e46  ldflda   class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth <>c__DisplayClass2_0::userAuth
0x2e4b  ldloc.0
0x2e4c  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::targetUserId
0x2e51  ldloca.s 2
0x2e53  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::InitializeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext soapContext, [out] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth& userAuth, [out] valuetype [mscorlib]System.Guid& targetUserId, [out] class [Microsoft.Crm.Core]Microsoft.Crm.Performance.IWebServicePerformanceCounters& counters)
0x2e58  ldarg.0
0x2e59  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x2e5e  ldc.i4.s 0x1A
0x2e60  ldstr    a0// "{0}"
0x2e65  ldc.i4.1
0x2e66  newarr   [mscorlib]System.Object
0x2e6b  dup
0x2e6c  ldc.i4.0
0x2e6d  ldloc.0
0x2e6e  ldftn    instance string <>c__DisplayClass2_0::<Execute>b__0()
0x2e74  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDelayedTracing/DelayedStringConverter::.ctor(object, native int)
0x2e79  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDelayedTracing::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDelayedTracing/DelayedStringConverter)
0x2e7e  stelem.ref
0x2e7f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e84  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x2e89  brfalse.s loc_2EFE
0x2e8b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2e90  stloc.s  6
0x2e92  ldarg.0
0x2e93  ldloc.0
0x2e94  ldfld    object <>c__DisplayClass2_0::request
0x2e99  ldloc.s  6
0x2e9b  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::SerializeRequest(object request, class [mscorlib]System.Text.StringBuilder sb)
0x2ea0  ldloc.s  6
0x2ea2  callvirt instance string [mscorlib]System.Object::ToString()
0x2ea7  call     string [Microsoft.Crm.Core]Microsoft.Crm.Performance.XmlEntityNameExtractor::QuickExtract(string)
0x2eac  stloc.s  7
0x2eae  ldloc.0
0x2eaf  ldfld    object <>c__DisplayClass2_0::request
0x2eb4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2eb9  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2ebe  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x2ec3  stloc.s  8
0x2ec5  ldloc.s  7
0x2ec7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ecc  brtrue.s loc_2EE5
0x2ece  ldloc.s  8
0x2ed0  ldstr    asc_121CE// " "
0x2ed5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2eda  pop
0x2edb  ldloc.s  8
0x2edd  ldloc.s  7
0x2edf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ee4  pop
0x2ee5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x2eea  ldc.i4.1
0x2eeb  ldarg.0
0x2eec  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x2ef1  ldloc.s  8
0x2ef3  callvirt instance string [mscorlib]System.Object::ToString()
0x2ef8  ldc.i4.0
0x2ef9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnBeginRequest(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceTraceType, valuetype [mscorlib]System.Guid, string, int32)
0x2efe  ldarg.0
0x2eff  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_transactionContextId
0x2f04  ldsfld   class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EndpointVersionProvider::CrmSdk2007Version
0x2f09  newobj   instance void Microsoft.Crm.Sdk.CrmServiceInternal::.ctor(valuetype [mscorlib]System.Guid transactionContextId, class [mscorlib]System.Version endpointVersion)
0x2f0e  ldarg.0
0x2f0f  ldloc.0
0x2f10  ldfld    object <>c__DisplayClass2_0::request
0x2f15  call     instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.InProcessCrmService::ConvertToDynamicRequest(object strongTypedRequest)
0x2f1a  stloc.3
0x2f1b  ldloc.3
0x2f1c  ldarg.0
0x2f1d  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Sdk.InProcessCrmService::_correlationToken
0x2f22  ldarg.0
0x2f23  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.Sdk.InProcessCrmService::_callerOriginToken
0x2f28  ldloc.0
0x2f29  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth <>c__DisplayClass2_0::userAuth
0x2f2e  ldloc.0
0x2f2f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::targetUserId
0x2f34  callvirt instance class Microsoft.Crm.Sdk.ResponseBase Microsoft.Crm.Sdk.CrmServiceInternal::Execute(class Microsoft.Crm.Sdk.RequestBase request, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x2f39  stloc.s  4
0x2f3b  ldarg.0
0x2f3c  ldloc.s  4
0x2f3e  ldloc.0
0x2f3f  ldfld    object <>c__DisplayClass2_0::request
0x2f44  ldloc.3
0x2f45  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x2f4a  call     instance object Microsoft.Crm.Sdk.InProcessCrmService::ConvertToStrongTypedResponse(class Microsoft.Crm.Sdk.ResponseBase dynamicResponse, object request, class Microsoft.Crm.Sdk.IRequestBuilder requestBuilder)
0x2f4f  stloc.s  5
0x2f51  ldarg.0
0x2f52  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x2f57  ldc.i4.s 0x1A
0x2f59  ldstr    aInprocesscrmse// "InProcessCrmService finished processing"...
0x2f5e  ldc.i4.3
0x2f5f  newarr   [mscorlib]System.Object
0x2f64  dup
0x2f65  ldc.i4.0
0x2f66  ldloc.0
0x2f67  ldfld    object <>c__DisplayClass2_0::request
0x2f6c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f71  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2f76  stelem.ref
0x2f77  dup
0x2f78  ldc.i4.1
0x2f79  ldloc.0
0x2f7a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth <>c__DisplayClass2_0::userAuth
0x2f7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x2f84  box      [mscorlib]System.Guid
0x2f89  stelem.ref
0x2f8a  dup
0x2f8b  ldc.i4.2
0x2f8c  ldloc.0
0x2f8d  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::targetUserId
0x2f92  box      [mscorlib]System.Guid
0x2f97  stelem.ref
0x2f98  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f9d  ldarg.0
0x2f9e  ldloc.2
0x2f9f  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::UninitializeContext(class [Microsoft.Crm.Core]Microsoft.Crm.Performance.IWebServicePerformanceCounters counters)
0x2fa4  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x2fa9  brfalse.s loc_2FB7
0x2fab  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x2fb0  ldc.i4.1
0x2fb1  ldc.i4.0
0x2fb2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool, int32)
0x2fb7  ldloc.s  5
0x2fb9  stloc.s  9
0x2fbb  leave.s  loc_2FC5
0x2fbd  ldloc.2
0x2fbe  call     void Microsoft.Crm.Sdk.InProcessCrmService::HandleException(class [mscorlib]System.Exception e, class [Microsoft.Crm.Core]Microsoft.Crm.Performance.IWebServicePerformanceCounters counters)
0x2fc3  rethrow
0x2fc5  ldloc.s  9
0x2fc7  ret
```
