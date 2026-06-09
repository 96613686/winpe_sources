# Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::GetResourceUrlFromSigninResponse

- ea: `0xd8a0`
- end: `0xd906`
- name: `Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::GetResourceUrlFromSigninResponse`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xcc40`
- `0x14f50`

## callees

- `0xcb0`
- `0xd40`
- `0xd8a0`

## pseudocode

```c

```

## disassembly

```asm
0xd8a0  ldarg.0
0xd8a1  ldarg.1
0xd8a2  call     instance string [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::GetReturnUrlFromResponse(class [System.Web]System.Web.HttpRequestBase)
0xd8a7  stloc.0
0xd8a8  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OnlinePortalRequest()
0xd8ad  brfalse.s loc_D904
0xd8af  ldloc.0
0xd8b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd8b5  brtrue.s loc_D904
0xd8b7  ldloc.0
0xd8b8  newobj   instance void [System]System.Uri::.ctor(string)
0xd8bd  stloc.1
0xd8be  ldloc.1
0xd8bf  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsOnlinePortalHomePageRequest(class [System]System.Uri uri)
0xd8c4  brtrue.s loc_D8DD
0xd8c6  ldloc.1
0xd8c7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOnlineOrganization(class [System]System.Uri requested)
0xd8cc  stloc.2
0xd8cd  ldstr    aSignin// "signin"
0xd8d2  ldc.i4.0
0xd8d3  ldloc.2
0xd8d4  ldloc.0
0xd8d5  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.PortalRedirector::BuildUrl(string, int32, valuetype [mscorlib]System.Guid, string)
0xd8da  stloc.0
0xd8db  br.s     loc_D904
0xd8dd  ldloc.1
0xd8de  callvirt instance string [System]System.Uri::get_Query()
0xd8e3  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0xd8e8  ldstr    aMscrmurl// "mscrmurl"
0xd8ed  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd8f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd8f7  brfalse.s loc_D904
0xd8f9  ldstr    aSignin// "signin"
0xd8fe  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.PortalRedirector::BuildUrl(string)
0xd903  stloc.0
0xd904  ldloc.0
0xd905  ret
```
