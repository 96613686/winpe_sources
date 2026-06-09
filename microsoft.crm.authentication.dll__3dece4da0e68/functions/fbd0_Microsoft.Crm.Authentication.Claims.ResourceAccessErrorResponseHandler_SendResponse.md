# Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendResponse

- ea: `0xfbd0`
- end: `0xfc72`
- name: `Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::SendResponse`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xf780`
- `0xf940`

## callees

- `0x7780`
- `0xfbd0`

## string_xrefs

- `0xfbd5`: `ResourceAccessErrorResponseHandler.SendResponse: Rejecting claim with response '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0xfbd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfbd5  ldstr    aResourceaccess// "ResourceAccessErrorResponseHandler.Send"...
0xfbda  ldc.i4.1
0xfbdb  newarr   [mscorlib]System.Object
0xfbe0  dup
0xfbe1  ldc.i4.0
0xfbe2  ldarg.2
0xfbe3  stelem.ref
0xfbe4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfbe9  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xfbee  ldarg.0
0xfbef  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xfbf4  ldarg.1
0xfbf5  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0xfbfa  ldarg.0
0xfbfb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xfc00  ldstr    aWwwAuthenticat// "WWW-Authenticate"
0xfc05  ldarg.2
0xfc06  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0xfc0b  ldarg.0
0xfc0c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0xfc11  ldsfld   string Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryConstants::TicketId
0xfc16  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xfc1b  brfalse.s loc_FC50
0xfc1d  ldarg.0
0xfc1e  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0xfc23  ldsfld   string Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryConstants::TicketId
0xfc28  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xfc2d  unbox.any [mscorlib]System.Guid
0xfc32  stloc.0
0xfc33  ldarg.0
0xfc34  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xfc39  ldstr    aXAuthenticatio// "x-authentication-ticketid"
0xfc3e  ldloca.s 0
0xfc40  constrained. [mscorlib]System.Guid
0xfc46  callvirt instance string [mscorlib]System.Object::ToString()
0xfc4b  callvirt instance void [System.Web]System.Web.HttpResponse::AppendHeader(string, string)
0xfc50  ldarg.0
0xfc51  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0xfc56  ldstr    aAuthentication_13// "AuthenticationState"
0xfc5b  ldc.i4.3
0xfc5c  box      Microsoft.Crm.Authentication.Engine.AuthenticationState
0xfc61  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xfc66  ldarg.0
0xfc67  callvirt instance class [System.Web]System.Web.HttpApplication [System.Web]System.Web.HttpContext::get_ApplicationInstance()
0xfc6c  callvirt instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0xfc71  ret
```
