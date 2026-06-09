# Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrievePrivilegesByRole

- ea: `0xd0380`
- end: `0xd0469`
- name: `Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrievePrivilegesByRole`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xd0380`

## string_xrefs

- `0xd03f0`: `privilegedepthmask`
- `0xd0417`: `PrivilegeObjectTypeCodes`
- `0xd03b1`: `privilegeid`
- `0xd03d2`: `privilegeid`
- `0xd03d7`: `privilegeid`
- `0xd041c`: `privilegeid`
- `0xd0421`: `privilegeid`
- `0xd0442`: `privilegeid`
- `0xd03c1`: `accessright`
- `0xd03cd`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0xd0380  ldarg.1
0xd0381  call     T0x2B000190
0xd0386  brtrue.s loc_D038E
0xd0388  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>>::.ctor()
0xd038d  ret
0xd038e  ldarg.0
0xd038f  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xd0394  ldarg.s  6
0xd0396  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xd039b  stloc.0
0xd039c  ldloc.0
0xd039d  ldc.i4.1
0xd039e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0xd03a3  ldloc.0
0xd03a4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xd03a9  ldc.i4.3
0xd03aa  newarr   [mscorlib]System.String
0xd03af  dup
0xd03b0  ldc.i4.0
0xd03b1  ldstr    aPrivilegeid// "privilegeid"
0xd03b6  stelem.ref
0xd03b7  dup
0xd03b8  ldc.i4.1
0xd03b9  ldstr    aIsdisabledwhen// "isdisabledwhenintegrated"
0xd03be  stelem.ref
0xd03bf  dup
0xd03c0  ldc.i4.2
0xd03c1  ldstr    aAccessright// "accessright"
0xd03c6  stelem.ref
0xd03c7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xd03cc  ldloc.0
0xd03cd  ldstr    aRoleprivileges// "RolePrivileges"
0xd03d2  ldstr    aPrivilegeid// "privilegeid"
0xd03d7  ldstr    aPrivilegeid// "privilegeid"
0xd03dc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xd03e1  stloc.1
0xd03e2  ldloc.1
0xd03e3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xd03e8  ldc.i4.2
0xd03e9  newarr   [mscorlib]System.String
0xd03ee  dup
0xd03ef  ldc.i4.0
0xd03f0  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd03f5  stelem.ref
0xd03f6  dup
0xd03f7  ldc.i4.1
0xd03f8  ldstr    aRoleid// "roleid"
0xd03fd  stelem.ref
0xd03fe  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xd0403  ldloc.1
0xd0404  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0xd0409  ldstr    aRoleid// "roleid"
0xd040e  ldc.i4.8
0xd040f  ldarg.1
0xd0410  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xd0415  pop
0xd0416  ldloc.0
0xd0417  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0xd041c  ldstr    aPrivilegeid// "privilegeid"
0xd0421  ldstr    aPrivilegeid// "privilegeid"
0xd0426  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xd042b  stloc.2
0xd042c  ldloc.2
0xd042d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xd0432  ldstr    aObjecttypecode// "objecttypecode"
0xd0437  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xd043c  ldloc.0
0xd043d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xd0442  ldstr    aPrivilegeid// "privilegeid"
0xd0447  ldc.i4.0
0xd0448  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xd044d  ldarg.0
0xd044e  ldloc.0
0xd044f  ldloc.1
0xd0450  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xd0455  ldloc.2
0xd0456  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xd045b  ldarg.2
0xd045c  ldarg.3
0xd045d  ldarg.s  4
0xd045f  ldarg.s  5
0xd0461  ldarg.s  6
0xd0463  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>> class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::RetrievePrivilegesByRoleFromDatabase(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, string, string, int32, bool, bool, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd0468  ret
```
