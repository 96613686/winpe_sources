# Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::get_AllRoleIds

- ea: `0x4eab0`
- end: `0x4ebe0`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::get_AllRoleIds`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4e930`

## callees

- `0x4e2f0`
- `0x4eab0`
- `0x4ebe0`

## string_xrefs

- `0x4eae0`: `roletemplateid`
- `0x4eb4a`: `roletemplateid`
- `0x4eb71`: `roletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x4eab0  ldarg.0
0x4eab1  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::_allRoleIds
0x4eab6  brtrue   loc_4EBD9
0x4eabb  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RoleService::.ctor()
0x4eac0  stloc.0
0x4eac1  ldstr    aRole// "Role"
0x4eac6  ldarg.0
0x4eac7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4eacc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4ead1  stloc.1
0x4ead2  ldloc.1
0x4ead3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4ead8  ldc.i4.3
0x4ead9  newarr   [mscorlib]System.String
0x4eade  dup
0x4eadf  ldc.i4.0
0x4eae0  ldstr    aRoletemplateid// "roletemplateid"
0x4eae5  stelem.ref
0x4eae6  dup
0x4eae7  ldc.i4.1
0x4eae8  ldstr    aRoleid// "roleid"
0x4eaed  stelem.ref
0x4eaee  dup
0x4eaef  ldc.i4.2
0x4eaf0  ldstr    aBusinessunitid// "businessunitid"
0x4eaf5  stelem.ref
0x4eaf6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4eafb  ldarg.0
0x4eafc  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::GetRootBusinessUnitId()
0x4eb01  stloc.2
0x4eb02  ldloc.0
0x4eb03  ldloc.1
0x4eb04  ldarg.0
0x4eb05  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::context
0x4eb0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4eb0f  ldarg.0
0x4eb10  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4eb15  stfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::_allRoleIds
0x4eb1a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4eb1f  stloc.3
0x4eb20  br.s     loc_4EB9F
0x4eb22  ldloc.3
0x4eb23  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4eb28  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4eb2d  stloc.s  4
0x4eb2f  ldloc.s  4
0x4eb31  ldstr    aBusinessunitid// "businessunitid"
0x4eb36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4eb3b  unbox.any [mscorlib]System.Guid
0x4eb40  ldloc.2
0x4eb41  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4eb46  brfalse.s loc_4EB59
0x4eb48  ldloc.s  4
0x4eb4a  ldstr    aRoletemplateid// "roletemplateid"
0x4eb4f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4eb54  ldnull
0x4eb55  cgt.un
0x4eb57  br.s     loc_4EB5A
0x4eb59  ldc.i4.0
0x4eb5a  brtrue.s loc_4EB6F
0x4eb5c  ldloc.s  4
0x4eb5e  ldstr    aRoleid// "roleid"
0x4eb63  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4eb68  unbox.any [mscorlib]System.Guid
0x4eb6d  br.s     loc_4EB80
0x4eb6f  ldloc.s  4
0x4eb71  ldstr    aRoletemplateid// "roletemplateid"
0x4eb76  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4eb7b  unbox.any [mscorlib]System.Guid
0x4eb80  stloc.s  5
0x4eb82  ldarg.0
0x4eb83  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::_allRoleIds
0x4eb88  ldloc.s  5
0x4eb8a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x4eb8f  brtrue.s loc_4EB9F
0x4eb91  ldarg.0
0x4eb92  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::_allRoleIds
0x4eb97  ldloc.s  5
0x4eb99  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x4eb9e  pop
0x4eb9f  ldloc.3
0x4eba0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4eba5  brtrue   loc_4EB22
0x4ebaa  leave.s  loc_4EBC0
0x4ebac  ldloc.3
0x4ebad  isinst   [mscorlib]System.IDisposable
0x4ebb2  stloc.s  6
0x4ebb4  ldloc.s  6
0x4ebb6  brfalse.s loc_4EBBF
0x4ebb8  ldloc.s  6
0x4ebba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ebbf  endfinally
0x4ebc0  ldarg.0
0x4ebc1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::get_ImportedRoleIds()
0x4ebc6  brfalse.s loc_4EBD9
0x4ebc8  ldarg.0
0x4ebc9  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::_allRoleIds
0x4ebce  ldarg.0
0x4ebcf  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::get_ImportedRoleIds()
0x4ebd4  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::UnionWith(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x4ebd9  ldarg.0
0x4ebda  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportFormXmlHandler::_allRoleIds
0x4ebdf  ret
```
