# Microsoft.Crm.ObjectModel.RoleServiceInternal`1::AddPrivilegesFromCollection

- ea: `0xd33a0`
- end: `0xd356c`
- name: `Microsoft.Crm.ObjectModel.RoleServiceInternal`1::AddPrivilegesFromCollection`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xd33a0`

## string_xrefs

- `0xd34a4`: `componentstate`
- `0xd3424`: `privilegedepthmask`
- `0xd3480`: `privilegedepthmask`
- `0xd3491`: `privilegedepthmask`
- `0xd34e4`: `privilegedepthmask`
- `0xd34f5`: `privilegedepthmask`
- `0xd3509`: `privilegedepthmask`
- `0xd3539`: `privilegedepthmask`
- `0xd33d3`: `privilegeid`
- `0xd3442`: `privilegeid`
- `0xd34c2`: `roleprivilegeid`
- `0xd34c9`: `roleprivilegeid`

## pseudocode

```c

```

## disassembly

```asm
0xd33a0  newobj   instance void class Microsoft.Crm.ObjectModel.RolePrivilegesServiceInternal`1<var<u1>>::.ctor()
0xd33a5  stloc.0
0xd33a6  ldarg.0
0xd33a7  ldarg.1
0xd33a8  ldarg.s  4
0xd33aa  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection class Microsoft.Crm.ObjectModel.RoleServiceInternal`1<var<u1>>::RetrieveRolePrivilegeCollectionIncludeDeleted(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd33af  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::.ctor()
0xd33b4  stloc.1
0xd33b5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::.ctor()
0xd33ba  stloc.2
0xd33bb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xd33c0  stloc.3
0xd33c1  br.s     loc_D33E9
0xd33c3  ldloc.3
0xd33c4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd33c9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xd33ce  stloc.s  4
0xd33d0  ldloc.2
0xd33d1  ldloc.s  4
0xd33d3  ldstr    aPrivilegeid// "privilegeid"
0xd33d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd33dd  unbox.any [mscorlib]System.Guid
0xd33e2  ldloc.s  4
0xd33e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::set_Item(var<u1>, !!T0)
0xd33e9  ldloc.3
0xd33ea  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd33ef  brtrue.s loc_D33C3
0xd33f1  leave.s  loc_D3407
0xd33f3  ldloc.3
0xd33f4  isinst   [mscorlib]System.IDisposable
0xd33f9  stloc.s  5
0xd33fb  ldloc.s  5
0xd33fd  brfalse.s loc_D3406
0xd33ff  ldloc.s  5
0xd3401  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd3406  endfinally
0xd3407  ldarg.2
0xd3408  stloc.s  6
0xd340a  ldc.i4.0
0xd340b  stloc.s  7
0xd340d  br       loc_D355F
0xd3412  ldloc.s  6
0xd3414  ldloc.s  7
0xd3416  ldelem.ref
0xd3417  stloc.s  8
0xd3419  ldarg.s  4
0xd341b  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RolePrivileges::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd3420  stloc.s  9
0xd3422  ldloc.s  9
0xd3424  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd3429  ldarg.0
0xd342a  ldloc.s  8
0xd342c  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_Depth()
0xd3431  call     instance int32 class Microsoft.Crm.ObjectModel.RoleServiceInternal`1<var<u1>>::ProcessDepth(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth)
0xd3436  box      [mscorlib]System.Int32
0xd343b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd3440  ldloc.s  9
0xd3442  ldstr    aPrivilegeid// "privilegeid"
0xd3447  ldloc.s  8
0xd3449  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0xd344e  box      [mscorlib]System.Guid
0xd3453  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd3458  ldloc.s  9
0xd345a  ldstr    aRoleid// "roleid"
0xd345f  ldarg.1
0xd3460  box      [mscorlib]System.Guid
0xd3465  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd346a  ldloc.2
0xd346b  ldloc.s  8
0xd346d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0xd3472  ldloca.s 0xA
0xd3474  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>::TryGetValue(var<u1>, !!T0)
0xd3479  brfalse  loc_D352B
0xd347e  ldloc.s  0xA
0xd3480  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd3485  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd348a  unbox.any [mscorlib]System.Int32
0xd348f  ldloc.s  9
0xd3491  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd3496  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd349b  unbox.any [mscorlib]System.Int32
0xd34a0  bne.un.s loc_D34B8
0xd34a2  ldloc.s  0xA
0xd34a4  ldstr    aComponentstate_0// "componentstate"
0xd34a9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd34ae  unbox.any [mscorlib]System.Int32
0xd34b3  ldc.i4.2
0xd34b4  ceq
0xd34b6  br.s     loc_D34B9
0xd34b8  ldc.i4.1
0xd34b9  ldarg.3
0xd34ba  or
0xd34bb  brfalse  loc_D3559
0xd34c0  ldloc.s  9
0xd34c2  ldstr    aRoleprivilegei// "roleprivilegeid"
0xd34c7  ldloc.s  0xA
0xd34c9  ldstr    aRoleprivilegei// "roleprivilegeid"
0xd34ce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd34d3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd34d8  ldloc.0
0xd34d9  ldloc.s  9
0xd34db  ldarg.s  4
0xd34dd  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd34e2  ldloc.s  0xA
0xd34e4  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd34e9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd34ee  unbox.any [mscorlib]System.Int32
0xd34f3  ldloc.s  9
0xd34f5  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd34fa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd34ff  unbox.any [mscorlib]System.Int32
0xd3504  beq.s    loc_D3559
0xd3506  ldloc.1
0xd3507  ldloc.s  9
0xd3509  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd350e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd3513  unbox.any [mscorlib]System.Int32
0xd3518  ldloc.s  8
0xd351a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0xd351f  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::.ctor(int32, valuetype [mscorlib]System.Guid)
0xd3524  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::Add(var<u1>)
0xd3529  br.s     loc_D3559
0xd352b  ldarg.0
0xd352c  ldloc.s  9
0xd352e  ldloc.0
0xd352f  ldarg.s  4
0xd3531  call     instance void class Microsoft.Crm.ObjectModel.RoleServiceInternal`1<var<u1>>::CreateRolePrivilege(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.RolePrivileges, class Microsoft.Crm.ObjectModel.RolePrivilegesServiceInternal`1<var<u1>>, !!T0)
0xd3536  ldloc.1
0xd3537  ldloc.s  9
0xd3539  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd353e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd3543  unbox.any [mscorlib]System.Int32
0xd3548  ldloc.s  8
0xd354a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::get_PrivilegeId()
0xd354f  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege::.ctor(int32, valuetype [mscorlib]System.Guid)
0xd3554  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege>::Add(var<u1>)
0xd3559  ldloc.s  7
0xd355b  ldc.i4.1
0xd355c  add
0xd355d  stloc.s  7
0xd355f  ldloc.s  7
0xd3561  ldloc.s  6
0xd3563  ldlen
0xd3564  conv.i4
0xd3565  blt      loc_D3412
0xd356a  ldloc.1
0xd356b  ret
```
