# Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrieveUserPrivileges_1

- ea: `0xcfb60`
- end: `0xcfcda`
- name: `Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1::RetrieveUserPrivileges_1`
- size: `378`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0xcfb60`

## string_xrefs

- `0xcfc0d`: `privilegedepthmask`
- `0xcfb9a`: `accessmode`
- `0xcfc6a`: `PrivilegeObjectTypeCodes`
- `0xcfbd6`: `privilegeid`
- `0xcfbf7`: `privilegeid`
- `0xcfbfc`: `privilegeid`
- `0xcfc6f`: `privilegeid`
- `0xcfc74`: `privilegeid`
- `0xcfc97`: `privilegeid`
- `0xcfbe6`: `accessright`
- `0xcfbf2`: `RolePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0xcfb60  ldarg.1
0xcfb61  ldstr    aUserid_2// "userId"
0xcfb66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xcfb6b  ldarg.2
0xcfb6c  ldstr    aContext// "context"
0xcfb71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcfb76  ldarga.s 3
0xcfb78  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xcfb7d  brfalse.s loc_CFB88
0xcfb7f  ldarga.s 3
0xcfb81  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xcfb86  brtrue.s loc_CFBAC
0xcfb88  ldc.i4.8
0xcfb89  ldarg.1
0xcfb8a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor(int32, valuetype [mscorlib]System.Guid)
0xcfb8f  stloc.s  7
0xcfb91  ldarg.0
0xcfb92  ldloc.s  7
0xcfb94  ldarg.2
0xcfb95  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::CheckReadPrivilegeAndAccess(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfb9a  ldstr    aAccessmode// "accessmode"
0xcfb9f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcfba4  unbox.any [mscorlib]System.Int32
0xcfba9  stloc.0
0xcfbaa  br.s     loc_CFBB4
0xcfbac  ldarga.s 3
0xcfbae  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xcfbb3  stloc.0
0xcfbb4  ldarg.0
0xcfbb5  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0xcfbba  ldarg.2
0xcfbbb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xcfbc0  stloc.1
0xcfbc1  ldloc.1
0xcfbc2  ldc.i4.1
0xcfbc3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0xcfbc8  ldloc.1
0xcfbc9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xcfbce  ldc.i4.3
0xcfbcf  newarr   [mscorlib]System.String
0xcfbd4  dup
0xcfbd5  ldc.i4.0
0xcfbd6  ldstr    aPrivilegeid// "privilegeid"
0xcfbdb  stelem.ref
0xcfbdc  dup
0xcfbdd  ldc.i4.1
0xcfbde  ldstr    aIsdisabledwhen// "isdisabledwhenintegrated"
0xcfbe3  stelem.ref
0xcfbe4  dup
0xcfbe5  ldc.i4.2
0xcfbe6  ldstr    aAccessright// "accessright"
0xcfbeb  stelem.ref
0xcfbec  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xcfbf1  ldloc.1
0xcfbf2  ldstr    aRoleprivileges// "RolePrivileges"
0xcfbf7  ldstr    aPrivilegeid// "privilegeid"
0xcfbfc  ldstr    aPrivilegeid// "privilegeid"
0xcfc01  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xcfc06  stloc.2
0xcfc07  ldloc.2
0xcfc08  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xcfc0d  ldstr    aPrivilegedepth// "privilegedepthmask"
0xcfc12  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcfc17  ldloc.2
0xcfc18  ldstr    aRole// "Role"
0xcfc1d  ldstr    aParentrootrole// "parentrootroleid"
0xcfc22  ldstr    aRoleid// "roleid"
0xcfc27  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xcfc2c  stloc.3
0xcfc2d  ldloc.3
0xcfc2e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xcfc33  ldstr    aBusinessunitid// "businessunitid"
0xcfc38  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcfc3d  ldloc.3
0xcfc3e  ldstr    aSystemuserrole// "SystemUserRoles"
0xcfc43  ldstr    aRoleid// "roleid"
0xcfc48  ldstr    aRoleid// "roleid"
0xcfc4d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0xcfc52  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0xcfc57  ldstr    aSystemuserid// "systemuserid"
0xcfc5c  ldc.i4.0
0xcfc5d  ldarg.1
0xcfc5e  box      [mscorlib]System.Guid
0xcfc63  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xcfc68  pop
0xcfc69  ldloc.1
0xcfc6a  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCodes"
0xcfc6f  ldstr    aPrivilegeid// "privilegeid"
0xcfc74  ldstr    aPrivilegeid// "privilegeid"
0xcfc79  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0xcfc7e  stloc.s  4
0xcfc80  ldloc.s  4
0xcfc82  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xcfc87  ldstr    aObjecttypecode// "objecttypecode"
0xcfc8c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xcfc91  ldloc.1
0xcfc92  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xcfc97  ldstr    aPrivilegeid// "privilegeid"
0xcfc9c  ldc.i4.0
0xcfc9d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xcfca2  ldarg.0
0xcfca3  ldarg.1
0xcfca4  ldarg.2
0xcfca5  call     instance bool class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::CheckSpecialUser(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfcaa  stloc.s  5
0xcfcac  ldarg.0
0xcfcad  ldloc.1
0xcfcae  ldloc.2
0xcfcaf  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xcfcb4  ldloc.3
0xcfcb5  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xcfcba  ldloc.s  4
0xcfcbc  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0xcfcc1  ldarg.2
0xcfcc2  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::RetrievePrivilegesFromDatabase(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, string, string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcfcc7  stloc.s  6
0xcfcc9  ldarg.0
0xcfcca  ldarg.2
0xcfccb  ldloc.0
0xcfccc  ldloc.s  5
0xcfcce  ldloc.s  6
0xcfcd0  ldarg.s  4
0xcfcd2  ldarg.s  5
0xcfcd4  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] class Microsoft.Crm.ObjectModel.PrivilegeServiceInternal`1<var<u1>>::GetPrivilegeArrayFromCollection(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, bool, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool, bool)
0xcfcd9  ret
```
