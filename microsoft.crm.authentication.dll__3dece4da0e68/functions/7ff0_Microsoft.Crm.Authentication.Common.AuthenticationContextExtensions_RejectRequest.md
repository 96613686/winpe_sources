# Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::RejectRequest

- ea: `0x7ff0`
- end: `0x802f`
- name: `Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::RejectRequest`
- size: `63`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd2d0`
- `0xd4a0`
- `0xd660`
- `0x15130`

## callees

- `0x7780`

## string_xrefs

- `0x7ff5`: `AuthenticationContextExtensions.RejectRequest: rejecting URL '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x7ff0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7ff5  ldstr    aAuthentication_14// "AuthenticationContextExtensions.RejectR"...
0x7ffa  ldc.i4.1
0x7ffb  newarr   [mscorlib]System.Object
0x8000  dup
0x8001  ldc.i4.0
0x8002  ldarg.0
0x8003  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8008  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x800d  stelem.ref
0x800e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8013  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x8018  ldarg.0
0x8019  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x801e  ldstr    aAuthentication_13// "AuthenticationState"
0x8023  ldc.i4.3
0x8024  box      Microsoft.Crm.Authentication.Engine.AuthenticationState
0x8029  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x802e  ret
```
