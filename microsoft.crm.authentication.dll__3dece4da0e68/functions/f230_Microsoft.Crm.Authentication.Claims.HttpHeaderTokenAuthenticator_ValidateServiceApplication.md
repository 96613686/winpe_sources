# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ValidateServiceApplication

- ea: `0xf230`
- end: `0xf42d`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenAuthenticator::ValidateServiceApplication`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0xef20`

## callees

- `0xd50`
- `0x1550`
- `0x1570`
- `0x15b0`
- `0x1fc0`
- `0x2000`
- `0x79f0`
- `0x7e10`
- `0x7e30`
- `0x7e50`
- `0x7e70`
- `0xf230`
- `0x13bf0`
- `0x13c00`
- `0x13c20`

## string_xrefs

- `0xf41f`: `HttpHeaderTokenAuthenticator.ValidateServiceApplication(): Authenticated`

## pseudocode

```c

```

## disassembly

```asm
0xf230  ldarg.2
0xf231  initobj  Microsoft.Crm.Authentication.CrmUserInfo
0xf237  ldarg.0
0xf238  isinst   [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0xf23d  stloc.0
0xf23e  ldloc.0
0xf23f  brfalse  loc_F42B
0xf244  ldloc.0
0xf245  call     bool Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsApplicationServiceIdentity(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken token)
0xf24a  brfalse  loc_F42B
0xf24f  ldloc.0
0xf250  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::GetApplicationId(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken token)
0xf255  stloc.1
0xf256  ldloc.1
0xf257  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf25c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf261  brfalse.s loc_F265
0xf263  ldc.i4.0
0xf264  ret
0xf265  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0xf26a  ldarg.1
0xf26b  ldloc.1
0xf26c  ldloca.s 2
0xf26e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::TryGetServiceApplicationUserId(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid&)
0xf273  brfalse  loc_F322
0xf278  ldloc.1
0xf279  ldloc.2
0xf27a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf27f  brfalse.s loc_F283
0xf281  ldc.i4.0
0xf282  ret
0xf283  call     class Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::get_Instance()
0xf288  ldloc.0
0xf289  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::GetTenantId(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken token)
0xf28e  callvirt instance bool Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant::ValidateRequiredTenant(valuetype [mscorlib]System.Guid tenantId)
0xf293  brtrue.s loc_F297
0xf295  ldc.i4.0
0xf296  ret
0xf297  ldloc.0
0xf298  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Audiences()
0xf29d  call     T0x2B00000E
0xf2a2  newobj   instance void [System]System.Uri::.ctor(string)
0xf2a7  stloc.3
0xf2a8  call     class Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant Microsoft.Crm.Authentication.Claims.HeaderAuthentication.AllowedServiceToServiceTenant::get_Instance()
0xf2ad  ldloc.1
0xf2ae  callvirt instance bool Microsoft.Crm.Authentication.Claims.HeaderAuthentication.IAllowedServiceToServiceTenant::BypassAudienceCheckForApp(valuetype [mscorlib]System.Guid applicationId)
0xf2b3  brfalse.s loc_F2E1
0xf2b5  ldarg.2
0xf2b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf2bb  ldstr    aAppid0// "appid:{0}"
0xf2c0  ldc.i4.1
0xf2c1  newarr   [mscorlib]System.Object
0xf2c6  dup
0xf2c7  ldc.i4.0
0xf2c8  ldloc.1
0xf2c9  box      [mscorlib]System.Guid
0xf2ce  stelem.ref
0xf2cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf2d4  ldarg.1
0xf2d5  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ValidateSpecialUser(string authenticationInfo, valuetype [mscorlib]System.Guid organizationId)
0xf2da  stobj    Microsoft.Crm.Authentication.CrmUserInfo
0xf2df  ldc.i4.1
0xf2e0  ret
0xf2e1  ldloc.3
0xf2e2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganization(class [System]System.Uri url)
0xf2e7  stloc.s  4
0xf2e9  ldarg.1
0xf2ea  ldloc.s  4
0xf2ec  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf2f1  brfalse  loc_F42B
0xf2f6  ldarg.2
0xf2f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf2fc  ldstr    aAppid0// "appid:{0}"
0xf301  ldc.i4.1
0xf302  newarr   [mscorlib]System.Object
0xf307  dup
0xf308  ldc.i4.0
0xf309  ldloc.1
0xf30a  box      [mscorlib]System.Guid
0xf30f  stelem.ref
0xf310  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf315  ldarg.1
0xf316  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ValidateSpecialUser(string authenticationInfo, valuetype [mscorlib]System.Guid organizationId)
0xf31b  stobj    Microsoft.Crm.Authentication.CrmUserInfo
0xf320  ldc.i4.1
0xf321  ret
0xf322  ldc.i4.0
0xf323  stloc.s  5
0xf325  ldloc.0
0xf326  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::GetDirectoryObjectId(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken token)
0xf32b  stloc.s  6
0xf32d  ldloc.s  6
0xf32f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf334  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf339  brfalse.s loc_F349
0xf33b  ldarg.2
0xf33c  ldloc.s  6
0xf33e  ldarg.1
0xf33f  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::RetrieveUserByObjectId(valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid organizationId)
0xf344  stobj    Microsoft.Crm.Authentication.CrmUserInfo
0xf349  ldarg.2
0xf34a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0xf34f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf354  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf359  brfalse.s loc_F379
0xf35b  ldarg.2
0xf35c  call     instance valuetype Microsoft.Crm.Authentication.SystemUserType Microsoft.Crm.Authentication.CrmUserInfo::get_SystemUserType()
0xf361  ldc.i4.1
0xf362  bne.un.s loc_F372
0xf364  ldarg.2
0xf365  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_ApplicationId()
0xf36a  ldloc.1
0xf36b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf370  brfalse.s loc_F374
0xf372  ldc.i4.0
0xf373  ret
0xf374  ldc.i4.1
0xf375  stloc.s  5
0xf377  br.s     loc_F3E0
0xf379  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf37e  ldstr    aAppid0// "appid:{0}"
0xf383  ldc.i4.1
0xf384  newarr   [mscorlib]System.Object
0xf389  dup
0xf38a  ldc.i4.0
0xf38b  ldloc.1
0xf38c  box      [mscorlib]System.Guid
0xf391  stelem.ref
0xf392  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf397  stloc.s  8
0xf399  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0xf39e  ldarg.1
0xf39f  ldloc.s  8
0xf3a1  ldloca.s 9
0xf3a3  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::TryGetCrmUserId(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid&)
0xf3a8  brfalse.s loc_F3B4
0xf3aa  ldloc.s  9
0xf3ac  ldloc.1
0xf3ad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf3b2  brfalse.s loc_F3B6
0xf3b4  ldc.i4.0
0xf3b5  ret
0xf3b6  ldarg.2
0xf3b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3bc  ldstr    aAppid0// "appid:{0}"
0xf3c1  ldc.i4.1
0xf3c2  newarr   [mscorlib]System.Object
0xf3c7  dup
0xf3c8  ldc.i4.0
0xf3c9  ldloc.1
0xf3ca  box      [mscorlib]System.Guid
0xf3cf  stelem.ref
0xf3d0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf3d5  ldarg.1
0xf3d6  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ValidateSpecialUser(string authenticationInfo, valuetype [mscorlib]System.Guid organizationId)
0xf3db  stobj    Microsoft.Crm.Authentication.CrmUserInfo
0xf3e0  ldloc.0
0xf3e1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::GetTenantId(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken token)
0xf3e6  stloc.s  7
0xf3e8  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0xf3ed  ldloc.s  7
0xf3ef  stloc.s  0xA
0xf3f1  ldarg.1
0xf3f2  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::RetrieveOrganizationContextId(valuetype [mscorlib]System.Guid)
0xf3f7  stloc.s  0xB
0xf3f9  ldloca.s 0xB
0xf3fb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xf400  brtrue.s loc_F405
0xf402  ldc.i4.0
0xf403  br.s     loc_F413
0xf405  ldloc.s  0xA
0xf407  ldloca.s 0xB
0xf409  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xf40e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf413  brfalse.s loc_F42B
0xf415  ldloc.s  5
0xf417  brfalse.s loc_F429
0xf419  ldarg.2
0xf41a  ldobj    Microsoft.Crm.Authentication.CrmUserInfo
0xf41f  ldstr    aHttpheadertoke_6// "HttpHeaderTokenAuthenticator.ValidateSe"...
0xf424  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogExternalApplication(valuetype Microsoft.Crm.Authentication.CrmUserInfo appUserInfo, string context)
0xf429  ldc.i4.1
0xf42a  ret
0xf42b  ldc.i4.0
0xf42c  ret
```
