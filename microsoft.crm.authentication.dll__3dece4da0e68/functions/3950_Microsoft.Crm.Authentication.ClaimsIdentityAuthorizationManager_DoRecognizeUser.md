# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::DoRecognizeUser

- ea: `0x3950`
- end: `0x3a9a`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::DoRecognizeUser`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x31b0`

## callees

- `0x1570`
- `0x3950`
- `0x3aa0`
- `0x5d30`
- `0x6050`
- `0x6180`
- `0x6320`
- `0x7780`

## string_xrefs

- `0x396a`: `ClaimsIdentityAuthorizationManager.DoRecognizeUser(): no identity found`
- `0x3a7f`: `ClaimsIdentityAuthorizationManager.DoRecognizeUser(): Unable to locate a userId for userAuth '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x3950  ldarg.2
0x3951  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3956  stobj    [mscorlib]System.Guid
0x395b  ldarg.0
0x395c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x3961  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0x3966  stloc.0
0x3967  ldloc.0
0x3968  brtrue.s loc_3976
0x396a  ldstr    aClaimsidentity_10// "ClaimsIdentityAuthorizationManager.DoRe"...
0x396f  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x3974  ldc.i4.0
0x3975  ret
0x3976  ldloc.0
0x3977  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<string> [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_Identifier()
0x397c  callvirt instance var<u1> class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<string>::get_Value()
0x3981  stloc.1
0x3982  ldarg.1
0x3983  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3988  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x398d  brfalse  loc_3A7A
0x3992  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x3997  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0x399c  ldc.i4.2
0x399d  bne.un.s loc_39C5
0x399f  ldloc.0
0x39a0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::get_ObjectId()
0x39a5  callvirt instance var<u1> class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.LazyValue`1<valuetype [mscorlib]System.Guid>::get_Value()
0x39aa  stloc.3
0x39ab  ldarg.1
0x39ac  ldloc.3
0x39ad  ldloca.s 2
0x39af  call     bool Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::TryGetUserByObjectId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId, [out] valuetype Microsoft.Crm.Authentication.CrmUserInfo& crmUser)
0x39b4  brfalse.s loc_39C5
0x39b6  ldarg.2
0x39b7  ldloca.s 2
0x39b9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x39be  stobj    [mscorlib]System.Guid
0x39c3  ldc.i4.1
0x39c4  ret
0x39c5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x39ca  ldarg.1
0x39cb  ldloc.1
0x39cc  ldarg.2
0x39cd  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::TryGetCrmUserId(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid&)
0x39d2  brfalse.s loc_39D6
0x39d4  ldc.i4.1
0x39d5  ret
0x39d6  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x39db  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x39e0  ldc.i4.2
0x39e1  beq.s    loc_39ED
0x39e3  ldarg.0
0x39e4  ldarg.1
0x39e5  ldloc.1
0x39e6  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, valuetype [mscorlib]System.Guid organizationId, string userAuth)
0x39eb  br.s     loc_39F4
0x39ed  ldarg.1
0x39ee  ldloc.1
0x39ef  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser(valuetype [mscorlib]System.Guid organizationId, string userAuth)
0x39f4  stloc.2
0x39f5  ldloca.s 2
0x39f7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x39fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3a01  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3a06  brfalse.s loc_3A17
0x3a08  ldarg.2
0x3a09  ldloca.s 2
0x3a0b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3a10  stobj    [mscorlib]System.Guid
0x3a15  ldc.i4.1
0x3a16  ret
0x3a17  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x3a1c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x3a21  ldc.i4.2
0x3a22  bne.un.s loc_3A7A
0x3a24  ldarg.0
0x3a25  ldarg.1
0x3a26  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.SupportUserInformation::MatchExistingUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, valuetype [mscorlib]System.Guid organizationId)
0x3a2b  stloc.s  4
0x3a2d  ldloca.s 4
0x3a2f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3a34  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3a39  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3a3e  brfalse.s loc_3A4F
0x3a40  ldarg.2
0x3a41  ldloca.s 4
0x3a43  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3a48  stobj    [mscorlib]System.Guid
0x3a4d  ldc.i4.1
0x3a4e  ret
0x3a4f  ldarg.0
0x3a50  ldarg.1
0x3a51  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.DelegatedAdminInformation::MatchExistingUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, valuetype [mscorlib]System.Guid organizationId)
0x3a56  stloc.s  5
0x3a58  ldloca.s 5
0x3a5a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3a5f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3a64  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3a69  brfalse.s loc_3A7A
0x3a6b  ldarg.2
0x3a6c  ldloca.s 5
0x3a6e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x3a73  stobj    [mscorlib]System.Guid
0x3a78  ldc.i4.1
0x3a79  ret
0x3a7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a7f  ldstr    aClaimsidentity_11// "ClaimsIdentityAuthorizationManager.DoRe"...
0x3a84  ldc.i4.1
0x3a85  newarr   [mscorlib]System.Object
0x3a8a  dup
0x3a8b  ldc.i4.0
0x3a8c  ldloc.1
0x3a8d  stelem.ref
0x3a8e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a93  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x3a98  ldc.i4.0
0x3a99  ret
```
