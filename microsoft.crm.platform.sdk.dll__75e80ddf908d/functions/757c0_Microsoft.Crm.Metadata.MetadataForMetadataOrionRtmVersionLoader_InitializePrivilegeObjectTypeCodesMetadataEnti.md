# Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializePrivilegeObjectTypeCodesMetadataEntity

- ea: `0x757c0`
- end: `0x75894`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializePrivilegeObjectTypeCodesMetadataEntity`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x72170`

## callees

- `0x70970`
- `0x70f50`
- `0x71340`
- `0x71790`
- `0x71970`
- `0x71fa0`
- `0x71fb0`
- `0x72120`

## string_xrefs

- `0x757c0`: `PrivilegeObjectTypeCode`
- `0x75835`: `PrivilegeId`
- `0x7583a`: `privilegeid`
- `0x75805`: `PrivilegeObjectTypeCodeId`
- `0x7580a`: `privilegeobjecttypecodeid`
- `0x757c5`: `PrivilegeObjectTypeCodes`

## pseudocode

```c

```

## disassembly

```asm
0x757c0  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x757c5  ldstr    aPrivilegeobjec_6// "PrivilegeObjectTypeCodes"
0x757ca  ldnull
0x757cb  ldnull
0x757cc  ldnull
0x757cd  ldnull
0x757ce  ldnull
0x757cf  ldc.i4.0
0x757d0  ldc.i4.0
0x757d1  ldc.i4.s 0xA
0x757d3  ldloca.s 1
0x757d5  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x757db  ldloc.1
0x757dc  ldloca.s 1
0x757de  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x757e4  ldloc.1
0x757e5  ldnull
0x757e6  ldnull
0x757e7  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadataDescription::.ctor(string metadataEntityName, string tableName, string idsTableName, string logicalViewName, string standardViewName, string logicalAsIfPublishedViewName, string standardAsIfPublishedViewName, bool areSystemRecordsDeletable, bool isPublishable, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode typeCode, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId, string externalName, string externalCollectionName)
0x757ec  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadataDescription description)
0x757f1  stloc.0
0x757f2  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::get_MetadataForMetadata()
0x757f7  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x757fc  ldloc.0
0x757fd  call     class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary metadataEntities, class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity)
0x75802  pop
0x75803  ldloc.0
0x75804  ldc.i4.0
0x75805  ldstr    aPrivilegeobjec_1// "PrivilegeObjectTypeCodeId"
0x7580a  ldstr    aPrivilegeobjec_3// "privilegeobjecttypecodeid"
0x7580f  ldc.i4.0
0x75810  ldc.i4.0
0x75811  ldc.i4.1
0x75812  ldc.i4.1
0x75813  ldc.i4.0
0x75814  ldc.i4.0
0x75815  ldc.i4.0
0x75816  ldc.i4.0
0x75817  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7581c  ldc.i4.0
0x7581d  ldc.i4.0
0x7581e  ldc.i4.0
0x7581f  ldc.i4.1
0x75820  ldnull
0x75821  ldc.i4.0
0x75822  ldnull
0x75823  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75828  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7582d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75832  pop
0x75833  ldloc.0
0x75834  ldc.i4.1
0x75835  ldstr    aPrivilegeid_0// "PrivilegeId"
0x7583a  ldstr    aPrivilegeid_1// "privilegeid"
0x7583f  ldc.i4.0
0x75840  ldc.i4.0
0x75841  ldc.i4.0
0x75842  ldc.i4.0
0x75843  ldc.i4.1
0x75844  ldc.i4.0
0x75845  ldc.i4.0
0x75846  ldc.i4.0
0x75847  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7584c  ldc.i4.0
0x7584d  ldc.i4.0
0x7584e  ldc.i4.0
0x7584f  ldc.i4.1
0x75850  ldnull
0x75851  ldc.i4.0
0x75852  ldnull
0x75853  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75858  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7585d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75862  pop
0x75863  ldloc.0
0x75864  ldc.i4.2
0x75865  ldstr    aObjecttypecode// "ObjectTypeCode"
0x7586a  ldstr    aObjecttypecode_0// "objecttypecode"
0x7586f  ldc.i4.1
0x75870  ldc.i4.0
0x75871  ldc.i4.0
0x75872  ldc.i4.0
0x75873  ldc.i4.1
0x75874  ldc.i4.0
0x75875  ldc.i4.0
0x75876  ldc.i4.1
0x75877  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7587c  ldc.i4.0
0x7587d  ldc.i4.0
0x7587e  ldc.i4.0
0x7587f  ldc.i4.1
0x75880  ldnull
0x75881  ldc.i4.0
0x75882  ldnull
0x75883  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75888  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7588d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75892  pop
0x75893  ret
```
