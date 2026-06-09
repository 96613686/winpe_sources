# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::SetOrganizationId

- ea: `0x38c0`
- end: `0x3941`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::SetOrganizationId`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x31b0`

## callees

- `0x1980`
- `0x3120`
- `0x38c0`
- `0x7780`

## string_xrefs

- `0x3926`: `ClaimsIdentityAuthorizationManager.SetOrganizationId(): organization id was not sent for userAuth '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x38c0  ldarg.s  4
0x38c2  ldobj    [mscorlib]System.Guid
0x38c7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38cc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x38d1  brfalse.s loc_38D5
0x38d3  ldc.i4.1
0x38d4  ret
0x38d5  ldarg.0
0x38d6  ldc.i4.1
0x38d7  beq.s    loc_38F2
0x38d9  ldarg.3
0x38da  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x38df  brtrue.s loc_38FF
0x38e1  ldarg.s  4
0x38e3  ldarg.3
0x38e4  ldarg.2
0x38e5  ldc.i4.0
0x38e6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgId(string userAuth, class [mscorlib]System.Security.Claims.ClaimsPrincipal claimsPrincipal, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x38eb  stobj    [mscorlib]System.Guid
0x38f0  br.s     loc_38FF
0x38f2  ldarg.s  4
0x38f4  ldarg.1
0x38f5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetOrganizationId(class [System]System.Uri uri)
0x38fa  stobj    [mscorlib]System.Guid
0x38ff  ldarg.s  4
0x3901  ldobj    [mscorlib]System.Guid
0x3906  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x390b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3910  brfalse.s loc_3921
0x3912  ldarg.2
0x3913  ldarg.s  4
0x3915  ldobj    [mscorlib]System.Guid
0x391a  call     void [Microsoft.Crm.Core]IdentityExtensions::SetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x391f  ldc.i4.1
0x3920  ret
0x3921  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3926  ldstr    aClaimsidentity_9// "ClaimsIdentityAuthorizationManager.SetO"...
0x392b  ldc.i4.1
0x392c  newarr   [mscorlib]System.Object
0x3931  dup
0x3932  ldc.i4.0
0x3933  ldarg.3
0x3934  stelem.ref
0x3935  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x393a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x393f  ldc.i4.0
0x3940  ret
```
