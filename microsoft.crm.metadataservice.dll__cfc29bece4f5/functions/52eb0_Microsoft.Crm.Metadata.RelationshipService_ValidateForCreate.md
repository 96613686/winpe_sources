# Microsoft.Crm.Metadata.RelationshipService::ValidateForCreate

- ea: `0x52eb0`
- end: `0x52fe0`
- name: `Microsoft.Crm.Metadata.RelationshipService::ValidateForCreate`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f1d0`
- `0x4f690`

## callees

- `0x4cf00`
- `0x4d140`
- `0x4d180`
- `0x4d1a0`
- `0x4d1c0`
- `0x4d1e0`
- `0x4d250`
- `0x52e30`
- `0x52eb0`
- `0x52fe0`
- `0x53160`
- `0x531c0`
- `0x53730`
- `0x538d0`
- `0x53e60`
- `0x55b00`
- `0x57380`
- `0x58380`
- `0x58430`
- `0x58550`

## string_xrefs

- `0x52f98`: `Attribute with Name {0} already exists on entity {1}`

## pseudocode

```c

```

## disassembly

```asm
0x52eb0  ldarg.2
0x52eb1  ldarg.2
0x52eb2  callvirt instance bool Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IsCustomizable()
0x52eb7  brfalse.s loc_52ECC
0x52eb9  ldarg.1
0x52eba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_ReferencedEntityId()
0x52ebf  ldarg.1
0x52ec0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_ReferencingEntityId()
0x52ec5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x52eca  br.s     loc_52ECD
0x52ecc  ldc.i4.0
0x52ecd  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CanChangeHierarchicalSettings(bool value)
0x52ed2  ldarg.2
0x52ed3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RelationshipCreateInfo::get_ReferencedEntity()
0x52ed8  stloc.0
0x52ed9  ldarg.2
0x52eda  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RelationshipCreateInfo::get_ReferencingEntity()
0x52edf  stloc.1
0x52ee0  ldarg.0
0x52ee1  ldloc.0
0x52ee2  ldloc.1
0x52ee3  ldarg.3
0x52ee4  ldloca.s 2
0x52ee6  ldloca.s 3
0x52ee8  call     instance bool Microsoft.Crm.Metadata.RelationshipService::ValidateEntityRolesAndRelationshipPair(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencedEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] int32& errorCode, [out] string& exceptionMessage)
0x52eed  brtrue.s loc_52EF7
0x52eef  ldloc.3
0x52ef0  ldloc.2
0x52ef1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x52ef6  throw
0x52ef7  ldarg.1
0x52ef8  ldloc.1
0x52ef9  ldloc.0
0x52efa  ldarg.3
0x52efb  call     void Microsoft.Crm.Metadata.RelationshipService::ValidateCascadeLinkTypes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencedEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x52f00  ldarg.1
0x52f01  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::get_InnerEntityData()
0x52f06  call     bool Microsoft.Crm.Metadata.RelationshipService::IsRelationshipCascading(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity relationship)
0x52f0b  brfalse.s loc_52F24
0x52f0d  ldarg.0
0x52f0e  ldloc.0
0x52f0f  ldloc.1
0x52f10  ldnull
0x52f11  ldnull
0x52f12  ldarg.3
0x52f13  ldarg.2
0x52f14  callvirt instance bool Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IsPartOfPolymorphicRelationships()
0x52f19  ldarg.1
0x52f1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescription::get_ReferencingAttributeId()
0x52f1f  call     instance void Microsoft.Crm.Metadata.RelationshipService::ValidateParentalRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencedEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingAttribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata referencingAttributeMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isPartOfPolymorphicRelationships, valuetype [mscorlib]System.Guid referencingAttributeId)
0x52f24  ldarg.0
0x52f25  ldarg.2
0x52f26  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x52f2b  ldarg.3
0x52f2c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x52f31  call     instance void Microsoft.Crm.Metadata.RelationshipServiceBase::ValidateEntityRelationshipSchemaName(string schemaName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x52f36  ldarg.2
0x52f37  ldarg.1
0x52f38  ldarg.3
0x52f39  call     bool Microsoft.Crm.Metadata.RelationshipService::ShouldValidateAttributeName(class Microsoft.Crm.Metadata.RelationshipCreateInfo relationshipCreateInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x52f3e  brfalse.s loc_52F58
0x52f40  ldarg.2
0x52f41  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x52f46  newobj   instance void Microsoft.Crm.Metadata.SchemaNameValidator::.ctor(string schemaName)
0x52f4b  dup
0x52f4c  ldc.i4.s 0x64
0x52f4e  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateSchemaName(int32 len)
0x52f53  callvirt instance void Microsoft.Crm.Metadata.SchemaNameValidator::ValidateKeywordConflict()
0x52f58  ldarg.3
0x52f59  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x52f5e  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x52f63  ldc.i4.1
0x52f64  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x52f69  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x52f6e  brtrue.s loc_52FCF
0x52f70  ldarg.3
0x52f71  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x52f76  ldloc.1
0x52f77  ldstr    aEntityid// "entityid"
0x52f7c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52f81  unbox.any [mscorlib]System.Guid
0x52f86  ldarg.2
0x52f87  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x52f8c  call     bool Microsoft.Crm.Metadata.RelationshipService::DoesAttributeWithSameNameExist(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, valuetype [mscorlib]System.Guid entityId, string attributeLogicalName)
0x52f91  brfalse.s loc_52FCF
0x52f93  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52f98  ldstr    aAttributeWithN// "Attribute with Name {0} already exists "...
0x52f9d  ldc.i4.2
0x52f9e  newarr   [mscorlib]System.Object
0x52fa3  dup
0x52fa4  ldc.i4.0
0x52fa5  ldarg.2
0x52fa6  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelationshipAttributeName()
0x52fab  stelem.ref
0x52fac  dup
0x52fad  ldc.i4.1
0x52fae  ldloc.1
0x52faf  ldstr    aName// "name"
0x52fb4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x52fb9  castclass [mscorlib]System.String
0x52fbe  stelem.ref
0x52fbf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52fc4  ldc.i4   0x80047013
0x52fc9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x52fce  throw
0x52fcf  ldarg.0
0x52fd0  ldloc.0
0x52fd1  ldloc.1
0x52fd2  call     instance void Microsoft.Crm.Metadata.RelationshipService::ValidateVirtualEntityRelationships(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencedEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity referencingEntity)
0x52fd7  ldarg.0
0x52fd8  ldarg.2
0x52fd9  ldarg.1
0x52fda  call     instance void Microsoft.Crm.Metadata.RelationshipService::ValidateForCreateHierarchyEntityRelationship(class Microsoft.Crm.Metadata.RelationshipCreateInfo relationshipInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription)
0x52fdf  ret
```
