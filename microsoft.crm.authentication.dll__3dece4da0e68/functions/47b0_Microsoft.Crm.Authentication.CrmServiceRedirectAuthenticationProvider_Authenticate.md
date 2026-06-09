# Microsoft.Crm.Authentication.CrmServiceRedirectAuthenticationProvider::Authenticate

- ea: `0x47b0`
- end: `0x47f1`
- name: `Microsoft.Crm.Authentication.CrmServiceRedirectAuthenticationProvider::Authenticate`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x47b0`
- `0x4800`
- `0x78e0`

## string_xrefs

- `0x47be`: `AUTH: CrmServiceRedirectAuthenticationProvider redirects request to {0}.`
- `0x47e3`: `CrmServiceRedirectAuthenticationProvider.Authenticate()`

## pseudocode

```c

```

## disassembly

```asm
0x47b0  ldarg.0
0x47b1  call     instance string Microsoft.Crm.Authentication.CrmServiceRedirectAuthenticationProvider::GetWsdlRedirectUrl()
0x47b6  stloc.0
0x47b7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x47bc  ldc.i4.s 0x16
0x47be  ldstr    aAuthCrmservice// "AUTH: CrmServiceRedirectAuthenticationP"...
0x47c3  ldc.i4.1
0x47c4  newarr   [mscorlib]System.Object
0x47c9  dup
0x47ca  ldc.i4.0
0x47cb  ldloc.0
0x47cc  stelem.ref
0x47cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x47d2  ldarg.1
0x47d3  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x47d8  ldloc.0
0x47d9  ldc.i4.1
0x47da  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string, bool)
0x47df  ldc.i4.1
0x47e0  stloc.1
0x47e1  leave.s  loc_47EF
0x47e3  ldstr    aCrmserviceredi// "CrmServiceRedirectAuthenticationProvide"...
0x47e8  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x47ed  rethrow
0x47ef  ldloc.1
0x47f0  ret
```
