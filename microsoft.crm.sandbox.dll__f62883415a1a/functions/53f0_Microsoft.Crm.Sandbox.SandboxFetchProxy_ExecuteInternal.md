# Microsoft.Crm.Sandbox.SandboxFetchProxy::ExecuteInternal

- ea: `0x53f0`
- end: `0x54e0`
- name: `Microsoft.Crm.Sandbox.SandboxFetchProxy::ExecuteInternal`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x52f0`
- `0x53f0`

## callees

- `0x260`
- `0xf30`
- `0xf50`
- `0x1420`
- `0x14d0`
- `0x50f0`
- `0x5170`
- `0x51d0`
- `0x5370`
- `0x53f0`

## string_xrefs

- `0x5473`: `SandboxFetchProxy.ExecuteInternal:  Server: {0} has already been contacted once. Giving up.`

## pseudocode

```c

```

## disassembly

```asm
0x53f0  ldarg.s  4
0x53f2  ldarg.0
0x53f3  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.SandboxFetchProxy::get_SelectedServer()
0x53f8  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x53fd  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x5402  ldarg.0
0x5403  call     instance class Microsoft.Crm.Sandbox.InternalSandboxSdkClient Microsoft.Crm.Sandbox.SandboxFetchProxy::get_Client()
0x5408  ldarg.1
0x5409  ldarg.2
0x540a  ldarg.3
0x540b  callvirt instance unsigned int8[] Microsoft.Crm.Sandbox.InternalSandboxSdkClient::Execute(class Microsoft.Crm.Sandbox.SandboxSdkContext requestContext, string operation, unsigned int8[] serializedRequest)
0x5410  stloc.0
0x5411  leave    loc_54DE
0x5416  stloc.1
0x5417  ldloc.1
0x5418  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x541d  brfalse.s loc_5421
0x541f  rethrow
0x5421  ldarg.0
0x5422  call     instance string Microsoft.Crm.Sandbox.SandboxFetchProxy::get_PreferredServerName()
0x5427  brfalse.s loc_5451
0x5429  ldloc.1
0x542a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x542f  ldc.i4.s 0x21
0x5431  ldstr    aSandboxfetchpr_1// "SandboxFetchProxy.ExecuteInternal: Pref"...
0x5436  ldc.i4.1
0x5437  newarr   [mscorlib]System.Object
0x543c  dup
0x543d  ldc.i4.0
0x543e  ldarg.0
0x543f  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.SandboxFetchProxy::get_SelectedServer()
0x5444  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x5449  stelem.ref
0x544a  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x544f  rethrow
0x5451  ldarg.0
0x5452  call     instance void Microsoft.Crm.Sandbox.SandboxFetchProxy::InitializeClient()
0x5457  ldarg.s  4
0x5459  ldarg.0
0x545a  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.SandboxFetchProxy::get_SelectedServer()
0x545f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x5464  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x5469  brfalse.s loc_549F
0x546b  ldloc.1
0x546c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5471  ldc.i4.s 0x21
0x5473  ldstr    aSandboxfetchpr_2// "SandboxFetchProxy.ExecuteInternal:  Ser"...
0x5478  ldc.i4.1
0x5479  newarr   [mscorlib]System.Object
0x547e  dup
0x547f  ldc.i4.0
0x5480  ldarg.0
0x5481  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.SandboxFetchProxy::get_SelectedServer()
0x5486  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x548b  stelem.ref
0x548c  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5491  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::get_SandboxFetchProxyGiveUp()
0x5496  ldc.i4.1
0x5497  conv.i8
0x5498  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::ReportValue(int64)
0x549d  rethrow
0x549f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54a4  ldc.i4.s 0x21
0x54a6  ldstr    aSandboxfetchpr_3// "SandboxFetchProxy.ExecuteInternal: Retr"...
0x54ab  ldc.i4.1
0x54ac  newarr   [mscorlib]System.Object
0x54b1  dup
0x54b2  ldc.i4.0
0x54b3  ldarg.0
0x54b4  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.SandboxFetchProxy::get_SelectedServer()
0x54b9  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x54be  stelem.ref
0x54bf  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x54c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::get_SandboxFetchProxyFailureRetry()
0x54c9  ldc.i4.1
0x54ca  conv.i8
0x54cb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::ReportValue(int64)
0x54d0  ldarg.0
0x54d1  ldarg.1
0x54d2  ldarg.2
0x54d3  ldarg.3
0x54d4  ldarg.s  4
0x54d6  call     instance unsigned int8[] Microsoft.Crm.Sandbox.SandboxFetchProxy::ExecuteInternal(class Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, string requestName, unsigned int8[] serializedRequest, class [mscorlib]System.Collections.Generic.IList`1<string> contactedServers)
0x54db  stloc.0
0x54dc  leave.s  loc_54DE
0x54de  ldloc.0
0x54df  ret
```
