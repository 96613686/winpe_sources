# Microsoft.Crm.Metadata.RelationshipService::CreateDefaultMapping

- ea: `0x54ce0`
- end: `0x54edd`
- name: `Microsoft.Crm.Metadata.RelationshipService::CreateDefaultMapping`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f690`

## callees

- `0x404f0`
- `0x40900`
- `0x4cf00`
- `0x4d140`
- `0x4d3e0`
- `0x54cc0`
- `0x54ce0`
- `0x56370`
- `0x56390`
- `0x76f30`
- `0x76f70`

## string_xrefs

- `0x54d21`: `Entity {0} is not mappable so an attribute map will not be created for relationship {1}`
- `0x54d76`: `Entity {0} is not mappable so an attribute map will not be created for relationship {1}`

## pseudocode

```c

```

## disassembly

```asm
0x54ce0  ldarg.s  5
0x54ce2  brfalse.s loc_54CF9
0x54ce4  ldarg.s  4
0x54ce6  newobj   instance void Microsoft.Crm.Metadata.RelationshipOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x54ceb  ldarg.1
0x54cec  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x54cf1  call     instance bool Microsoft.Crm.Metadata.RelationshipOverrider::ShouldSkipAttributeMapCreate(string schemeName)
0x54cf6  brfalse.s loc_54CF9
0x54cf8  ret
0x54cf9  ldarg.2
0x54cfa  ldstr    aIsmappable// "ismappable"
0x54cff  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x54d04  brtrue.s loc_54D18
0x54d06  ldarg.2
0x54d07  ldstr    aIsmappable// "ismappable"
0x54d0c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54d11  unbox.any [mscorlib]System.Boolean
0x54d16  brtrue.s loc_54D4E
0x54d18  ldarg.s  4
0x54d1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x54d1f  ldc.i4.s 0x19
0x54d21  ldstr    aEntity0IsNotMa// "Entity {0} is not mappable so an attrib"...
0x54d26  ldc.i4.2
0x54d27  newarr   [mscorlib]System.Object
0x54d2c  dup
0x54d2d  ldc.i4.0
0x54d2e  ldarg.2
0x54d2f  ldstr    aName// "name"
0x54d34  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54d39  castclass [mscorlib]System.String
0x54d3e  stelem.ref
0x54d3f  dup
0x54d40  ldc.i4.1
0x54d41  ldarg.1
0x54d42  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x54d47  stelem.ref
0x54d48  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x54d4d  ret
0x54d4e  ldarg.3
0x54d4f  ldstr    aIsmappable// "ismappable"
0x54d54  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x54d59  brtrue.s loc_54D6D
0x54d5b  ldarg.3
0x54d5c  ldstr    aIsmappable// "ismappable"
0x54d61  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54d66  unbox.any [mscorlib]System.Boolean
0x54d6b  brtrue.s loc_54DA3
0x54d6d  ldarg.s  4
0x54d6f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x54d74  ldc.i4.s 0x19
0x54d76  ldstr    aEntity0IsNotMa// "Entity {0} is not mappable so an attrib"...
0x54d7b  ldc.i4.2
0x54d7c  newarr   [mscorlib]System.Object
0x54d81  dup
0x54d82  ldc.i4.0
0x54d83  ldarg.3
0x54d84  ldstr    aName// "name"
0x54d89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54d8e  castclass [mscorlib]System.String
0x54d93  stelem.ref
0x54d94  dup
0x54d95  ldc.i4.1
0x54d96  ldarg.1
0x54d97  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x54d9c  stelem.ref
0x54d9d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x54da2  ret
0x54da3  ldarg.2
0x54da4  ldstr    aEntityid// "entityid"
0x54da9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54dae  unbox.any [mscorlib]System.Guid
0x54db3  stloc.0
0x54db4  ldstr    aAttribute// "Attribute"
0x54db9  ldc.i4.1
0x54dba  newarr   [mscorlib]System.String
0x54dbf  dup
0x54dc0  ldc.i4.0
0x54dc1  ldstr    aLogicalname// "logicalname"
0x54dc6  stelem.ref
0x54dc7  ldarg.s  4
0x54dc9  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54dce  stloc.1
0x54dcf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::.ctor()
0x54dd4  dup
0x54dd5  ldloc.0
0x54dd6  ldloc.1
0x54dd7  ldarg.s  4
0x54dd9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x54dde  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrievePrimaryKeyAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x54de3  stloc.2
0x54de4  ldloc.0
0x54de5  ldloc.1
0x54de6  ldarg.s  4
0x54de8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x54ded  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrievePrimaryFieldAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x54df2  stloc.3
0x54df3  ldloc.2
0x54df4  ldstr    aLogicalname// "logicalname"
0x54df9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54dfe  castclass [mscorlib]System.String
0x54e03  ldarg.1
0x54e04  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x54e09  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54e0e  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x54e13  ldc.i4.1
0x54e14  newobj   instance void AttributeMapping::.ctor(string sourceName, string targetName, bool isSytem)
0x54e19  stloc.s  4
0x54e1b  ldloc.s  4
0x54e1d  ldloc.3
0x54e1e  ldstr    aLogicalname// "logicalname"
0x54e23  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54e28  castclass [mscorlib]System.String
0x54e2d  ldarg.1
0x54e2e  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_NameViewAttribute()
0x54e33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54e38  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x54e3d  callvirt instance class AttributeMapping AttributeMapping::AddChildAttributeMapping(string sourceName, string targetName)
0x54e42  pop
0x54e43  ldarg.2
0x54e44  ldstr    aLogicalname// "logicalname"
0x54e49  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54e4e  castclass [mscorlib]System.String
0x54e53  ldarg.3
0x54e54  ldstr    aLogicalname// "logicalname"
0x54e59  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54e5e  castclass [mscorlib]System.String
0x54e63  ldarg.s  4
0x54e65  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityMappingHelper::TryGetEntityMapId(string sourceEntityName, string targetEntityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x54e6a  stloc.s  5
0x54e6c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54e71  ldloc.s  5
0x54e73  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x54e78  brfalse.s loc_54EB2
0x54e7a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x54e7f  stloc.s  6
0x54e81  ldloc.s  6
0x54e83  ldloc.s  4
0x54e85  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x54e8a  pop
0x54e8b  ldarg.s  4
0x54e8d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSetSolutionToDefaultModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x54e92  stloc.s  7
0x54e94  ldloc.s  5
0x54e96  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54e9b  ldloc.s  6
0x54e9d  ldarg.s  4
0x54e9f  call     void Microsoft.Crm.Metadata.EntityMappingHelper::CreateAttributeMappings(valuetype [mscorlib]System.Guid entityMappingId, valuetype [mscorlib]System.Guid parentAttributeMappingId, class [mscorlib]System.Collections.ArrayList attributeMappings, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x54ea4  leave.s  loc_54EDC
0x54ea6  ldloc.s  7
0x54ea8  brfalse.s loc_54EB1
0x54eaa  ldloc.s  7
0x54eac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54eb1  endfinally
0x54eb2  ldarg.0
0x54eb3  ldarg.2
0x54eb4  ldstr    aLogicalname// "logicalname"
0x54eb9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54ebe  castclass [mscorlib]System.String
0x54ec3  ldarg.3
0x54ec4  ldstr    aLogicalname// "logicalname"
0x54ec9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x54ece  castclass [mscorlib]System.String
0x54ed3  ldloc.s  4
0x54ed5  ldarg.s  4
0x54ed7  call     instance void Microsoft.Crm.Metadata.RelationshipService::CreateEntityMapping(string referencedEntityLogicalName, string referencingEntityLogicalName, class AttributeMapping primaryKeyMapping, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x54edc  ret
```
