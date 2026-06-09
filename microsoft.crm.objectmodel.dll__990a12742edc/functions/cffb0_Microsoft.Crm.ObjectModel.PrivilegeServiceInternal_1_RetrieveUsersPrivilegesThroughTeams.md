# Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrieveUsersPrivilegesThroughTeams

- ea: `0xcffb0`
- end: `0xd011b`
- name: `Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrieveUsersPrivilegesThroughTeams`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## string_xrefs

- `0xd0025`: `privilegedepthmask`
- `0xd00a7`: `PrivilegeObjectTypeCodes`
- `0xcffee`: `privilegeid`
- `0xd000f`: `privilegeid`
- `0xd0014`: `privilegeid`
- `0xd00ac`: `privilegeid`
- `0xd00b1`: `privilegeid`
- `0xd00d4`: `privilegeid`
- `0xcfffe`: `accessright`
- `0xd000a`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0xcffb0  ldarg.1
0xcffb1  ldstr    aUserid_2// "userId"
0xcffb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xcffbb  ldarg.2
0xcffbc  ldstr    aContext// "context"
0xcffc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcffc6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0xcffcb  ldarg.1
0xcffcc  ldarg.2
0xcffcd  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0xcffd2  stloc.0
0xcffd3  ldarg.0
0xcffd4  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xcffd9  ldarg.2
0xcffda  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xcffdf  stloc.1
0xcffe0  ldloc.1
0xcffe1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xcffe6  ldc.i4.3
0xcffe7  newarr   [mscorlib]System.String
0xcffec  dup
0xcffed  ldc.i4.0
0xcffee  ldstr    aPrivilegeid// "privilegeid"
0xcfff3  stelem.ref
0xcfff4  dup
0xcfff5  ldc.i4.1
0xcfff6  ldstr    aIsdisabledwhen// "isdisabledwhenintegrated"
0xcfffb  stelem.ref
0xcfffc  dup
0xcfffd  ldc.i4.2
0xcfffe  ldstr    aAccessright// "accessright"
0xd0003  stelem.ref
0xd0004  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xd0009  ldloc.1
0xd000a  ldstr    aRoleprivileges// "RolePrivileges"
0xd000f  ldstr    aPrivilegeid// "privilegeid"
0xd0014  ldstr    aPrivilegeid// "privilegeid"
0xd0019  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xd001e  stloc.2
0xd001f  ldloc.2
0xd0020  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xd0025  ldstr    aPrivilegedepth// "privilegedepthmask"
0xd002a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xd002f  ldloc.2
0xd0030  ldstr    aRole// "Role"
0xd0035  ldstr    aParentrootrole// "parentrootroleid"
0xd003a  ldstr    aRoleid// "roleid"
0xd003f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xd0044  stloc.3
0xd0045  ldloc.3
0xd0046  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xd004b  ldstr    aBusinessunitid// "businessunitid"
0xd0050  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xd0055  ldloc.3
0xd0056  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Order()
0xd005b  ldstr    aBusinessunitid// "businessunitid"
0xd0060  ldc.i4.0
0xd0061  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xd0066  ldloc.3
0xd0067  ldstr    aTeamroles// "TeamRoles"
0xd006c  ldstr    aRoleid// "roleid"
0xd0071  ldstr    aRoleid// "roleid"
0xd0076  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xd007b  ldstr    aTeammembership// "TeamMembership"
0xd0080  ldstr    aTeamid_0// "teamid"
0xd0085  ldstr    aTeamid_0// "teamid"
0xd008a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xd008f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0xd0094  ldstr    aSystemuserid// "systemuserid"
0xd0099  ldc.i4.0
0xd009a  ldarg.1
0xd009b  box      [mscorlib]System.Guid
0xd00a0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xd00a5  pop
0xd00a6  ldloc.1
0xd00a7  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0xd00ac  ldstr    aPrivilegeid// "privilegeid"
0xd00b1  ldstr    aPrivilegeid// "privilegeid"
0xd00b6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xd00bb  stloc.s  4
0xd00bd  ldloc.s  4
0xd00bf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xd00c4  ldstr    aObjecttypecode// "objecttypecode"
0xd00c9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xd00ce  ldloc.1
0xd00cf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xd00d4  ldstr    aPrivilegeid// "privilegeid"
0xd00d9  ldc.i4.0
0xd00da  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xd00df  ldarg.0
0xd00e0  ldarg.1
0xd00e1  ldarg.2
0xd00e2  call     instance bool class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::CheckSpecialUser(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd00e7  stloc.s  5
0xd00e9  ldarg.0
0xd00ea  ldloc.1
0xd00eb  ldloc.2
0xd00ec  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xd00f1  ldloc.3
0xd00f2  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xd00f7  ldloc.s  4
0xd00f9  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xd00fe  ldarg.2
0xd00ff  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::RetrievePrivilegesFromDatabase(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, string, string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd0104  stloc.s  6
0xd0106  ldarg.0
0xd0107  ldarg.2
0xd0108  ldloc.0
0xd0109  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_AccessMode()
0xd010e  ldloc.s  5
0xd0110  ldloc.s  6
0xd0112  ldarg.3
0xd0113  ldarg.s  4
0xd0115  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::GetPrivilegeArrayFromCollection(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, bool, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool, bool)
0xd011a  ret
```
