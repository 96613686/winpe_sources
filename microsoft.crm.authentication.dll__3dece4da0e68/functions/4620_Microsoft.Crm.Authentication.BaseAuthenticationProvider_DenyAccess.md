# Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess

- ea: `0x4620`
- end: `0x4643`
- name: `Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2cc0`
- `0x4bf0`
- `0x6530`
- `0xc910`

## callees

- `0x45f0`
- `0x7780`

## pseudocode

```c

```

## disassembly

```asm
0x4620  ldarg.2
0x4621  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x4626  ldarg.0
0x4627  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::UpdateDenyCounter()
0x462c  ldarg.1
0x462d  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpApplication::get_Response()
0x4632  ldc.i4   0x191
0x4637  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x463c  ldarg.1
0x463d  callvirt instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x4642  ret
```
