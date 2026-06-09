# <>c__DisplayClass5_0::<AuthenticateSessionSecurityToken>b__0

- ea: `0x15130`
- end: `0x154fb`
- name: `<>c__DisplayClass5_0::<AuthenticateSessionSecurityToken>b__0`
- size: `971`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xb90`
- `0xc70`
- `0xcc0`
- `0xf30`
- `0xfb0`
- `0x10e0`
- `0x1180`
- `0x1380`
- `0x27a0`
- `0x7780`
- `0x7d90`
- `0x7ff0`
- `0xc2b0`
- `0xc3e0`
- `0xe200`
- `0xe360`
- `0xe8d0`
- `0xe910`
- `0xea80`
- `0xeae0`
- `0x15130`

## string_xrefs

- `0x15199`: `CrmSessionAuthenticationManager.AuthenticateSessionSecurityToken: IP request received`
- `0x151f2`: `CrmSessionAuthenticationManager.AuthenticateSessionSecurityToken: empty OrganizationId returned from CrmAuthorizationUtility.GetRequestedOrganization()`
- `0x153f8`: `http://schemas.microsoft.com/identity/claims/puid`
- `0x15477`: `CrmSessionAuthenticationManager.AuthenticateSessionSecurityToken():  invalid identity`

## pseudocode

```c

```

## disassembly

```asm
0x15130  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15135  stloc.0
0x15136  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x1513b  brfalse.s loc_1518D
0x1513d  ldstr    aClaimsauthengi// "ClaimsAuthEngine_BEGIN_EXECUTE"
0x15142  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x15147  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x1514c  ldc.i4.3
0x1514d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15152  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15157  ldstr    aClaimssessiona// "ClaimsSessionAuth: {0}"
0x1515c  ldc.i4.1
0x1515d  newarr   [mscorlib]System.Object
0x15162  dup
0x15163  ldc.i4.0
0x15164  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15169  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1516e  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x15173  stelem.ref
0x15174  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15179  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1517e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x15183  callvirt instance int32 [System.Web]System.Web.HttpRequest::get_TotalBytes()
0x15188  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnBeginRequest(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceTraceType, valuetype [mscorlib]System.Guid, string, int32)
0x1518d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15192  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyIfIPRequest(class [System.Web]System.Web.HttpContext context)
0x15197  brfalse.s loc_151B2
0x15199  ldstr    aCrmsessionauth_6// "CrmSessionAuthenticationManager.Authent"...
0x1519e  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x151a3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x151a8  call     void Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::RejectRequest(class [System.Web]System.Web.HttpContext context)
0x151ad  leave    loc_154FA
0x151b2  ldc.i4.0
0x151b3  stloc.1
0x151b4  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OnlinePortalRequest()
0x151b9  brtrue.s loc_1520B
0x151bb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x151c0  ldc.i4.0
0x151c1  call     bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::IsPageExcluded(class [System.Web]System.Web.HttpContext context, bool includeSpecialPages)
0x151c6  brtrue.s loc_1520B
0x151c8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x151cd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x151d2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganization(class [System.Web]System.Web.HttpRequest request)
0x151d7  stloc.0
0x151d8  ldloc.0
0x151d9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x151de  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x151e3  brfalse.s loc_1520B
0x151e5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x151ea  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x151ef  ldc.i4.2
0x151f0  bne.un.s loc_1520B
0x151f2  ldstr    aCrmsessionauth_7// "CrmSessionAuthenticationManager.Authent"...
0x151f7  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x151fc  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15201  call     void Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::RejectRequest(class [System.Web]System.Web.HttpContext context)
0x15206  leave    loc_154FA
0x1520b  ldarg.0
0x1520c  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x15211  ldarg.0
0x15212  ldfld    class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken <>c__DisplayClass5_0::sessionToken
0x15217  call     instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::ValidateSessionToken(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken)
0x1521c  call     T0x2B000022
0x15221  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0x15226  stloc.2
0x15227  ldloc.2
0x15228  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0x1522d  stloc.3
0x1522e  ldc.i4.0
0x1522f  stloc.s  4
0x15231  ldloc.0
0x15232  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15237  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1523c  brfalse.s loc_1524B
0x1523e  ldarg.0
0x1523f  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x15244  ldloc.3
0x15245  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::TryGetDefaultOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal userPrincipal)
0x1524a  stloc.0
0x1524b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15250  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsReportWebResource(class [System.Web]System.Web.HttpContext context)
0x15255  brfalse.s loc_15274
0x15257  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1525c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::TryFindOrgIdByReferrer(class [System.Web]System.Web.HttpContext context)
0x15261  stloc.s  5
0x15263  ldloc.s  5
0x15265  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1526a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1526f  brfalse.s loc_15274
0x15271  ldloc.s  5
0x15273  stloc.0
0x15274  ldloc.2
0x15275  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::get_IsAuthenticated()
0x1527a  brfalse  loc_1548D
0x1527f  ldloc.2
0x15280  ldloc.0
0x15281  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x15286  ldloc.0
0x15287  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1528c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15291  brfalse.s loc_15297
0x15293  ldc.i4.1
0x15294  stloc.1
0x15295  br.s     loc_152EB
0x15297  ldloc.0
0x15298  call     void Microsoft.Crm.Authentication.CrmAuthorizationUtility::HandleLiveBehavior(valuetype [mscorlib]System.Guid organizationId)
0x1529d  ldloc.2
0x1529e  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::get_IsAuthenticated()
0x152a3  brfalse.s loc_152EB
0x152a5  ldloc.3
0x152a6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x152ab  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x152b0  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x152b5  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x152ba  ldstr    aPassiveauthent// "PassiveAuthentication"
0x152bf  newobj   instance void [System.IdentityModel]System.Security.Claims.AuthorizationContext::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal, string, string)
0x152c4  stloc.s  6
0x152c6  ldarg.0
0x152c7  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x152cc  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.HttpModuleBase::get_FederationConfiguration()
0x152d1  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration::get_IdentityConfiguration()
0x152d6  callvirt instance class [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_ClaimsAuthorizationManager()
0x152db  ldloc.s  6
0x152dd  callvirt instance bool [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager::CheckAccess(class [System.IdentityModel]System.Security.Claims.AuthorizationContext)
0x152e2  brfalse.s loc_152E8
0x152e4  ldc.i4.1
0x152e5  stloc.1
0x152e6  br.s     loc_152EB
0x152e8  ldc.i4.1
0x152e9  stloc.s  4
0x152eb  ldloc.1
0x152ec  brfalse.s loc_15326
0x152ee  ldarg.0
0x152ef  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x152f4  ldloc.3
0x152f5  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::SetCurrentIdentity(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x152fa  ldloc.0
0x152fb  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsFeatureCustomSessionDurationEnabled(valuetype [mscorlib]System.Guid orgId)
0x15300  brtrue.s loc_15326
0x15302  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15307  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1530c  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0x15311  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15316  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x1531b  ldarg.0
0x1531c  ldfld    class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken <>c__DisplayClass5_0::sessionToken
0x15321  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x15326  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1532b  call     bool Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::IsSignOutRequest(class [System.Web]System.Web.HttpContext context)
0x15330  brtrue   loc_153B8
0x15335  ldarg.0
0x15336  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x1533b  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.HttpModuleBase::get_FederationConfiguration()
0x15340  callvirt instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfiguration::get_IdentityConfiguration()
0x15345  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlers()
0x1534a  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0x1534f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15354  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0x15359  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler
0x1535e  stloc.s  7
0x15360  ldloc.s  7
0x15362  ldloc.3
0x15363  ldarg.0
0x15364  ldfld    bool <>c__DisplayClass5_0::writeCookie
0x15369  ldarg.0
0x1536a  ldflda   class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken <>c__DisplayClass5_0::sessionToken
0x1536f  call     bool Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::AdjustSessionTokenLifetime(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler handler, class [mscorlib]System.Security.Claims.ClaimsPrincipal userPrincipal, bool isNewSession, class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken& sessionToken)
0x15374  stloc.s  8
0x15376  ldarg.0
0x15377  ldfld    bool <>c__DisplayClass5_0::writeCookie
0x1537c  ldloc.s  8
0x1537e  or
0x1537f  brfalse.s loc_153B8
0x15381  ldarg.0
0x15382  ldarg.0
0x15383  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x15388  ldloc.s  7
0x1538a  ldarg.0
0x1538b  ldfld    class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken <>c__DisplayClass5_0::sessionToken
0x15390  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteSessionTokenToCrmCookie(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler handler, class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken sessionToken)
0x15395  stfld    class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken <>c__DisplayClass5_0::sessionToken
0x1539a  ldarg.0
0x1539b  ldfld    bool <>c__DisplayClass5_0::writeCookie
0x153a0  brfalse.s loc_153B8
0x153a2  ldloc.3
0x153a3  call     void Microsoft.Crm.Authentication.CrmAuthorizationUtility::AuditSupportUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x153a8  ldloc.3
0x153a9  call     void Microsoft.Crm.Authentication.CrmAuthorizationUtility::AuditDelegatedAdminUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x153ae  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x153b3  call     void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionManagementCookie(class [System.Web]System.Web.HttpContext context)
0x153b8  ldloc.s  4
0x153ba  brfalse  loc_15474
0x153bf  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x153c4  call     bool Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsWabRequest(class [System.Web]System.Web.HttpContext context)
0x153c9  brtrue   loc_15474
0x153ce  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x153d3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x153d8  ldc.i4.2
0x153d9  bne.un   loc_15474
0x153de  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x153e3  ldloc.0
0x153e4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x153e9  brfalse.s loc_15456
0x153eb  ldarg.0
0x153ec  ldfld    class Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager <>c__DisplayClass5_0::<>4__this
0x153f1  ldloc.3
0x153f2  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::SetCurrentIdentity(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x153f7  ldloc.3
0x153f8  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/identity/c"...
0x153fd  callvirt instance class [mscorlib]System.Security.Claims.Claim [mscorlib]System.Security.Claims.ClaimsPrincipal::FindFirst(string)
0x15402  dup
0x15403  brtrue.s loc_15409
0x15405  pop
0x15406  ldnull
0x15407  br.s     loc_1540E
0x15409  call     instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x1540e  stloc.s  9
0x15410  ldloc.s  9
0x15412  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15417  brtrue.s loc_15446
0x15419  ldloc.s  9
0x1541b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15420  ldc.i4.s 0x10
0x15422  beq.s    loc_15446
0x15424  ldloc.0
0x15425  ldc.i4.s 0x16
0x15427  ldstr    aUserHasNonStan// "User has non-standard PUID format. PUID"...
0x1542c  ldc.i4.1
0x1542d  newarr   [mscorlib]System.Object
0x15432  dup
0x15433  ldc.i4.0
0x15434  ldloc.s  9
0x15436  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1543b  box      [mscorlib]System.Int32
0x15440  stelem.ref
0x15441  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15446  ldloc.0
0x15447  ldstr    aNotmemberoforg// "notMemberOfOrg"
0x1544c  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::RedirectToAppPortalNotificationUrl(valuetype [mscorlib]System.Guid, string)
0x15451  leave    loc_154FA
0x15456  ldstr    aSignin// "signin"
0x1545b  ldloc.0
0x1545c  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.PortalRedirector::BuildUrl(string, valuetype [mscorlib]System.Guid)
0x15461  stloc.s  0xA
0x15463  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15468  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x1546d  ldloc.s  0xA
0x1546f  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x15474  ldloc.1
0x15475  brtrue.s loc_1548D
0x15477  ldstr    aCrmsessionauth_8// "CrmSessionAuthenticationManager.Authent"...
0x1547c  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x15481  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x15486  ldnull
0x15487  ldloc.0
0x15488  call     void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::HandleRejectedAccess(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Exception exception, valuetype [mscorlib]System.Guid orgId)
0x1548d  leave.s  loc_154FA
0x1548f  stloc.s  0xB
0x15491  ldloc.s  0xB
0x15493  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::HandleAuthenticationException(class [mscorlib]System.Exception ex)
0x15498  brfalse.s loc_154A7
0x1549a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1549f  ldloc.s  0xB
0x154a1  ldloc.0
0x154a2  call     void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::HandleRejectedAccess(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Exception exception, valuetype [mscorlib]System.Guid orgId)
0x154a7  leave.s  loc_154FA
0x154a9  stloc.s  0xC
0x154ab  ldloc.s  0xC
0x154ad  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::HandleAuthenticationException(class [mscorlib]System.Exception ex)
0x154b2  brfalse.s loc_154C1
0x154b4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x154b9  ldloc.s  0xC
0x154bb  ldloc.0
0x154bc  call     void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::HandleRejectedAccess(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Exception exception, valuetype [mscorlib]System.Guid orgId)
0x154c1  leave.s  loc_154FA
0x154c3  stloc.s  0xD
0x154c5  ldloc.s  0xD
0x154c7  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::HandleAuthenticationException(class [mscorlib]System.Exception ex)
0x154cc  brfalse.s loc_154DB
0x154ce  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x154d3  ldloc.s  0xD
0x154d5  ldloc.0
0x154d6  call     void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::HandleRejectedAccess(class [System.Web]System.Web.HttpContext context, class [mscorlib]System.Exception exception, valuetype [mscorlib]System.Guid orgId)
0x154db  leave.s  loc_154FA
0x154dd  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x154e2  brfalse.s loc_154F9
0x154e4  ldstr    aClaimsauthengi_0// "ClaimsAuthEngine_END_EXECUTE"
0x154e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x154ee  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x154f3  ldc.i4.1
0x154f4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool)
0x154f9  endfinally
0x154fa  ret
```
