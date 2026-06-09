# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::HandleRejectedAccess

- ea: `0xe910`
- end: `0xe9ea`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::HandleRejectedAccess`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15130`

## callees

- `0x7780`
- `0xc2e0`
- `0xc3e0`
- `0xe910`

## string_xrefs

- `0xe94b`: `CrmSessionAuthenticationManager.HandleRejectedAccess: re-directing request: {0} because of expired token: {1}`
- `0xe9a8`: `CrmSessionAuthenticationManager.HandleRejectedAccess: rejecting non-user interactive request: {0} because of expired token: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe910  ldarg.0
0xe911  ldstr    aContext// "context"
0xe916  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe91b  ldarg.0
0xe91c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe921  ldstr    aContextRequest// "context.Request"
0xe926  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe92b  ldarg.1
0xe92c  isinst   [System.IdentityModel.Services]System.IdentityModel.Services.FederatedSessionExpiredException
0xe931  stloc.0
0xe932  ldloc.0
0xe933  brfalse.s loc_E9A3
0xe935  ldarg.0
0xe936  ldc.i4.1
0xe937  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::IsPageExcluded(class [System.Web]System.Web.HttpContext context, bool includeSpecialPages)
0xe93c  brtrue.s loc_E9A3
0xe93e  ldarg.0
0xe93f  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyPageIfNotAuthenticated(class [System.Web]System.Web.HttpContext context)
0xe944  brtrue.s loc_E9A3
0xe946  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe94b  ldstr    aCrmsessionauth_4// "CrmSessionAuthenticationManager.HandleR"...
0xe950  ldc.i4.2
0xe951  newarr   [mscorlib]System.Object
0xe956  dup
0xe957  ldc.i4.0
0xe958  ldarg.0
0xe959  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe95e  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xe963  stelem.ref
0xe964  dup
0xe965  ldc.i4.1
0xe966  ldloc.0
0xe967  stelem.ref
0xe968  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe96d  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xe972  ldarg.0
0xe973  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0xe978  ldstr    aOrganizationid// "organizationId"
0xe97d  ldarg.2
0xe97e  box      [mscorlib]System.Guid
0xe983  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xe988  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe98d  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0xe992  ldstr    aAuthentication_13// "AuthenticationState"
0xe997  ldc.i4.4
0xe998  box      Microsoft.Crm.Authentication.Engine.AuthenticationState
0xe99d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xe9a2  ret
0xe9a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe9a8  ldstr    aCrmsessionauth_5// "CrmSessionAuthenticationManager.HandleR"...
0xe9ad  ldc.i4.2
0xe9ae  newarr   [mscorlib]System.Object
0xe9b3  dup
0xe9b4  ldc.i4.0
0xe9b5  ldarg.0
0xe9b6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe9bb  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xe9c0  stelem.ref
0xe9c1  dup
0xe9c2  ldc.i4.1
0xe9c3  ldloc.0
0xe9c4  stelem.ref
0xe9c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe9ca  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xe9cf  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe9d4  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0xe9d9  ldstr    aAuthentication_13// "AuthenticationState"
0xe9de  ldc.i4.3
0xe9df  box      Microsoft.Crm.Authentication.Engine.AuthenticationState
0xe9e4  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xe9e9  ret
```
