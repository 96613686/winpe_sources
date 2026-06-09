# <>c__DisplayClass2_0::<OnSecurityTokenValidated>b__0

- ea: `0x14d30`
- end: `0x14db3`
- name: `<>c__DisplayClass2_0::<OnSecurityTokenValidated>b__0`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xdc0`
- `0x7780`
- `0x9140`
- `0x9180`
- `0x9a80`
- `0x14d30`

## string_xrefs

- `0x14d9d`: `CrmFederatedAuthenticationModule.OnSecurityTokenValidated nonce was not valid, cancelling the request and let it go through identity provider signin flow.`

## pseudocode

```c

```

## disassembly

```asm
0x14d30  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x14d35  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x14d3a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganizationFromReplyContext(class [System.Web]System.Web.HttpRequest request)
0x14d3f  call     bool Microsoft.Crm.Authentication.Claims.NonceSessionSettings::NonceRequiredForSignOn(valuetype [mscorlib]System.Guid orgId)
0x14d44  brtrue.s loc_14D47
0x14d46  ret
0x14d47  call     class Microsoft.Crm.Authentication.Claims.INonceProtocolValidator Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_Instance()
0x14d4c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x14d51  ldarg.0
0x14d52  ldfld    class [System.IdentityModel.Services]System.IdentityModel.Services.SecurityTokenValidatedEventArgs <>c__DisplayClass2_0::e
0x14d57  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel.Services]System.IdentityModel.Services.SecurityTokenValidatedEventArgs::get_ClaimsPrincipal()
0x14d5c  callvirt instance bool Microsoft.Crm.Authentication.Claims.INonceProtocolValidator::ValidateSignOnTokenNonceForNewSession(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x14d61  stloc.0
0x14d62  ldarg.0
0x14d63  ldfld    class [System.IdentityModel.Services]System.IdentityModel.Services.SecurityTokenValidatedEventArgs <>c__DisplayClass2_0::e
0x14d68  ldloc.0
0x14d69  ldc.i4.0
0x14d6a  ceq
0x14d6c  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x14d71  ldarg.0
0x14d72  ldfld    class [System.IdentityModel.Services]System.IdentityModel.Services.SecurityTokenValidatedEventArgs <>c__DisplayClass2_0::e
0x14d77  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0x14d7c  brfalse.s loc_14DB2
0x14d7e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x14d83  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x14d88  ldstr    aAuthentication_13// "AuthenticationState"
0x14d8d  ldc.i4.3
0x14d8e  box      Microsoft.Crm.Authentication.Engine.AuthenticationState
0x14d93  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x14d98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14d9d  ldstr    aCrmfederatedau_13// "CrmFederatedAuthenticationModule.OnSecu"...
0x14da2  ldc.i4.0
0x14da3  newarr   [mscorlib]System.Object
0x14da8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14dad  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x14db2  ret
```
