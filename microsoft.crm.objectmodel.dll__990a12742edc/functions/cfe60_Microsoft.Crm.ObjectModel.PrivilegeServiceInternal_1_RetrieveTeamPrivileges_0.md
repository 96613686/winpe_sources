# Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrieveTeamPrivileges_0

- ea: `0xcfe60`
- end: `0xcffa2`
- name: `Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrieveTeamPrivileges_0`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## string_xrefs

- `0xcfee1`: `privilegedepthmask`
- `0xcff3e`: `PrivilegeObjectTypeCodes`
- `0xcfeaa`: `privilegeid`
- `0xcfecb`: `privilegeid`
- `0xcfed0`: `privilegeid`
- `0xcff43`: `privilegeid`
- `0xcff48`: `privilegeid`
- `0xcff6b`: `privilegeid`
- `0xcfeba`: `accessright`
- `0xcfec6`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0xcfe60  ldarg.1
0xcfe61  ldstr    aTeamid_1// "teamId"
0xcfe66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xcfe6b  ldarg.2
0xcfe6c  ldstr    aContext// "context"
0xcfe71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcfe76  ldc.i4.s 9
0xcfe78  ldarg.1
0xcfe79  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32, valuetype [mscorlib]System.Guid)
0xcfe7e  stloc.0
0xcfe7f  ldarg.0
0xcfe80  ldloc.0
0xcfe81  ldarg.2
0xcfe82  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::CheckReadPrivilegeAndAccess(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfe87  pop
0xcfe88  ldarg.0
0xcfe89  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xcfe8e  ldarg.2
0xcfe8f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xcfe94  stloc.1
0xcfe95  ldloc.1
0xcfe96  ldc.i4.1
0xcfe97  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0xcfe9c  ldloc.1
0xcfe9d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xcfea2  ldc.i4.3
0xcfea3  newarr   [mscorlib]System.String
0xcfea8  dup
0xcfea9  ldc.i4.0
0xcfeaa  ldstr    aPrivilegeid// "privilegeid"
0xcfeaf  stelem.ref
0xcfeb0  dup
0xcfeb1  ldc.i4.1
0xcfeb2  ldstr    aIsdisabledwhen// "isdisabledwhenintegrated"
0xcfeb7  stelem.ref
0xcfeb8  dup
0xcfeb9  ldc.i4.2
0xcfeba  ldstr    aAccessright// "accessright"
0xcfebf  stelem.ref
0xcfec0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xcfec5  ldloc.1
0xcfec6  ldstr    aRoleprivileges// "RolePrivileges"
0xcfecb  ldstr    aPrivilegeid// "privilegeid"
0xcfed0  ldstr    aPrivilegeid// "privilegeid"
0xcfed5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xcfeda  stloc.2
0xcfedb  ldloc.2
0xcfedc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xcfee1  ldstr    aPrivilegedepth// "privilegedepthmask"
0xcfee6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcfeeb  ldloc.2
0xcfeec  ldstr    aRole// "Role"
0xcfef1  ldstr    aParentrootrole// "parentrootroleid"
0xcfef6  ldstr    aRoleid// "roleid"
0xcfefb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xcff00  stloc.3
0xcff01  ldloc.3
0xcff02  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xcff07  ldstr    aBusinessunitid// "businessunitid"
0xcff0c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcff11  ldloc.3
0xcff12  ldstr    aTeamroles// "TeamRoles"
0xcff17  ldstr    aRoleid// "roleid"
0xcff1c  ldstr    aRoleid// "roleid"
0xcff21  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xcff26  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0xcff2b  ldstr    aTeamid_0// "teamid"
0xcff30  ldc.i4.0
0xcff31  ldarg.1
0xcff32  box      [mscorlib]System.Guid
0xcff37  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xcff3c  pop
0xcff3d  ldloc.1
0xcff3e  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0xcff43  ldstr    aPrivilegeid// "privilegeid"
0xcff48  ldstr    aPrivilegeid// "privilegeid"
0xcff4d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xcff52  stloc.s  4
0xcff54  ldloc.s  4
0xcff56  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xcff5b  ldstr    aObjecttypecode// "objecttypecode"
0xcff60  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcff65  ldloc.1
0xcff66  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xcff6b  ldstr    aPrivilegeid// "privilegeid"
0xcff70  ldc.i4.0
0xcff71  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xcff76  ldarg.0
0xcff77  ldloc.1
0xcff78  ldloc.2
0xcff79  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xcff7e  ldloc.3
0xcff7f  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xcff84  ldloc.s  4
0xcff86  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xcff8b  ldarg.2
0xcff8c  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::RetrievePrivilegesFromDatabase(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, string, string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcff91  stloc.s  5
0xcff93  ldarg.0
0xcff94  ldarg.2
0xcff95  ldc.i4.0
0xcff96  ldc.i4.0
0xcff97  ldloc.s  5
0xcff99  ldarg.3
0xcff9a  ldarg.s  4
0xcff9c  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::GetPrivilegeArrayFromCollection(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, bool, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool, bool)
0xcffa1  ret
```
