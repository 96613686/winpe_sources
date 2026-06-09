# Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService::GetCapabilityUserRoles

- ea: `0xd340`
- end: `0xd61a`
- name: `Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService::GetCapabilityUserRoles`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x308d0`

## callees

- `0xba30`
- `0xd340`
- `0xd620`
- `0xd640`
- `0x1c330`
- `0x30900`
- `0x30940`
- `0x309a0`
- `0x30a00`

## string_xrefs

- `0xd485`: `RoleTemplateIds`
- `0xd4a7`: `RoleTemplateIds`

## pseudocode

```c

```

## disassembly

```asm
0xd340  newobj   instance void <>c__DisplayClass4_0::.ctor()
0xd345  stloc.0
0xd346  ldloc.0
0xd347  ldarg.0
0xd348  stfld    class Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService <>c__DisplayClass4_0::<>4__this
0xd34d  ldloc.0
0xd34e  ldarg.1
0xd34f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::organizationId
0xd354  ldloc.0
0xd355  ldarg.2
0xd356  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::businessUnitId
0xd35b  ldarg.0
0xd35c  ldftn    instance class Microsoft.Crm.CrmLive.Provisioning.ICapabilityRoleInfoCacheableService Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService::<GetCapabilityUserRoles>b__4_0()
0xd362  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.CrmLive.Provisioning.ICapabilityRoleInfoCacheableService>::.ctor(object, native int)
0xd367  call     T0x2B000043
0xd36c  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xd371  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xd376  stloc.1
0xd377  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService::GetCapabilityToRoleMapping()
0xd37c  stloc.2
0xd37d  call     T0x2B000044
0xd382  ldloc.0
0xd383  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::organizationId
0xd388  ldloc.0
0xd389  ldftn    instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> <>c__DisplayClass4_0::<GetCapabilityUserRoles>b__1()
0xd38f  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>>::.ctor(object, native int)
0xd394  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> Microsoft.Crm.CrmLive.Provisioning.ICapabilityRoleInfoCacheableService::GetAllRoles(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>> dataSource)
0xd399  stloc.3
0xd39a  ldloc.2
0xd39b  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xd3a0  brfalse.s loc_D3A4
0xd3a2  ldloc.1
0xd3a3  ret
0xd3a4  ldloc.2
0xd3a5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xd3aa  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xd3af  stloc.s  4
0xd3b1  br       loc_D5FC
0xd3b6  ldloca.s 4
0xd3b8  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0xd3bd  stloc.s  5
0xd3bf  ldloc.s  5
0xd3c1  ldstr    aCapability// "Capability"
0xd3c6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd3cb  castclass [mscorlib]System.String
0xd3d0  stloc.s  6
0xd3d2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xd3d7  stloc.s  7
0xd3d9  ldloc.s  5
0xd3db  ldstr    aRoleids// "RoleIds"
0xd3e0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd3e5  brfalse  loc_D483
0xd3ea  newobj   instance void <>c__DisplayClass4_1::.ctor()
0xd3ef  stloc.s  8
0xd3f1  ldloc.s  8
0xd3f3  ldloc.0
0xd3f4  stfld    class <>c__DisplayClass4_0 <>c__DisplayClass4_1::CS$<>8__locals1
0xd3f9  ldloc.s  8
0xd3fb  ldloc.s  5
0xd3fd  ldstr    aRoleids// "RoleIds"
0xd402  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd407  castclass [mscorlib]System.String
0xd40c  ldc.i4.1
0xd40d  newarr   [mscorlib]System.Char
0xd412  dup
0xd413  ldc.i4.0
0xd414  ldc.i4.s 0x2C
0xd416  stelem.i2
0xd417  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xd41c  ldsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> <>c::<>9__4_2
0xd421  dup
0xd422  brtrue.s loc_D43B
0xd424  pop
0xd425  ldsfld   class <>c <>c::<>9
0xd42a  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetCapabilityUserRoles>b__4_2(string v)
0xd430  newobj   instance void class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xd435  dup
0xd436  stsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> <>c::<>9__4_2
0xd43b  call     T0x2B00004A
0xd440  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass4_1::capabilityRoleIds
0xd445  ldloc.s  7
0xd447  ldloc.3
0xd448  ldloc.s  8
0xd44a  ldftn    instance bool <>c__DisplayClass4_1::<GetCapabilityUserRoles>b__3(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag p)
0xd450  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xd455  call     T0x2B00004B
0xd45a  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__4_4
0xd45f  dup
0xd460  brtrue.s loc_D479
0xd462  pop
0xd463  ldsfld   class <>c <>c::<>9
0xd468  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetCapabilityUserRoles>b__4_4(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag p)
0xd46e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xd473  dup
0xd474  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__4_4
0xd479  call     T0x2B00004C
0xd47e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xd483  ldloc.s  5
0xd485  ldstr    aRoletemplateid_0// "RoleTemplateIds"
0xd48a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd48f  brfalse  loc_D531
0xd494  newobj   instance void <>c__DisplayClass4_2::.ctor()
0xd499  stloc.s  9
0xd49b  ldloc.s  9
0xd49d  ldloc.0
0xd49e  stfld    class <>c__DisplayClass4_0 <>c__DisplayClass4_2::CS$<>8__locals2
0xd4a3  ldloc.s  9
0xd4a5  ldloc.s  5
0xd4a7  ldstr    aRoletemplateid_0// "RoleTemplateIds"
0xd4ac  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd4b1  castclass [mscorlib]System.String
0xd4b6  ldc.i4.1
0xd4b7  newarr   [mscorlib]System.Char
0xd4bc  dup
0xd4bd  ldc.i4.0
0xd4be  ldc.i4.s 0x2C
0xd4c0  stelem.i2
0xd4c1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xd4c6  ldsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> <>c::<>9__4_5
0xd4cb  dup
0xd4cc  brtrue.s loc_D4E5
0xd4ce  pop
0xd4cf  ldsfld   class <>c <>c::<>9
0xd4d4  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetCapabilityUserRoles>b__4_5(string v)
0xd4da  newobj   instance void class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xd4df  dup
0xd4e0  stsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> <>c::<>9__4_5
0xd4e5  call     T0x2B00004A
0xd4ea  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass4_2::roleTemplateIds
0xd4ef  ldloc.3
0xd4f0  ldloc.s  9
0xd4f2  ldftn    instance bool <>c__DisplayClass4_2::<GetCapabilityUserRoles>b__6(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag p)
0xd4f8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xd4fd  call     T0x2B00004B
0xd502  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__4_7
0xd507  dup
0xd508  brtrue.s loc_D521
0xd50a  pop
0xd50b  ldsfld   class <>c <>c::<>9
0xd510  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetCapabilityUserRoles>b__4_7(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag p)
0xd516  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xd51b  dup
0xd51c  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__4_7
0xd521  call     T0x2B00004C
0xd526  stloc.s  0xA
0xd528  ldloc.s  7
0xd52a  ldloc.s  0xA
0xd52c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xd531  ldloc.s  5
0xd533  ldstr    aRolenames// "RoleNames"
0xd538  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd53d  brfalse  loc_D5E8
0xd542  ldloc.s  5
0xd544  ldstr    aRolenames// "RoleNames"
0xd549  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd54e  castclass [mscorlib]System.String
0xd553  ldc.i4.1
0xd554  newarr   [mscorlib]System.Char
0xd559  dup
0xd55a  ldc.i4.0
0xd55b  ldc.i4.s 0x2C
0xd55d  stelem.i2
0xd55e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xd563  stloc.s  0xB
0xd565  ldloc.s  0xB
0xd567  call     T0x2B00000B
0xd56c  brfalse.s loc_D5E8
0xd56e  newobj   instance void <>c__DisplayClass4_3::.ctor()
0xd573  stloc.s  0xC
0xd575  ldloc.s  0xC
0xd577  ldloc.0
0xd578  stfld    class <>c__DisplayClass4_0 <>c__DisplayClass4_3::CS$<>8__locals3
0xd57d  ldarg.0
0xd57e  ldfld    class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService::_orgAccess
0xd583  ldloc.s  0xC
0xd585  ldfld    class <>c__DisplayClass4_0 <>c__DisplayClass4_3::CS$<>8__locals3
0xd58a  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::organizationId
0xd58f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<int32> Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetOrganizationLanguages(valuetype [mscorlib]System.Guid organizationId)
0xd594  stloc.s  0xD
0xd596  ldloc.s  0xC
0xd598  ldloc.s  0xB
0xd59a  ldloc.s  0xD
0xd59c  call     class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentService::GetLocalizedRoleNames(class [mscorlib]System.Collections.Generic.IList`1<string> roles, class [mscorlib]System.Collections.Generic.IList`1<int32> organizationLanguages)
0xd5a1  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> <>c__DisplayClass4_3::localizedRoleNames
0xd5a6  ldloc.3
0xd5a7  ldloc.s  0xC
0xd5a9  ldftn    instance bool <>c__DisplayClass4_3::<GetCapabilityUserRoles>b__8(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag p)
0xd5af  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xd5b4  call     T0x2B00004B
0xd5b9  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__4_9
0xd5be  dup
0xd5bf  brtrue.s loc_D5D8
0xd5c1  pop
0xd5c2  ldsfld   class <>c <>c::<>9
0xd5c7  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetCapabilityUserRoles>b__4_9(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag p)
0xd5cd  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xd5d2  dup
0xd5d3  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__4_9
0xd5d8  call     T0x2B00004C
0xd5dd  stloc.s  0xE
0xd5df  ldloc.s  7
0xd5e1  ldloc.s  0xE
0xd5e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xd5e8  ldloc.1
0xd5e9  ldloc.s  6
0xd5eb  ldloc.s  7
0xd5ed  call     T0x2B000047
0xd5f2  call     T0x2B000046
0xd5f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0xd5fc  ldloca.s 4
0xd5fe  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xd603  brtrue   loc_D3B6
0xd608  leave.s  loc_D618
0xd60a  ldloca.s 4
0xd60c  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0xd612  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd617  endfinally
0xd618  ldloc.1
0xd619  ret
```
