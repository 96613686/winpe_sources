# Microsoft.Crm.BusinessEntities.SecurityLibrary::TryGetMaxPrivilegeDepthForUserAcrossBusinessUnits

- ea: `0x62bb0`
- end: `0x62cd9`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::TryGetMaxPrivilegeDepthForUserAcrossBusinessUnits`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x61f20`
- `0x62b70`

## callees

- `0x62bb0`
- `0x636d0`

## string_xrefs

- `0x62bbc`: `privilege`
- `0x62ca1`: `SecLib::TryGetMaxPrivilegeDepthForUserAcrossBusinessUnits failed - UserNotAssignedRoles. User={0}, privilege={1}`

## pseudocode

```c

```

## disassembly

```asm
0x62bb0  ldarg.0
0x62bb1  ldstr    aUser// "user"
0x62bb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x62bbb  ldarg.1
0x62bbc  ldstr    aPrivilege_0// "privilege"
0x62bc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x62bc6  ldarg.2
0x62bc7  ldstr    aContext// "context"
0x62bcc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x62bd1  ldarg.3
0x62bd2  ldc.i4.0
0x62bd3  stind.i4
0x62bd4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x62bd9  ldarg.0
0x62bda  ldarg.2
0x62bdb  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x62be0  stloc.0
0x62be1  ldc.i4.m1
0x62be2  stloc.1
0x62be3  ldc.i4.0
0x62be4  stloc.2
0x62be5  ldloc.0
0x62be6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62beb  ldlen
0x62bec  brfalse.s loc_62C18
0x62bee  ldc.i4.1
0x62bef  stloc.2
0x62bf0  ldloc.0
0x62bf1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62bf6  ldarg.1
0x62bf7  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::GetPrivilegeIndex(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] privileges, valuetype [mscorlib]System.Guid privilege)
0x62bfc  stloc.3
0x62bfd  ldc.i4.0
0x62bfe  ldloc.3
0x62bff  bgt.s    loc_62C18
0x62c01  ldloc.0
0x62c02  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62c07  ldloc.3
0x62c08  ldelem.ref
0x62c09  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x62c0e  stloc.1
0x62c0f  ldloc.1
0x62c10  ldc.i4.3
0x62c11  bne.un.s loc_62C18
0x62c13  ldarg.3
0x62c14  ldc.i4.3
0x62c15  stind.i4
0x62c16  ldc.i4.1
0x62c17  ret
0x62c18  ldloc.0
0x62c19  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_Teams()
0x62c1e  stloc.s  4
0x62c20  ldc.i4.0
0x62c21  stloc.s  5
0x62c23  br.s     loc_62C91
0x62c25  ldloc.s  4
0x62c27  ldloc.s  5
0x62c29  ldelem   [mscorlib]System.Guid
0x62c2e  stloc.s  6
0x62c30  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache::Instance()
0x62c35  ldloc.s  6
0x62c37  ldarg.2
0x62c38  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ITeam>::LookupEntry(void, var<u1>)
0x62c3d  stloc.s  7
0x62c3f  ldloc.s  7
0x62c41  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62c46  brfalse.s loc_62C8B
0x62c48  ldloc.s  7
0x62c4a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62c4f  ldlen
0x62c50  brfalse.s loc_62C8B
0x62c52  ldc.i4.1
0x62c53  stloc.2
0x62c54  ldloc.s  7
0x62c56  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62c5b  ldarg.1
0x62c5c  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::GetPrivilegeIndex(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] privileges, valuetype [mscorlib]System.Guid privilege)
0x62c61  stloc.s  8
0x62c63  ldc.i4.0
0x62c64  ldloc.s  8
0x62c66  bgt.s    loc_62C8B
0x62c68  ldloc.s  7
0x62c6a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x62c6f  ldloc.s  8
0x62c71  ldelem.ref
0x62c72  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x62c77  stloc.s  9
0x62c79  ldloc.s  9
0x62c7b  ldc.i4.3
0x62c7c  bne.un.s loc_62C83
0x62c7e  ldarg.3
0x62c7f  ldc.i4.3
0x62c80  stind.i4
0x62c81  ldc.i4.1
0x62c82  ret
0x62c83  ldloc.s  9
0x62c85  ldloc.1
0x62c86  ble.s    loc_62C8B
0x62c88  ldloc.s  9
0x62c8a  stloc.1
0x62c8b  ldloc.s  5
0x62c8d  ldc.i4.1
0x62c8e  add
0x62c8f  stloc.s  5
0x62c91  ldloc.s  5
0x62c93  ldloc.s  4
0x62c95  ldlen
0x62c96  conv.i4
0x62c97  blt.s    loc_62C25
0x62c99  ldloc.2
0x62c9a  brtrue.s loc_62CCE
0x62c9c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62ca1  ldstr    aSeclibTrygetma// "SecLib::TryGetMaxPrivilegeDepthForUserA"...
0x62ca6  ldc.i4.2
0x62ca7  newarr   [mscorlib]System.Object
0x62cac  dup
0x62cad  ldc.i4.0
0x62cae  ldarg.0
0x62caf  box      [mscorlib]System.Guid
0x62cb4  stelem.ref
0x62cb5  dup
0x62cb6  ldc.i4.1
0x62cb7  ldarg.1
0x62cb8  box      [mscorlib]System.Guid
0x62cbd  stelem.ref
0x62cbe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x62cc3  ldc.i4   0x80042F09
0x62cc8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string, int32)
0x62ccd  throw
0x62cce  ldloc.1
0x62ccf  ldc.i4.m1
0x62cd0  bne.un.s loc_62CD4
0x62cd2  ldc.i4.0
0x62cd3  ret
0x62cd4  ldarg.3
0x62cd5  ldloc.1
0x62cd6  stind.i4
0x62cd7  ldc.i4.1
0x62cd8  ret
```
