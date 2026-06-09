# Microsoft.Crm.Caching.UserDataWebServiceCacheLoader::PopulatePrivilegeDepths

- ea: `0x14fe0`
- end: `0x15260`
- name: `Microsoft.Crm.Caching.UserDataWebServiceCacheLoader::PopulatePrivilegeDepths`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14df0`

## callees

- `0x128c0`
- `0x14fe0`

## string_xrefs

- `0x1503d`: `accessmode`
- `0x15093`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0x14fe0  ldloca.s 0
0x14fe2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>
0x14fe8  ldc.i4.0
0x14fe9  stloc.1
0x14fea  ldarg.1
0x14feb  stloc.2
0x14fec  ldc.i4.0
0x14fed  stloc.3
0x14fee  br       loc_15256
0x14ff3  ldloc.2
0x14ff4  ldloc.3
0x14ff5  ldelem.ref
0x14ff6  stloc.s  4
0x14ff8  ldloca.s 0
0x14ffa  ldloc.s  4
0x14ffc  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x15001  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x15006  ldloc.0
0x15007  stloc.s  5
0x15009  ldc.i4.3
0x1500a  stloc.s  6
0x1500c  ldloca.s 5
0x1500e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::GetValueOrDefault()
0x15013  ldloc.s  6
0x15015  beq.s    loc_1501A
0x15017  ldc.i4.0
0x15018  br.s     loc_15021
0x1501a  ldloca.s 5
0x1501c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::get_HasValue()
0x15021  brfalse.s loc_1503C
0x15023  ldarg.s  4
0x15025  ldloc.s  4
0x15027  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x1502c  ldc.i4.3
0x1502d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x15032  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>>::set_Item(var<u1>, !!T0)
0x15037  br       loc_15252
0x1503c  ldarg.0
0x1503d  ldstr    aAccessmode// "accessmode"
0x15042  callvirt instance object Microsoft.Crm.Caching.CachePlatformEntityWrapper::GetAttributeValue(string attributeName)
0x15047  unbox.any [mscorlib]System.Int32
0x1504c  ldc.i4.2
0x1504d  bne.un.s loc_15092
0x1504f  ldarg.s  6
0x15051  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15056  ldloc.s  4
0x15058  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x1505d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(valuetype [mscorlib]System.Guid)
0x15062  stloc.s  7
0x15064  ldloc.s  4
0x15066  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x1506b  ldloc.s  7
0x1506d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_AccessRight()
0x15072  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::IsInvalidPrivilegeForReadOnlyUser(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights)
0x15077  brfalse.s loc_15092
0x15079  ldarg.s  4
0x1507b  ldloc.s  4
0x1507d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x15082  ldc.i4.3
0x15083  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x15088  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>>::set_Item(var<u1>, !!T0)
0x1508d  br       loc_15252
0x15092  ldarg.0
0x15093  ldstr    aAccessmode// "accessmode"
0x15098  callvirt instance object Microsoft.Crm.Caching.CachePlatformEntityWrapper::GetAttributeValue(string attributeName)
0x1509d  unbox.any [mscorlib]System.Int32
0x150a2  ldc.i4.2
0x150a3  bne.un.s loc_150F1
0x150a5  ldarg.s  6
0x150a7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x150ac  ldloc.s  4
0x150ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x150b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(valuetype [mscorlib]System.Guid)
0x150b8  stloc.s  8
0x150ba  ldc.i4.1
0x150bb  ldc.i4.1
0x150bc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmLicenseService::GetLicenseGuid(int32, bool)
0x150c1  ldloc.s  8
0x150c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x150c8  ldloc.s  8
0x150ca  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_ObjectTypeCode()
0x150cf  ldc.i4.1
0x150d0  ldc.i4.1
0x150d1  call     bool [Microsoft.Crm]Microsoft.Crm.CrmLicenseHelper::IsInvalidLicensePrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, int32, bool)
0x150d6  brfalse.s loc_150F1
0x150d8  ldarg.s  4
0x150da  ldloc.s  4
0x150dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x150e1  ldc.i4.3
0x150e2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x150e7  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>>::set_Item(var<u1>, !!T0)
0x150ec  br       loc_15252
0x150f1  ldarg.s  5
0x150f3  brfalse.s loc_15169
0x150f5  ldarg.2
0x150f6  stloc.s  9
0x150f8  ldc.i4.0
0x150f9  stloc.s  0xA
0x150fb  br.s     loc_1515C
0x150fd  ldloc.s  9
0x150ff  ldloc.s  0xA
0x15101  ldelem.ref
0x15102  stloc.s  0xB
0x15104  ldloc.s  0xB
0x15106  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x1510b  ldloc.s  4
0x1510d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x15112  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15117  brfalse.s loc_15156
0x15119  ldloc.s  0xB
0x1511b  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x15120  stloc.s  0xC
0x15122  ldloca.s 0
0x15124  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::get_HasValue()
0x15129  brfalse.s loc_15148
0x1512b  ldloc.s  0xC
0x1512d  ldloc.0
0x1512e  stloc.s  5
0x15130  ldloca.s 5
0x15132  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::GetValueOrDefault()
0x15137  bgt.s    loc_1513C
0x15139  ldc.i4.0
0x1513a  br.s     loc_15143
0x1513c  ldloca.s 5
0x1513e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::get_HasValue()
0x15143  brfalse  loc_15243
0x15148  ldloca.s 0
0x1514a  ldloc.s  0xC
0x1514c  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x15151  br       loc_15243
0x15156  ldloc.s  0xA
0x15158  ldc.i4.1
0x15159  add
0x1515a  stloc.s  0xA
0x1515c  ldloc.s  0xA
0x1515e  ldloc.s  9
0x15160  ldlen
0x15161  conv.i4
0x15162  blt.s    loc_150FD
0x15164  br       loc_15243
0x15169  ldc.i4.0
0x1516a  stloc.1
0x1516b  ldarg.3
0x1516c  stloc.s  0xD
0x1516e  ldc.i4.0
0x1516f  stloc.s  0xA
0x15171  br       loc_15238
0x15176  ldloc.s  0xD
0x15178  ldloc.s  0xA
0x1517a  ldelem   [mscorlib]System.Guid
0x1517f  stloc.s  0xE
0x15181  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.TeamDataCache::Instance()
0x15186  ldloc.s  0xE
0x15188  ldarg.s  6
0x1518a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ITeam>::LookupEntry(void, var<u1>)
0x1518f  stloc.s  0xF
0x15191  ldloc.s  0xF
0x15193  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x15198  brfalse  loc_15232
0x1519d  ldloc.s  0xF
0x1519f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x151a4  ldlen
0x151a5  brfalse  loc_15232
0x151aa  ldc.i4.0
0x151ab  stloc.s  0x10
0x151ad  br.s     loc_15222
0x151af  ldloc.s  0xF
0x151b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x151b6  ldloc.s  0x10
0x151b8  ldelem.ref
0x151b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x151be  ldloc.s  4
0x151c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x151c5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x151ca  brfalse.s loc_1521C
0x151cc  ldloc.s  0xF
0x151ce  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x151d3  ldloc.s  0x10
0x151d5  ldelem.ref
0x151d6  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0x151db  stloc.s  0x11
0x151dd  ldloc.s  0x11
0x151df  ldc.i4.3
0x151e0  bne.un.s loc_151EE
0x151e2  ldloca.s 0
0x151e4  ldc.i4.3
0x151e5  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x151ea  ldc.i4.1
0x151eb  stloc.1
0x151ec  br.s     loc_1522F
0x151ee  ldloca.s 0
0x151f0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::get_HasValue()
0x151f5  brfalse.s loc_15211
0x151f7  ldloc.s  0x11
0x151f9  ldloc.0
0x151fa  stloc.s  5
0x151fc  ldloca.s 5
0x151fe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::GetValueOrDefault()
0x15203  bgt.s    loc_15208
0x15205  ldc.i4.0
0x15206  br.s     loc_1520F
0x15208  ldloca.s 5
0x1520a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::get_HasValue()
0x1520f  brfalse.s loc_1522F
0x15211  ldloca.s 0
0x15213  ldloc.s  0x11
0x15215  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>::.ctor(var<u1>)
0x1521a  br.s     loc_1522F
0x1521c  ldloc.s  0x10
0x1521e  ldc.i4.1
0x1521f  add
0x15220  stloc.s  0x10
0x15222  ldloc.s  0x10
0x15224  ldloc.s  0xF
0x15226  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_Privileges()
0x1522b  ldlen
0x1522c  conv.i4
0x1522d  blt.s    loc_151AF
0x1522f  ldloc.1
0x15230  brtrue.s loc_15243
0x15232  ldloc.s  0xA
0x15234  ldc.i4.1
0x15235  add
0x15236  stloc.s  0xA
0x15238  ldloc.s  0xA
0x1523a  ldloc.s  0xD
0x1523c  ldlen
0x1523d  conv.i4
0x1523e  blt      loc_15176
0x15243  ldarg.s  4
0x15245  ldloc.s  4
0x15247  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0x1524c  ldloc.0
0x1524d  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth>>::set_Item(var<u1>, !!T0)
0x15252  ldloc.3
0x15253  ldc.i4.1
0x15254  add
0x15255  stloc.3
0x15256  ldloc.3
0x15257  ldloc.2
0x15258  ldlen
0x15259  conv.i4
0x1525a  blt      loc_14FF3
0x1525f  ret
```
