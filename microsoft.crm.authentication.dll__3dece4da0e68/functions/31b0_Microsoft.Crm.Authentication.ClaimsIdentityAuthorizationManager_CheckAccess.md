# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::CheckAccess

- ea: `0x31b0`
- end: `0x37fd`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::CheckAccess`
- size: `1613`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x8d0`
- `0x8f0`
- `0x1570`
- `0x1590`
- `0x1910`
- `0x1fc0`
- `0x2020`
- `0x31b0`
- `0x3800`
- `0x38c0`
- `0x3950`
- `0x7350`
- `0x7360`
- `0x7780`
- `0x78e0`

## string_xrefs

- `0x3225`: `ClaimsIdentityAuthorizationManager user was authenticated by Passive Auth Engine:  {0}`
- `0x325e`: `ClaimsIdentityAuthorizationManager.CheckAccess(): no principal found`
- `0x32ae`: `ClaimsIdentityAuthorizationManager.CheckAccess(): no identity found`
- `0x32cf`: `ClaimsIdentityAuthorizationManager.CheckAccess(): no resourceUrlClaim found`
- `0x3340`: `ClaimsIdentityAuthorizationManager.CheckAccess(): unable to establish the organization id`
- `0x33aa`: `ClaimsIdentityAuthorizationManager.CheckAccess(): unable to validate user token`
- `0x3433`: `ClaimsIdentityAuthorizationManager Authenticated user {0}`
- `0x3473`: `ClaimsIdentityAuthorizationManager.CheckAccess(): current identity is not authenticated.`
- `0x3489`: `ClaimsIdentityAuthorizationManager.CheckAccess()`
- `0x34b5`: `Org Data - AreReportsPublished	{56},AvailabilityGroupName:{0}, AverageAsyncRequestCompletionTime:{1},AverageIO:{2},AverageWebRequestCompletionTime:{3},BuildNumber:{4}, CurrentStorageSizeMB:{5}, DatabaseMirroringSetupInProgress:{6},DatabaseName:{7}, DatacenterId:{8}, DataSizeMB:{9},ExternalIdForAccountConversion:{10} ,FriendlyName:{11},HelpContentServerUrl:{12}, Id:{13} ,IsCustomEntityStateModelAware:{14} ,IsLocalReportBacklogPresent:{15} ,IsRemoteReportServerConfigured:{16} ,LastDatabaseQuickFix`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x31b5  stloc.0
0x31b6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x31bb  brfalse  loc_3254
0x31c0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x31c5  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x31ca  brfalse  loc_3254
0x31cf  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x31d4  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x31d9  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0x31de  stloc.s  6
0x31e0  ldloc.s  6
0x31e2  brfalse.s loc_3254
0x31e4  ldloc.s  6
0x31e6  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x31eb  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x31f0  brfalse.s loc_3254
0x31f2  ldloc.s  6
0x31f4  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x31f9  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0x31fe  stloc.s  7
0x3200  ldloc.s  7
0x3202  brfalse.s loc_3254
0x3204  ldloc.s  7
0x3206  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_Id()
0x320b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3210  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3215  brfalse.s loc_3254
0x3217  ldloc.s  7
0x3219  call     void Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateCallerId(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity identity)
0x321e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3223  ldc.i4.s 0x16
0x3225  ldstr    aClaimsidentity_0// "ClaimsIdentityAuthorizationManager user"...
0x322a  ldc.i4.1
0x322b  newarr   [mscorlib]System.Object
0x3230  dup
0x3231  ldc.i4.0
0x3232  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3237  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x323c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x3241  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x3246  stelem.ref
0x3247  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x324c  ldc.i4.1
0x324d  stloc.s  8
0x324f  leave    loc_37FA
0x3254  ldarg.1
0x3255  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel]System.Security.Claims.AuthorizationContext::get_Principal()
0x325a  stloc.1
0x325b  ldloc.1
0x325c  brtrue.s loc_3270
0x325e  ldstr    aClaimsidentity_1// "ClaimsIdentityAuthorizationManager.Chec"...
0x3263  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x3268  ldc.i4.0
0x3269  stloc.s  8
0x326b  leave    loc_37FA
0x3270  ldnull
0x3271  stloc.2
0x3272  ldloc.1
0x3273  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x3278  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0x327d  brfalse.s loc_328D
0x327f  ldloc.1
0x3280  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x3285  castclass [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0x328a  stloc.2
0x328b  br.s     loc_32AB
0x328d  ldloc.1
0x328e  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x3293  isinst   [mscorlib]System.Security.Claims.ClaimsIdentity
0x3298  brfalse.s loc_32AB
0x329a  ldloc.1
0x329b  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x32a0  castclass [mscorlib]System.Security.Claims.ClaimsIdentity
0x32a5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0x32aa  stloc.2
0x32ab  ldloc.2
0x32ac  brtrue.s loc_32C0
0x32ae  ldstr    aClaimsidentity_2// "ClaimsIdentityAuthorizationManager.Chec"...
0x32b3  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x32b8  ldc.i4.0
0x32b9  stloc.s  8
0x32bb  leave    loc_37FA
0x32c0  ldarg.1
0x32c1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Security.Claims.Claim> [System.IdentityModel]System.Security.Claims.AuthorizationContext::get_Resource()
0x32c6  call     T0x2B00000A
0x32cb  stloc.3
0x32cc  ldloc.3
0x32cd  brtrue.s loc_32E1
0x32cf  ldstr    aClaimsidentity_3// "ClaimsIdentityAuthorizationManager.Chec"...
0x32d4  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x32d9  ldc.i4.0
0x32da  stloc.s  8
0x32dc  leave    loc_37FA
0x32e1  ldloc.3
0x32e2  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x32e7  newobj   instance void [System]System.Uri::.ctor(string)
0x32ec  stloc.s  4
0x32ee  ldloc.s  4
0x32f0  call     valuetype Microsoft.Crm.Authentication.ServiceType Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ServiceType(class [System]System.Uri serviceUrl)
0x32f5  stloc.s  5
0x32f7  ldloc.2
0x32f8  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::get_IsAuthenticated()
0x32fd  brfalse  loc_3473
0x3302  ldloc.s  5
0x3304  ldc.i4.3
0x3305  bne.un.s loc_330F
0x3307  ldc.i4.1
0x3308  stloc.s  8
0x330a  leave    loc_37FA
0x330f  ldloc.2
0x3310  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_OrganizationId()
0x3315  stloc.0
0x3316  ldloc.2
0x3317  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<string> [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_UserPrincipalName()
0x331c  callvirt instance var<u1> class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<string>::get_Value()
0x3321  stloc.s  9
0x3323  ldloc.2
0x3324  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<string> [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_Identifier()
0x3329  callvirt instance var<u1> class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<string>::get_Value()
0x332e  stloc.s  0xA
0x3330  ldloc.s  5
0x3332  ldloc.s  4
0x3334  ldloc.1
0x3335  ldloc.s  0xA
0x3337  ldloca.s 0
0x3339  call     bool Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::SetOrganizationId(valuetype Microsoft.Crm.Authentication.ServiceType serviceType, class [System]System.Uri resourceUrl, class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, string userAuth, valuetype [mscorlib]System.Guid& organizationId)
0x333e  brtrue.s loc_3352
0x3340  ldstr    aClaimsidentity_4// "ClaimsIdentityAuthorizationManager.Chec"...
0x3345  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x334a  ldc.i4.0
0x334b  stloc.s  8
0x334d  leave    loc_37FA
0x3352  ldc.i4.1
0x3353  stloc.s  0xB
0x3355  ldloc.1
0x3356  ldloc.0
0x3357  ldloca.s 0xC
0x3359  call     bool Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::DoRecognizeUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, valuetype [mscorlib]System.Guid organizationId, [out] valuetype [mscorlib]System.Guid& userId)
0x335e  brtrue.s loc_339C
0x3360  ldloc.s  9
0x3362  ldloc.0
0x3363  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ValidateSpecialUser(string authenticationInfo, valuetype [mscorlib]System.Guid organizationId)
0x3368  stloc.s  0xD
0x336a  ldloca.s 0xD
0x336c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3371  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3376  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x337b  brfalse.s loc_339C
0x337d  ldloca.s 0xD
0x337f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_OrganizationId()
0x3384  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3389  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x338e  brfalse.s loc_339C
0x3390  ldloca.s 0xD
0x3392  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3397  stloc.s  0xC
0x3399  ldc.i4.0
0x339a  stloc.s  0xB
0x339c  ldloc.s  0xC
0x339e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33a3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33a8  brfalse.s loc_33BC
0x33aa  ldstr    aClaimsidentity_5// "ClaimsIdentityAuthorizationManager.Chec"...
0x33af  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x33b4  ldc.i4.0
0x33b5  stloc.s  8
0x33b7  leave    loc_37FA
0x33bc  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x33c1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x33c6  ldc.i4.2
0x33c7  bne.un.s loc_3403
0x33c9  call     class Microsoft.Crm.Authentication.Telemetry.XRMAuthIdentityEventSource Microsoft.Crm.Authentication.Telemetry.XRMAuthIdentityEventSource::get_Instance()
0x33ce  ldloc.1
0x33cf  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetTenantId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x33d4  ldloc.1
0x33d5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetObjectId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x33da  ldloc.s  0xC
0x33dc  ldloc.0
0x33dd  callvirt instance void Microsoft.Crm.Authentication.Telemetry.XRMAuthIdentityEventSource::XRMAuthIdentity(valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x33e2  ldloc.1
0x33e3  call     bool [Microsoft.Crm.Core]IdentityExtensions::IsDelegatedAdmin(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x33e8  brfalse.s loc_3403
0x33ea  call     class Microsoft.Crm.Authentication.Telemetry.XRMAuthIdentityEventSource Microsoft.Crm.Authentication.Telemetry.XRMAuthIdentityEventSource::get_Instance()
0x33ef  ldloc.1
0x33f0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetHomeTenantId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x33f5  ldloc.1
0x33f6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetObjectId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x33fb  ldloc.s  0xC
0x33fd  ldloc.0
0x33fe  callvirt instance void Microsoft.Crm.Authentication.Telemetry.XRMAuthIdentityEventSource::XRMAuthIdentity(valuetype [mscorlib]System.Guid tenantId, valuetype [mscorlib]System.Guid objectId, valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x3403  ldloc.2
0x3404  ldloc.s  0xC
0x3406  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::set_Id(valuetype [mscorlib]System.Guid)
0x340b  ldloc.2
0x340c  call     void Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateCallerId(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity identity)
0x3411  ldloc.s  0xB
0x3413  brfalse.s loc_345B
0x3415  ldloc.s  0xC
0x3417  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x341c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3421  brfalse.s loc_345B
0x3423  ldloc.0
0x3424  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3429  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x342e  brfalse.s loc_345B
0x3430  ldloc.0
0x3431  ldc.i4.s 0x16
0x3433  ldstr    aClaimsidentity_6// "ClaimsIdentityAuthorizationManager Auth"...
0x3438  ldc.i4.1
0x3439  newarr   [mscorlib]System.Object
0x343e  dup
0x343f  ldc.i4.0
0x3440  ldloc.s  0xC
0x3442  box      [mscorlib]System.Guid
0x3447  stelem.ref
0x3448  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x344d  ldloc.s  0xC
0x344f  ldloc.0
0x3450  ldc.i4.1
0x3451  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3456  call     void Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::UpdateAccessTime(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Authentication.UserAuthenticationAccessType accessType, valuetype [mscorlib]System.DateTime accessTime)
0x345b  ldloc.s  5
0x345d  ldloc.1
0x345e  call     bool Microsoft.Crm.Authentication.AcsTokenLogger::IsTokenLoggingRequired(valuetype Microsoft.Crm.Authentication.ServiceType serviceType, class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal)
0x3463  brfalse.s loc_346B
0x3465  ldloc.1
0x3466  call     void Microsoft.Crm.Authentication.AcsTokenLogger::LogTokenDetails(class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal)
0x346b  ldc.i4.1
0x346c  stloc.s  8
0x346e  leave    loc_37FA
0x3473  ldstr    aClaimsidentity_7// "ClaimsIdentityAuthorizationManager.Chec"...
0x3478  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x347d  ldc.i4.0
0x347e  stloc.s  8
0x3480  leave    loc_37FA
0x3485  stloc.s  0xE
0x3487  ldloc.s  0xE
0x3489  ldstr    aClaimsidentity_8// "ClaimsIdentityAuthorizationManager.Chec"...
0x348e  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x3493  ldloc.0
0x3494  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3499  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x349e  brfalse  loc_37F8
0x34a3  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x34a8  ldloc.0
0x34a9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve(valuetype [mscorlib]System.Guid)
0x34ae  stloc.s  0xF
0x34b0  ldloc.s  0xE
0x34b2  ldloc.0
0x34b3  ldc.i4.s 0x16
0x34b5  ldstr    aOrgDataArerepo// "Org Data - AreReportsPublished\t{56},Av"...
0x34ba  ldc.i4.s 0x39
0x34bc  newarr   [mscorlib]System.Object
0x34c1  dup
0x34c2  ldc.i4.0
0x34c3  ldloc.s  0xF
0x34c5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_AvailabilityGroupName()
0x34ca  stelem.ref
0x34cb  dup
0x34cc  ldc.i4.1
0x34cd  ldloc.s  0xF
0x34cf  callvirt instance float32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_AverageAsyncRequestCompletionTime()
0x34d4  box      [mscorlib]System.Single
0x34d9  stelem.ref
0x34da  dup
0x34db  ldc.i4.2
0x34dc  ldloc.s  0xF
0x34de  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_AverageIO()
0x34e3  box      [mscorlib]System.Int32
0x34e8  stelem.ref
0x34e9  dup
0x34ea  ldc.i4.3
0x34eb  ldloc.s  0xF
0x34ed  callvirt instance float32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_AverageWebRequestCompletionTime()
0x34f2  box      [mscorlib]System.Single
0x34f7  stelem.ref
0x34f8  dup
0x34f9  ldc.i4.4
0x34fa  ldloc.s  0xF
0x34fc  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_BuildNumber()
0x3501  box      [mscorlib]System.Int32
0x3506  stelem.ref
0x3507  dup
0x3508  ldc.i4.5
0x3509  ldloc.s  0xF
0x350b  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_CurrentStorageSizeMB()
0x3510  box      [mscorlib]System.Int32
0x3515  stelem.ref
0x3516  dup
0x3517  ldc.i4.6
0x3518  ldloc.s  0xF
0x351a  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseMirroringSetupInProgress()
0x351f  box      [mscorlib]System.Boolean
0x3524  stelem.ref
0x3525  dup
0x3526  ldc.i4.7
0x3527  ldloc.s  0xF
0x3529  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x352e  stelem.ref
  ... truncated ...
```
