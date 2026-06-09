# Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetRoleTemplateIdToRoleIdMap

- ea: `0x4cd50`
- end: `0x4ceb7`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetRoleTemplateIdToRoleIdMap`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3d1c0`

## callees

- `0x4cd50`
- `0x4d220`

## string_xrefs

- `0x4cd6f`: `roletemplateid`
- `0x4cda2`: `roletemplateid`
- `0x4cddd`: `roletemplateid`
- `0x4ce36`: `roletemplateid`
- `0x4ce63`: `roletemplateid`
- `0x4ce7c`: `roletemplateid`
- `0x4ce22`: `RoleTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4cd50  ldarg.0
0x4cd51  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetRootBusinessUnitId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4cd56  stloc.0
0x4cd57  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleService::.ctor()
0x4cd5c  stloc.1
0x4cd5d  ldstr    aRole// "Role"
0x4cd62  ldarg.0
0x4cd63  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4cd68  stloc.2
0x4cd69  ldloc.2
0x4cd6a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4cd6f  ldstr    aRoletemplateid// "roletemplateid"
0x4cd74  ldc.i4.s 0xD
0x4cd76  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x4cd7b  pop
0x4cd7c  ldloc.2
0x4cd7d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4cd82  ldstr    aBusinessunitid// "businessunitid"
0x4cd87  ldc.i4.0
0x4cd88  ldloc.0
0x4cd89  box      [mscorlib]System.Guid
0x4cd8e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4cd93  pop
0x4cd94  ldloc.2
0x4cd95  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4cd9a  ldc.i4.2
0x4cd9b  newarr   [mscorlib]System.String
0x4cda0  dup
0x4cda1  ldc.i4.0
0x4cda2  ldstr    aRoletemplateid// "roletemplateid"
0x4cda7  stelem.ref
0x4cda8  dup
0x4cda9  ldc.i4.1
0x4cdaa  ldstr    aRoleid// "roleid"
0x4cdaf  stelem.ref
0x4cdb0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4cdb5  ldloc.1
0x4cdb6  ldloc.2
0x4cdb7  ldarg.0
0x4cdb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4cdbd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor()
0x4cdc2  stloc.3
0x4cdc3  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4cdc8  stloc.s  5
0x4cdca  br.s     loc_4CE02
0x4cdcc  ldloc.s  5
0x4cdce  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4cdd3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4cdd8  stloc.s  6
0x4cdda  ldloc.3
0x4cddb  ldloc.s  6
0x4cddd  ldstr    aRoletemplateid// "roletemplateid"
0x4cde2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4cde7  unbox.any [mscorlib]System.Guid
0x4cdec  ldloc.s  6
0x4cdee  ldstr    aRoleid// "roleid"
0x4cdf3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4cdf8  unbox.any [mscorlib]System.Guid
0x4cdfd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x4ce02  ldloc.s  5
0x4ce04  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ce09  brtrue.s loc_4CDCC
0x4ce0b  leave.s  loc_4CE22
0x4ce0d  ldloc.s  5
0x4ce0f  isinst   [mscorlib]System.IDisposable
0x4ce14  stloc.s  7
0x4ce16  ldloc.s  7
0x4ce18  brfalse.s loc_4CE21
0x4ce1a  ldloc.s  7
0x4ce1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ce21  endfinally
0x4ce22  ldstr    aRoletemplate// "RoleTemplate"
0x4ce27  ldarg.0
0x4ce28  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4ce2d  stloc.s  4
0x4ce2f  ldloc.s  4
0x4ce31  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4ce36  ldstr    aRoletemplateid// "roletemplateid"
0x4ce3b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x4ce40  ldloc.1
0x4ce41  ldloc.s  4
0x4ce43  ldarg.0
0x4ce44  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ce49  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4ce4e  stloc.s  5
0x4ce50  br.s     loc_4CE95
0x4ce52  ldloc.s  5
0x4ce54  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4ce59  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4ce5e  stloc.s  8
0x4ce60  ldloc.3
0x4ce61  ldloc.s  8
0x4ce63  ldstr    aRoletemplateid// "roletemplateid"
0x4ce68  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4ce6d  unbox.any [mscorlib]System.Guid
0x4ce72  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x4ce77  brtrue.s loc_4CE95
0x4ce79  ldloc.3
0x4ce7a  ldloc.s  8
0x4ce7c  ldstr    aRoletemplateid// "roletemplateid"
0x4ce81  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4ce86  unbox.any [mscorlib]System.Guid
0x4ce8b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ce90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x4ce95  ldloc.s  5
0x4ce97  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ce9c  brtrue.s loc_4CE52
0x4ce9e  leave.s  loc_4CEB5
0x4cea0  ldloc.s  5
0x4cea2  isinst   [mscorlib]System.IDisposable
0x4cea7  stloc.s  7
0x4cea9  ldloc.s  7
0x4ceab  brfalse.s loc_4CEB4
0x4cead  ldloc.s  7
0x4ceaf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ceb4  endfinally
0x4ceb5  ldloc.3
0x4ceb6  ret
```
