# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::TryReadAndValidateToken

- ea: `0xef20`
- end: `0xf1b1`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::TryReadAndValidateToken`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xcc0`
- `0x1570`
- `0x1590`
- `0x3120`
- `0x5f30`
- `0x7780`
- `0x85b0`
- `0xee70`
- `0xee90`
- `0xef20`
- `0xf200`
- `0xf230`
- `0xf730`
- `0xf740`
- `0xf750`

## string_xrefs

- `0xef21`: `accessToken`
- `0xef9d`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. S2S token. App cannot access discovery service.`
- `0xf05f`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. S2S token. ValidateServiceApplication failed.`
- `0xf110`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. S2S token. appUserInfo invalid. Reason:{0}`
- `0xf175`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. ClaimsAuthorizationManager.CheckAccess failed.`
- `0xf181`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. OrganizationId is Empty.`
- `0xf199`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. ClaimsPrincipal is null.`
- `0xf1a5`: `HttpHeaderTokenAuthenticator.TryReadAndValidateToken: failed. Token is null.`

## pseudocode

```c

```

## disassembly

```asm
0xef20  ldarg.1
0xef21  ldstr    aAccesstoken// "accessToken"
0xef26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xef2b  ldc.i4.0
0xef2c  stloc.0
0xef2d  ldarg.2
0xef2e  ldnull
0xef2f  stind.ref
0xef30  ldarg.0
0xef31  call     instance class Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::get_Handler()
0xef36  ldarg.1
0xef37  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler::ReadToken(string rawToken)
0xef3c  stloc.1
0xef3d  ldloc.1
0xef3e  brfalse  loc_F1A5
0xef43  ldarg.0
0xef44  call     instance class Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::get_Handler()
0xef49  ldloc.1
0xef4a  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token)
0xef4f  stloc.2
0xef50  ldloc.2
0xef51  brfalse  loc_F199
0xef56  ldarg.0
0xef57  call     instance bool Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::get_SetCrmIdentityClaims()
0xef5c  brfalse  loc_F18D
0xef61  ldloc.1
0xef62  call     bool Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ShouldValidateServiceApplication(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token)
0xef67  stloc.s  4
0xef69  ldloc.2
0xef6a  call     string [Microsoft.Crm.Core]IdentityExtensions::GetUserPrincipalName(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xef6f  stloc.s  5
0xef71  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_IsDiscoveryRequest()
0xef76  brtrue.s loc_EF99
0xef78  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xef7d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xef82  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xef87  callvirt instance string [System]System.Uri::get_AbsolutePath()
0xef8c  ldstr    aDiscoverySvcWe// "Discovery.svc/web"
0xef91  ldc.i4.5
0xef92  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xef97  brfalse.s loc_EFC5
0xef99  ldloc.s  4
0xef9b  brfalse.s loc_EFA9
0xef9d  ldstr    aHttpheadertoke// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xefa2  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xefa7  ldc.i4.0
0xefa8  ret
0xefa9  ldloc.s  5
0xefab  call     string Microsoft.Crm.Authentication.FederatedUserInformation::GetUserToken(string userPrincipalName)
0xefb0  dup
0xefb1  ldstr    aUserauth// "userAuth"
0xefb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xefbb  ldloc.2
0xefbc  ldc.i4.0
0xefbd  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgId(string userAuth, class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0xefc2  stloc.3
0xefc3  br.s     loc_EFD5
0xefc5  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xefca  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xefcf  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganization(class [System.Web]System.Web.HttpRequest request)
0xefd4  stloc.3
0xefd5  ldloc.3
0xefd6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xefdb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xefe0  brfalse  loc_F181
0xefe5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xefea  pop
0xefeb  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xeff0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xeff5  ldc.i4.2
0xeff6  bne.un.s loc_F04D
0xeff8  ldloc.1
0xeff9  isinst   Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken
0xeffe  stloc.s  6
0xf000  ldloc.s  6
0xf002  brfalse.s loc_F04D
0xf004  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0xf009  ldloc.3
0xf00a  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0xf00f  stloc.s  7
0xf011  ldloca.s 7
0xf013  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xf018  brtrue.s loc_F03E
0xf01a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf01f  ldstr    aTheTenantIdWas_0// "The tenant id was not found for the req"...
0xf024  ldc.i4.1
0xf025  newarr   [mscorlib]System.Object
0xf02a  dup
0xf02b  ldc.i4.0
0xf02c  ldloc.3
0xf02d  box      [mscorlib]System.Guid
0xf032  stelem.ref
0xf033  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf038  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0xf03d  throw
0xf03e  ldloc.s  6
0xf040  ldloca.s 7
0xf042  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xf047  ldloc.3
0xf048  call     void Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::ValidateIssuedLatteOrganization(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken jwt, valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid organizationId)
0xf04d  ldloc.s  4
0xf04f  brfalse  loc_F12F
0xf054  ldloc.1
0xf055  ldloc.3
0xf056  ldloca.s 8
0xf058  call     bool Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ValidateServiceApplication(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token, valuetype [mscorlib]System.Guid organizationId, [out] valuetype Microsoft.Crm.Authentication.CrmUserInfo& crmUser)
0xf05d  brtrue.s loc_F06B
0xf05f  ldstr    aHttpheadertoke_0// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xf064  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xf069  ldc.i4.0
0xf06a  ret
0xf06b  ldloca.s 8
0xf06d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0xf072  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf077  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf07c  brfalse.s loc_F0C2
0xf07e  ldloca.s 8
0xf080  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_OrganizationId()
0xf085  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf08a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf08f  brfalse.s loc_F0C2
0xf091  ldloca.s 8
0xf093  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0xf098  pop
0xf099  ldloc.2
0xf09a  ldloca.s 8
0xf09c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_OrganizationId()
0xf0a1  call     void [Microsoft.Crm.Core]IdentityExtensions::SetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0xf0a6  ldloc.2
0xf0a7  ldloca.s 8
0xf0a9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0xf0ae  call     void [Microsoft.Crm.Core]IdentityExtensions::SetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0xf0b3  ldarg.2
0xf0b4  ldloc.2
0xf0b5  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xf0ba  stind.ref
0xf0bb  ldc.i4.1
0xf0bc  stloc.0
0xf0bd  br       loc_F1AF
0xf0c2  ldsfld   string [mscorlib]System.String::Empty
0xf0c7  stloc.s  9
0xf0c9  ldloca.s 8
0xf0cb  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0xf0d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0d5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf0da  brfalse.s loc_F0EA
0xf0dc  ldloc.s  9
0xf0de  ldstr    aUseridIsEmpty// " UserId is empty"
0xf0e3  call     string [mscorlib]System.String::Concat(string, string)
0xf0e8  stloc.s  9
0xf0ea  ldloca.s 8
0xf0ec  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_OrganizationId()
0xf0f1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0f6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf0fb  brfalse.s loc_F10B
0xf0fd  ldloc.s  9
0xf0ff  ldstr    aOrganizationid_0// " OrganizationId is empty"
0xf104  call     string [mscorlib]System.String::Concat(string, string)
0xf109  stloc.s  9
0xf10b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf110  ldstr    aHttpheadertoke_1// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xf115  ldc.i4.1
0xf116  newarr   [mscorlib]System.Object
0xf11b  dup
0xf11c  ldc.i4.0
0xf11d  ldloc.s  9
0xf11f  stelem.ref
0xf120  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf125  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xf12a  br       loc_F1AF
0xf12f  ldloc.2
0xf130  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xf135  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xf13a  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xf13f  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xf144  ldstr    aHeaderauthenti// "HeaderAuthentication"
0xf149  newobj   instance void [System.IdentityModel]System.Security.Claims.AuthorizationContext::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal, string, string)
0xf14e  stloc.s  0xA
0xf150  ldarg.0
0xf151  call     instance class Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::get_Handler()
0xf156  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.IHttpHeaderTokenHandler::get_IdentityConfiguration()
0xf15b  callvirt instance class [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_ClaimsAuthorizationManager()
0xf160  ldloc.s  0xA
0xf162  callvirt instance bool [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager::CheckAccess(class [System.IdentityModel]System.Security.Claims.AuthorizationContext)
0xf167  brfalse.s loc_F175
0xf169  ldarg.2
0xf16a  ldloc.2
0xf16b  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xf170  stind.ref
0xf171  ldc.i4.1
0xf172  stloc.0
0xf173  br.s     loc_F1AF
0xf175  ldstr    aHttpheadertoke_2// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xf17a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xf17f  br.s     loc_F1AF
0xf181  ldstr    aHttpheadertoke_3// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xf186  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xf18b  br.s     loc_F1AF
0xf18d  ldarg.2
0xf18e  ldloc.2
0xf18f  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xf194  stind.ref
0xf195  ldc.i4.1
0xf196  stloc.0
0xf197  br.s     loc_F1AF
0xf199  ldstr    aHttpheadertoke_4// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xf19e  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xf1a3  br.s     loc_F1AF
0xf1a5  ldstr    aHttpheadertoke_5// "HttpHeaderTokenAuthenticator.TryReadAnd"...
0xf1aa  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xf1af  ldloc.0
0xf1b0  ret
```
