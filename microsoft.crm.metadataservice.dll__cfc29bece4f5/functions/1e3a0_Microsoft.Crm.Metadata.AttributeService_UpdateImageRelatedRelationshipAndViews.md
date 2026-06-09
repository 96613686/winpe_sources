# Microsoft.Crm.Metadata.AttributeService::UpdateImageRelatedRelationshipAndViews

- ea: `0x1e3a0`
- end: `0x1e406`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateImageRelatedRelationshipAndViews`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1e910`

## callees

- `0x184d0`
- `0x1e1d0`
- `0x1e260`
- `0x23300`
- `0x554c0`
- `0x55aa0`

## string_xrefs

- `0x1e3c8`: `ImageDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0x1e3a0  ldarg.0
0x1e3a1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1e3a6  ldarg.s  4
0x1e3a8  ldc.i4.1
0x1e3a9  newarr   [mscorlib]System.String
0x1e3ae  dup
0x1e3af  ldc.i4.0
0x1e3b0  ldstr    aPhysicalname// "physicalname"
0x1e3b5  stelem.ref
0x1e3b6  ldarg.s  5
0x1e3b8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1e3bd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription Microsoft.Crm.Metadata.AttributeService::GetParentEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, string[] columnNames, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1e3c2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_PhysicalName()
0x1e3c7  stloc.0
0x1e3c8  ldstr    aImagedescripto// "ImageDescriptor"
0x1e3cd  stloc.1
0x1e3ce  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::ImageDescriptor_EntityId
0x1e3d3  pop
0x1e3d4  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::ImageDescriptorId_AttributeId
0x1e3d9  pop
0x1e3da  ldarg.0
0x1e3db  ldarg.1
0x1e3dc  ldloc.1
0x1e3dd  ldloc.0
0x1e3de  ldarg.s  4
0x1e3e0  ldarg.s  5
0x1e3e2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeService::BuildImageRelationshipPropertyBag(class Microsoft.Crm.Metadata.AttributeInfo imageAttributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag imageId, string referencedEntityName, string referencingEntityName, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1e3e7  stloc.2
0x1e3e8  ldloc.2
0x1e3e9  ldarg.0
0x1e3ea  ldarg.s  5
0x1e3ec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeService::BuildImageEntityRelationshipPropertyBag(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class Microsoft.Crm.Metadata.AttributeInfo imageAttributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1e3f1  dup
0x1e3f2  ldloc.2
0x1e3f3  ldarg.s  5
0x1e3f5  call     void Microsoft.Crm.Metadata.RelationshipService::FixRelationshipPropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag entityRelationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1e3fa  ldloc.2
0x1e3fb  ldarg.s  5
0x1e3fd  ldarg.s  4
0x1e3ff  call     bool Microsoft.Crm.Metadata.RelationshipService::TryUpdateRelationshipInsteadOfCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipDescriptionPropertyBag entityRelationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1e404  pop
0x1e405  ret
```
