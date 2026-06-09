# Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog_0

- ea: `0x7680`
- end: `0x7778`
- name: `Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog_0`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x6a90`
- `0x7670`

## callees

- `0x73e0`
- `0x7440`
- `0x7680`
- `0x7aa0`
- `0x7be0`
- `0x14540`
- `0x14560`
- `0x14580`
- `0x145a0`
- `0x145c0`

## string_xrefs

- `0x7761`: `AuthenticationTelemetryUtilities.WriteEventLog: exception thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7680  ldarg.2
0x7681  call     class RuntimeContext Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::GetRuntimeContext([opt] class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal)
0x7686  stloc.0
0x7687  ldarg.3
0x7688  ldloc.0
0x7689  call     string Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::buildContext(string context, class RuntimeContext runtimeContext)
0x768e  stloc.1
0x768f  call     class Microsoft.Crm.Authentication.Telemetry.AuthenticationEventSource Microsoft.Crm.Authentication.Telemetry.AuthenticationEventSource::get_Instance()
0x7694  ldloc.0
0x7695  callvirt instance string RuntimeContext::get_HostName()
0x769a  ldloc.0
0x769b  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_OrganizationId()
0x76a0  ldloc.0
0x76a1  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_UserId()
0x76a6  ldloc.0
0x76a7  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_AppId()
0x76ac  ldarga.s 0
0x76ae  constrained. [System]System.Diagnostics.EventLogEntryType
0x76b4  callvirt instance string [mscorlib]System.Object::ToString()
0x76b9  ldarg.0
0x76ba  ldarga.s 1
0x76bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x76c1  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x76c6  ldarg.1
0x76c7  ldloc.1
0x76c8  ldarg.s  4
0x76ca  brtrue.s loc_76D3
0x76cc  ldsfld   string [mscorlib]System.String::Empty
0x76d1  br.s     loc_76DA
0x76d3  ldarg.s  4
0x76d5  callvirt instance string [mscorlib]System.Object::ToString()
0x76da  ldloc.0
0x76db  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_TicketId()
0x76e0  callvirt instance void Microsoft.Crm.Authentication.Telemetry.AuthenticationEventSource::EventLogEventWritten(string hostName, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid appId, string eventLevel, int32 eventLevelNumericValue, string id, int64 idNumericValue, string context, string exception, valuetype [mscorlib]System.Guid ticketId)
0x76e5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::NewEventLog()
0x76ea  stloc.2
0x76eb  ldloc.2
0x76ec  ldstr    aMscrmauthentic// "MSCRMAuthentication"
0x76f1  ldarg.0
0x76f2  ldarg.1
0x76f3  ldc.i4.7
0x76f4  newarr   [mscorlib]System.Object
0x76f9  dup
0x76fa  ldc.i4.0
0x76fb  ldloc.0
0x76fc  callvirt instance string RuntimeContext::get_HostName()
0x7701  stelem.ref
0x7702  dup
0x7703  ldc.i4.1
0x7704  ldloc.0
0x7705  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_OrganizationId()
0x770a  box      [mscorlib]System.Guid
0x770f  stelem.ref
0x7710  dup
0x7711  ldc.i4.2
0x7712  ldloc.0
0x7713  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_UserId()
0x7718  box      [mscorlib]System.Guid
0x771d  stelem.ref
0x771e  dup
0x771f  ldc.i4.3
0x7720  ldloc.0
0x7721  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_AppId()
0x7726  box      [mscorlib]System.Guid
0x772b  stelem.ref
0x772c  dup
0x772d  ldc.i4.4
0x772e  ldloc.1
0x772f  stelem.ref
0x7730  dup
0x7731  ldc.i4.5
0x7732  ldarg.s  4
0x7734  stelem.ref
0x7735  dup
0x7736  ldc.i4.6
0x7737  ldloc.0
0x7738  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_TicketId()
0x773d  box      [mscorlib]System.Guid
0x7742  stelem.ref
0x7743  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x7748  leave.s  loc_7754
0x774a  ldloc.2
0x774b  brfalse.s loc_7753
0x774d  ldloc.2
0x774e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7753  endfinally
0x7754  leave.s  loc_7777
0x7756  stloc.3
0x7757  ldloc.3
0x7758  ldloc.0
0x7759  callvirt instance valuetype [mscorlib]System.Guid RuntimeContext::get_OrganizationId()
0x775e  ldc.i4.s 0x16
0x7760  ldc.i4.1
0x7761  ldstr    aAuthentication_5// "AuthenticationTelemetryUtilities.WriteE"...
0x7766  ldc.i4.1
0x7767  newarr   [mscorlib]System.Object
0x776c  dup
0x776d  ldc.i4.0
0x776e  ldloc.3
0x776f  stelem.ref
0x7770  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x7775  leave.s  loc_7777
0x7777  ret
```
