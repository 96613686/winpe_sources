# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::CanHandleRequest

- ea: `0xeeb0`
- end: `0xef18`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::CanHandleRequest`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1a00`
- `0x1b30`
- `0xeeb0`
- `0xf1f0`

## pseudocode

```c

```

## disassembly

```asm
0xeeb0  ldarg.1
0xeeb1  ldstr    aRequest// "request"
0xeeb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xeebb  ldarg.1
0xeebc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0xeec1  ldstr    aAuthorization// "Authorization"
0xeec6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xeecb  call     bool Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::CanHandleRequestInternal(string authHeader)
0xeed0  brfalse.s loc_EED4
0xeed2  ldc.i4.1
0xeed3  ret
0xeed4  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0xeed9  ldarg.1
0xeeda  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xeedf  callvirt instance bool [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::ContainsSessionTokenCookie(class [System.Web]System.Web.HttpCookieCollection)
0xeee4  brfalse.s loc_EEE8
0xeee6  ldc.i4.0
0xeee7  ret
0xeee8  ldarg.1
0xeee9  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xeeee  callvirt instance string [System]System.Uri::get_AbsolutePath()
0xeef3  ldstr    aWeb// "/web"
0xeef8  ldc.i4.5
0xeef9  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xeefe  brfalse.s loc_EF02
0xef00  ldc.i4.1
0xef01  ret
0xef02  ldarg.1
0xef03  call     bool Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::IsODataV4Request(class [System.Web]System.Web.HttpRequest request)
0xef08  brfalse.s loc_EF0C
0xef0a  ldc.i4.1
0xef0b  ret
0xef0c  ldarg.1
0xef0d  call     bool Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::IsSearchRestEndpointRequest(class [System.Web]System.Web.HttpRequest request)
0xef12  brfalse.s loc_EF16
0xef14  ldc.i4.1
0xef15  ret
0xef16  ldc.i4.0
0xef17  ret
```
