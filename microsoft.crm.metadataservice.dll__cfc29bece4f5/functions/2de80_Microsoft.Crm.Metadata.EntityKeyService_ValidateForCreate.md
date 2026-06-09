# Microsoft.Crm.Metadata.EntityKeyService::ValidateForCreate

- ea: `0x2de80`
- end: `0x2df36`
- name: `Microsoft.Crm.Metadata.EntityKeyService::ValidateForCreate`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ddd0`

## callees

- `0x2d840`
- `0x2d860`
- `0x2d8b0`
- `0x2d8d0`
- `0x2de80`
- `0x2df40`
- `0x2e1f0`
- `0x2e470`
- `0x2e5a0`
- `0x2e660`
- `0x2e6e0`
- `0x456b0`
- `0x49cc0`

## string_xrefs

- `0x2deba`: `Cannot create an EntityKey without specifying an entity id`

## pseudocode

```c

```

## disassembly

```asm
0x2de80  ldarg.0
0x2de81  ldarg.1
0x2de82  ldarg.3
0x2de83  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateIfParentEntityIsVirtual(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2de88  ldstr    aEntitykey// "EntityKey"
0x2de8d  ldarg.1
0x2de8e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityKeyDescription()
0x2de93  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyDescriptionPropertyBag::get_InnerEntityData()
0x2de98  ldstr    aEntitykeyid// "entitykeyid"
0x2de9d  ldarg.3
0x2de9e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2dea3  call     void Microsoft.Crm.Metadata.MetadataValidator::ValidateMetadataIdIsSetAndUnique(string metadataEntityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataBusinessEntity, string metadataIdColumnName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x2dea8  ldarg.1
0x2dea9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityId()
0x2deae  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2deb3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2deb8  brfalse.s loc_2DEC5
0x2deba  ldstr    aCannotCreateAn_0// "Cannot create an EntityKey without spec"...
0x2debf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x2dec4  throw
0x2dec5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x2deca  ldarg.3
0x2decb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2ded0  ldarg.3
0x2ded1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x2ded6  stloc.0
0x2ded7  ldarg.0
0x2ded8  ldarg.1
0x2ded9  ldloc.0
0x2deda  ldarg.3
0x2dedb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2dee0  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateParentEntity(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings orgSettings, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x2dee5  ldarg.0
0x2dee6  ldarg.1
0x2dee7  ldarg.2
0x2dee8  ldarg.3
0x2dee9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2deee  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateEntityKeyNameForCreate(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, bool isInternalSolution, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x2def3  ldarg.0
0x2def4  ldarg.1
0x2def5  ldarg.3
0x2def6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2defb  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateEntityKeyWithSelectedAttributesDoesNotExist(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x2df00  ldarg.0
0x2df01  ldarg.1
0x2df02  ldloc.0
0x2df03  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateEntityKeyForCreate(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings orgSettings)
0x2df08  ldarg.0
0x2df09  ldarg.1
0x2df0a  ldloc.0
0x2df0b  ldarg.3
0x2df0c  call     instance void Microsoft.Crm.Metadata.EntityKeyService::ValidateAllAttributes(class Microsoft.Crm.Metadata.EntityKeyCreateInfo entityKeyInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings orgSettings, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2df11  ldarg.1
0x2df12  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_DisplayName()
0x2df17  ldarg.1
0x2df18  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityKeyCreateInfo::get_EntityKeyId()
0x2df1d  ldstr    aDisplayname// "DisplayName"
0x2df22  ldc.i4.s 0x15
0x2df24  ldstr    aEntityKeyDispl// "Entity Key display name"
0x2df29  ldarg.3
0x2df2a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x2df2f  ldc.i4.1
0x2df30  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::ValidateLabelCollectionContents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string parameterName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [opt] bool throwIfCollectionIsNullOrEmpty)
0x2df35  ret
```
