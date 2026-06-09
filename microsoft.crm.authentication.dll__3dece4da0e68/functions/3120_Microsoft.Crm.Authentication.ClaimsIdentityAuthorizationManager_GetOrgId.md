# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgId

- ea: `0x3120`
- end: `0x317b`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgId`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x38c0`
- `0xef20`

## callees

- `0x3120`
- `0x5dd0`
- `0x6410`
- `0x78e0`

## string_xrefs

- `0x3165`: `ClaimsIdentityAuthorizationManager.GetOrgId() could not determine default organization.`

## pseudocode

```c

```

## disassembly

```asm
0x3120  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3125  stloc.0
0x3126  ldarg.2
0x3127  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x312c  ldarg.0
0x312d  ldloca.s 0
0x312f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::TryGetDefaultOrganization(string, valuetype [mscorlib]System.Guid&)
0x3134  brtrue.s loc_3177
0x3136  ldarg.2
0x3137  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x313c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0x3141  ldc.i4.2
0x3142  beq.s    loc_314D
0x3144  ldarg.1
0x3145  ldarg.0
0x3146  call     bool Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, string userAuth)
0x314b  br.s     loc_3154
0x314d  ldarg.0
0x314e  ldarg.2
0x314f  call     bool Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser(string userAuth, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x3154  brfalse.s loc_3177
0x3156  ldarg.2
0x3157  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x315c  ldarg.0
0x315d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetDefaultOrganization(string)
0x3162  stloc.0
0x3163  leave.s  loc_3177
0x3165  ldstr    aClaimsidentity// "ClaimsIdentityAuthorizationManager.GetO"...
0x316a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x316f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3174  stloc.1
0x3175  leave.s  loc_3179
0x3177  ldloc.0
0x3178  ret
0x3179  ldloc.1
0x317a  ret
```
