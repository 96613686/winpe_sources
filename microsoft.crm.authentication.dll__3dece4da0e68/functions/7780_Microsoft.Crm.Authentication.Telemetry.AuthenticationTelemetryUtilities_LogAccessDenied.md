# Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied

- ea: `0x7780`
- end: `0x782b`
- name: `Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied`
- size: `171`
- prototype: ``
- caller_count: `28`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xc70`
- `0xe40`
- `0x2330`
- `0x2f90`
- `0x31b0`
- `0x38c0`
- `0x3950`
- `0x4620`
- `0x6730`
- `0x67e0`
- `0x7ff0`
- `0x9290`
- `0x93f0`
- `0x9550`
- `0x95c0`
- `0xc580`
- `0xcba0`
- `0xd2d0`
- `0xd4a0`
- `0xd660`
- `0xe910`
- `0xec70`
- `0xef20`
- `0xfbd0`
- `0x14150`
- `0x14d30`
- `0x14f50`
- `0x15130`

## callees

- `0x73e0`
- `0x7500`
- `0x7780`
- `0x7aa0`
- `0x7be0`
- `0x14540`
- `0x14560`
- `0x14580`
- `0x145a0`
- `0x145c0`

## string_xrefs

- `0x77c0`: `AccessDenied. HostName: {0}, UserId: {1}, AppId: {2}, Context: {3}, TicketId: {4}`
- `0x7814`: `AuthenticationTelemetryUtilities.LogAccessDenied: exception thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7780  ldnull
0x7781  call     class RuntimeContext Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::GetRuntimeContext([opt] class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal)
0x7786  stloc.0
0x7787  ldarg.0
0x7788  ldloc.0
0x7789  call     string Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::buildContext(string context, class RuntimeContext runtimeContext)
0x778e  stloc.1
0x778f  call     class Microsoft.Crm.Authentication.Telemetry.AuthenticationEventSource Microsoft.Crm.Authentication.Telemetry.AuthenticationEventSource::get_Instance()
0x7794  ldloc.0
0x7795  callvirt instance string RuntimeContext::get_HostName()
0x779a  ldloc.0
0x779b  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_OrganizationId()
0x77a0  ldloc.0
0x77a1  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_UserId()
0x77a6  ldloc.0
0x77a7  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_AppId()
0x77ac  ldloc.1
0x77ad  ldloc.0
0x77ae  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_TicketId()
0x77b3  callvirt instance void Microsoft.Crm.Authentication.Telemetry.AuthenticationEventSource::AccessDenied(string hostName, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid appId, string context, valuetype [mscorlib]System.Guid ticketId)
0x77b8  ldloc.0
0x77b9  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_OrganizationId()
0x77be  ldc.i4.s 0x16
0x77c0  ldstr    aAccessdeniedHo// "AccessDenied. HostName: {0}, UserId: {1"...
0x77c5  ldc.i4.5
0x77c6  newarr   [mscorlib]System.Object
0x77cb  dup
0x77cc  ldc.i4.0
0x77cd  ldloc.0
0x77ce  callvirt instance string RuntimeContext::get_HostName()
0x77d3  stelem.ref
0x77d4  dup
0x77d5  ldc.i4.1
0x77d6  ldloc.0
0x77d7  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_UserId()
0x77dc  box      [mscorlib]System.Guid
0x77e1  stelem.ref
0x77e2  dup
0x77e3  ldc.i4.2
0x77e4  ldloc.0
0x77e5  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_AppId()
0x77ea  box      [mscorlib]System.Guid
0x77ef  stelem.ref
0x77f0  dup
0x77f1  ldc.i4.3
0x77f2  ldarg.0
0x77f3  stelem.ref
0x77f4  dup
0x77f5  ldc.i4.4
0x77f6  ldloc.0
0x77f7  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_TicketId()
0x77fc  box      [mscorlib]System.Guid
0x7801  stelem.ref
0x7802  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7807  leave.s  loc_782A
0x7809  stloc.2
0x780a  ldloc.2
0x780b  ldloc.0
0x780c  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_OrganizationId()
0x7811  ldc.i4.s 0x16
0x7813  ldc.i4.1
0x7814  ldstr    aAuthentication_6// "AuthenticationTelemetryUtilities.LogAcc"...
0x7819  ldc.i4.1
0x781a  newarr   [mscorlib]System.Object
0x781f  dup
0x7820  ldc.i4.0
0x7821  ldloc.2
0x7822  stelem.ref
0x7823  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x7828  leave.s  loc_782A
0x782a  ret
```
