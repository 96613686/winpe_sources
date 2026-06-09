# Microsoft.Crm.Metadata.AttributeService::UpdateOutOfBoxRollupOrCalculatedFields

- ea: `0x23970`
- end: `0x23a85`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateOutOfBoxRollupOrCalculatedFields`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x23970`
- `0x23a90`
- `0x23e60`
- `0x25060`

## string_xrefs

- `0x23a0c`: `extensiontablename`
- `0x23a3e`: `extensiontablename`

## pseudocode

```c

```

## disassembly

```asm
0x23970  ldarg.0
0x23971  box      [mscorlib]System.Guid
0x23976  ldstr    aAttributeid_0// "attributeId"
0x2397b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x23980  ldarg.2
0x23981  ldstr    aContext// "context"
0x23986  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2398b  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x23990  ldarg.0
0x23991  ldstr    aAttribute// "Attribute"
0x23996  ldarg.2
0x23997  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2399c  stloc.0
0x2399d  ldloc.0
0x2399e  ldarg.2
0x2399f  call     bool Microsoft.Crm.Metadata.AttributeService::IsUpdateableRollupOrCalculatedFields(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x239a4  brfalse  loc_23A84
0x239a9  ldloc.0
0x239aa  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x239af  stloc.1
0x239b0  ldloc.1
0x239b1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceType()
0x239b6  stloc.2
0x239b7  ldloc.2
0x239b8  ldc.i4.1
0x239b9  beq.s    loc_239DA
0x239bb  ldloc.2
0x239bc  ldc.i4.2
0x239bd  bne.un   loc_23A84
0x239c2  ldarg.1
0x239c3  brfalse.s loc_239D1
0x239c5  ldloc.1
0x239c6  ldarg.2
0x239c7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x239cc  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::CreateIndexForRollupAndCalculatedField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x239d1  ldloc.1
0x239d2  ldarg.2
0x239d3  ldc.i4.1
0x239d4  call     void Microsoft.Crm.Metadata.AttributeService::SetRollupProperties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attribute, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool IsInstallOrPatch)
0x239d9  ret
0x239da  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x239df  ldloc.0
0x239e0  ldstr    aEntityid// "entityid"
0x239e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x239ea  unbox.any [mscorlib]System.Guid
0x239ef  ldstr    aEntity_0// "Entity"
0x239f4  ldc.i4.3
0x239f5  newarr   [mscorlib]System.String
0x239fa  dup
0x239fb  ldc.i4.0
0x239fc  ldstr    aIslogicalentit// "islogicalentity"
0x23a01  stelem.ref
0x23a02  dup
0x23a03  ldc.i4.1
0x23a04  ldstr    aBasetablename// "basetablename"
0x23a09  stelem.ref
0x23a0a  dup
0x23a0b  ldc.i4.2
0x23a0c  ldstr    aExtensiontable// "extensiontablename"
0x23a11  stelem.ref
0x23a12  ldarg.2
0x23a13  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23a18  stloc.3
0x23a19  ldloc.0
0x23a1a  ldstr    aIsstoredonprim// "isstoredonprimarytable"
0x23a1f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23a24  unbox.any [mscorlib]System.Boolean
0x23a29  brfalse.s loc_23A3D
0x23a2b  ldloc.3
0x23a2c  ldstr    aBasetablename// "basetablename"
0x23a31  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23a36  castclass [mscorlib]System.String
0x23a3b  br.s     loc_23A4D
0x23a3d  ldloc.3
0x23a3e  ldstr    aExtensiontable// "extensiontablename"
0x23a43  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23a48  castclass [mscorlib]System.String
0x23a4d  stloc.s  4
0x23a4f  ldloc.0
0x23a50  ldstr    aTablecolumnnam// "tablecolumnname"
0x23a55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23a5a  castclass [mscorlib]System.String
0x23a5f  stloc.s  5
0x23a61  ldloc.0
0x23a62  ldloc.s  4
0x23a64  ldloc.s  5
0x23a66  ldarg.2
0x23a67  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x23a6c  ldc.i4.1
0x23a6d  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x23a72  ldarg.2
0x23a73  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x23a78  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::UpdateCalculatedField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, string, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext)
0x23a7d  ldloc.0
0x23a7e  ldarg.2
0x23a7f  call     void Microsoft.Crm.Metadata.AttributeService::ResetSourceTypeMask(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23a84  ret
```
