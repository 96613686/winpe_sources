# Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::RetrievePermissions

- ea: `0x56180`
- end: `0x5626e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::RetrievePermissions`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x55ee0`

## callees

- `0x56180`

## string_xrefs

- `0x561d8`: `fieldsecurityprofileid`
- `0x561b7`: `canread`
- `0x561bf`: `canupdate`
- `0x561c7`: `cancreate`

## pseudocode

```c

```

## disassembly

```asm
0x56180  ldstr    aFieldpermissio// "FieldPermission"
0x56185  ldarg.0
0x56186  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x5618b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x56190  stloc.0
0x56191  ldloc.0
0x56192  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x56197  ldc.i4.6
0x56198  newarr   [mscorlib]System.String
0x5619d  dup
0x5619e  ldc.i4.0
0x5619f  ldstr    aFieldpermissio_0// "fieldpermissionid"
0x561a4  stelem.ref
0x561a5  dup
0x561a6  ldc.i4.1
0x561a7  ldstr    aEntityname_0// "entityname"
0x561ac  stelem.ref
0x561ad  dup
0x561ae  ldc.i4.2
0x561af  ldstr    aAttributelogic_0// "attributelogicalname"
0x561b4  stelem.ref
0x561b5  dup
0x561b6  ldc.i4.3
0x561b7  ldstr    aCanread_0// "canread"
0x561bc  stelem.ref
0x561bd  dup
0x561be  ldc.i4.4
0x561bf  ldstr    aCanupdate_0// "canupdate"
0x561c4  stelem.ref
0x561c5  dup
0x561c6  ldc.i4.5
0x561c7  ldstr    aCancreate_0// "cancreate"
0x561cc  stelem.ref
0x561cd  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x561d2  ldloc.0
0x561d3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x561d8  ldstr    aFieldsecurityp_0// "fieldsecurityprofileid"
0x561dd  ldc.i4.0
0x561de  ldarg.1
0x561df  box      [mscorlib]System.Guid
0x561e4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x561e9  pop
0x561ea  ldarg.2
0x561eb  ldloc.0
0x561ec  ldc.i4.4
0x561ed  ldarg.0
0x561ee  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileHandler::_context
0x561f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x561f8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x561fd  stloc.1
0x561fe  br.s     loc_5624F
0x56200  ldloc.1
0x56201  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x56206  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission
0x5620b  stloc.2
0x5620c  ldarg.s  4
0x5620e  ldloc.2
0x5620f  ldstr    aEntityname_0// "entityname"
0x56214  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x56219  unbox.any [mscorlib]System.Int32
0x5621e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x56223  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x56228  ldstr    asc_CD6F2// ":"
0x5622d  ldloc.2
0x5622e  ldstr    aAttributelogic_0// "attributelogicalname"
0x56233  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x56238  call     string [mscorlib]System.String::Concat(object, object, object)
0x5623d  stloc.3
0x5623e  ldarg.3
0x5623f  ldloc.3
0x56240  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::ContainsKey(var<u1>)
0x56245  brtrue.s loc_5624F
0x56247  ldarg.3
0x56248  ldloc.3
0x56249  ldloc.2
0x5624a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.FieldPermission>::Add(var<u1>, !!T0)
0x5624f  ldloc.1
0x56250  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x56255  brtrue.s loc_56200
0x56257  leave.s  loc_5626D
0x56259  ldloc.1
0x5625a  isinst   [mscorlib]System.IDisposable
0x5625f  stloc.s  4
0x56261  ldloc.s  4
0x56263  brfalse.s loc_5626C
0x56265  ldloc.s  4
0x56267  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5626c  endfinally
0x5626d  ret
```
