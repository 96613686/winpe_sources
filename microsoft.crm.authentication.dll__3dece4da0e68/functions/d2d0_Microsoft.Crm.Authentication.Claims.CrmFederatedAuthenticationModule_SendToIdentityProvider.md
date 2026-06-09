# Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::SendToIdentityProvider

- ea: `0xd2d0`
- end: `0xd462`
- name: `Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::SendToIdentityProvider`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0xd4a0`
- `0x14de0`

## callees

- `0x7780`
- `0x7ff0`
- `0x9130`
- `0x9180`
- `0x9a80`
- `0xcf40`
- `0xd250`
- `0xd2d0`
- `0xdb00`
- `0xdb20`
- `0xdb30`
- `0xdb60`
- `0xdb80`
- `0xdba0`
- `0xdc30`
- `0xdc50`

## string_xrefs

- `0xd31a`: `returnUri`

## pseudocode

```c

```

## disassembly

```asm
0xd2d0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xd2d5  stloc.0
0xd2d6  ldloc.0
0xd2d7  ldstr    aCurrent// "current"
0xd2dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd2e1  ldloc.0
0xd2e2  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xd2e7  ldstr    aResponse_0// "Response"
0xd2ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd2f1  ldc.i4.1
0xd2f2  stloc.1
0xd2f3  ldarg.1
0xd2f4  callvirt instance bool Microsoft.Crm.Authentication.Claims.RedirectLocation::get_PathBased()
0xd2f9  brtrue.s loc_D33E
0xd2fb  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OffloadingEnabled()
0xd300  brfalse.s loc_D33E
0xd302  ldarg.1
0xd303  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Location()
0xd308  ldc.i4.1
0xd309  ldloca.s 2
0xd30b  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0xd310  brfalse.s loc_D332
0xd312  ldloc.2
0xd313  call     class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationContextExtensions::UpdateUrlForOffloading(class [System]System.Uri)
0xd318  stloc.3
0xd319  ldloc.3
0xd31a  ldstr    aReturnuri// "returnUri"
0xd31f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd324  ldarg.1
0xd325  ldloc.3
0xd326  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xd32b  callvirt instance void Microsoft.Crm.Authentication.Claims.RedirectLocation::set_Location(string value)
0xd330  br.s     loc_D33E
0xd332  ldstr    aCrmfederatedau_7// "CrmFederatedAuthenticationModule.SendTo"...
0xd337  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xd33c  ldc.i4.0
0xd33d  stloc.1
0xd33e  ldloc.1
0xd33f  brfalse  loc_D456
0xd344  ldarg.0
0xd345  ldarg.1
0xd346  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_ContextId()
0xd34b  ldarg.1
0xd34c  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_Location()
0xd351  ldarg.1
0xd352  callvirt instance bool Microsoft.Crm.Authentication.Claims.RedirectLocation::get_RememberMe()
0xd357  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::CreateSignInRequest(string, string, bool)
0xd35c  newobj   instance void [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::.ctor(class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage)
0xd361  stloc.s  4
0xd363  ldarg.1
0xd364  callvirt instance bool Microsoft.Crm.Authentication.Claims.RedirectLocation::get_PathBased()
0xd369  brtrue.s loc_D375
0xd36b  ldarg.1
0xd36c  ldloc.s  4
0xd36e  call     void Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::UpdateRedirectingEventArgsNonPathBasedUrl(class Microsoft.Crm.Authentication.Claims.RedirectLocation redirectLocation, class [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs e)
0xd373  br.s     loc_D37D
0xd375  ldarg.1
0xd376  ldloc.s  4
0xd378  call     void Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::UpdateRedirectingEventArgsPathBasedUrl(class Microsoft.Crm.Authentication.Claims.RedirectLocation redirectLocation, class [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs e)
0xd37d  ldloc.s  4
0xd37f  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd384  dup
0xd385  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::get_Context()
0xd38a  ldstr    aCrmorgid_0// "&crmorgid="
0xd38f  ldarg.1
0xd390  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.RedirectLocation::get_OrganizationId()
0xd395  box      [mscorlib]System.Guid
0xd39a  call     string [mscorlib]System.String::Concat(object, object, object)
0xd39f  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::set_Context(string)
0xd3a4  ldarg.1
0xd3a5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.RedirectLocation::get_OrganizationId()
0xd3aa  call     bool Microsoft.Crm.Authentication.Claims.NonceSessionSettings::NonceRequiredForSignOn(valuetype [mscorlib]System.Guid orgId)
0xd3af  brfalse.s loc_D3EA
0xd3b1  call     class Microsoft.Crm.Authentication.Claims.INonceProtocolValidator Microsoft.Crm.Authentication.Claims.NonceProtocolValidator::get_Instance()
0xd3b6  ldloc.0
0xd3b7  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProtocolValidator::CreateAndSetNonce(class [System.Web]System.Web.HttpContext context)
0xd3bc  stloc.s  5
0xd3be  ldloc.s  5
0xd3c0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xd3c5  brtrue.s loc_D3EA
0xd3c7  ldloc.s  4
0xd3c9  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd3ce  dup
0xd3cf  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::get_Context()
0xd3d4  ldstr    aNonce_0// "&nonce="
0xd3d9  ldloc.s  5
0xd3db  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xd3e0  call     string [mscorlib]System.String::Concat(string, string, string)
0xd3e5  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationMessage::set_Context(string)
0xd3ea  ldarg.1
0xd3eb  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_HomeRealm()
0xd3f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd3f5  brtrue.s loc_D409
0xd3f7  ldloc.s  4
0xd3f9  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd3fe  ldarg.1
0xd3ff  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_HomeRealm()
0xd404  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::set_HomeRealm(string)
0xd409  ldarg.0
0xd40a  ldloc.s  4
0xd40c  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::OnRedirectingToIdentityProvider(class [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs)
0xd411  ldloc.s  4
0xd413  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xd418  brtrue.s loc_D461
0xd41a  ldarg.1
0xd41b  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_CoBrandingLocation()
0xd420  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xd425  brtrue.s loc_D43E
0xd427  ldloc.s  4
0xd429  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd42e  ldstr    aCbcxt// "cbcxt"
0xd433  ldarg.1
0xd434  callvirt instance string Microsoft.Crm.Authentication.Claims.RedirectLocation::get_CoBrandingLocation()
0xd439  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.FederationMessage::SetParameter(string, string)
0xd43e  ldloc.0
0xd43f  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xd444  ldloc.s  4
0xd446  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage [System.IdentityModel.Services]System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs::get_SignInRequestMessage()
0xd44b  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.SignInRequestMessage::get_RequestUrl()
0xd450  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xd455  ret
0xd456  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xd45b  call     void Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::RejectRequest(class [System.Web]System.Web.HttpContext context)
0xd460  ret
0xd461  ret
```
