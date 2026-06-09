# Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetEvoStsSettingForOrganization

- ea: `0x1070`
- end: `0x10d7`
- name: `Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetEvoStsSettingForOrganization`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x2820`
- `0xcf40`

## callees

- `0x1070`

## string_xrefs

- `0x1092`: `D:\a\1\s\src\Platform\Authentication\Legacy\Common\CrmAuthorizationUtility.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1070  ldarg.0
0x1071  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1076  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x107b  brfalse.s loc_10B3
0x107d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x1082  ldarg.0
0x1083  ldstr    aEvostsauthenti// "EvoSTSAuthenticationEnabled"
0x1088  ldc.i4   0x15C
0x108d  ldstr    aGetevostssetti// "GetEvoStsSettingForOrganization"
0x1092  ldstr    aDA1SSrcPlatfor// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0x1097  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x109c  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x10a1  stloc.1
0x10a2  ldloca.s 1
0x10a4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x10a9  brfalse.s loc_10B3
0x10ab  ldloca.s 1
0x10ad  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x10b2  ret
0x10b3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x10b8  ldstr    aEvostsauthenti// "EvoSTSAuthenticationEnabled"
0x10bd  ldc.i4.0
0x10be  callvirt T0x2B000005
0x10c3  stloc.0
0x10c4  ldloca.s 0
0x10c6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x10cb  brfalse.s loc_10D5
0x10cd  ldloca.s 0
0x10cf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x10d4  ret
0x10d5  ldc.i4.0
0x10d6  ret
```
