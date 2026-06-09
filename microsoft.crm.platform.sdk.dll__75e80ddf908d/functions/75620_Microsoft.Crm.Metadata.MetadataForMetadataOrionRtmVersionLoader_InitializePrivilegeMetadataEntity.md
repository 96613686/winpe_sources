# Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializePrivilegeMetadataEntity

- ea: `0x75620`
- end: `0x757b4`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializePrivilegeMetadataEntity`
- size: `404`
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

- `0x75620`: `Privilege`
- `0x75665`: `PrivilegeId`
- `0x75785`: `AccessRight`
- `0x7566a`: `privilegeid`
- `0x7578a`: `accessright`
- `0x75625`: `PrivilegeBase`

## pseudocode

```c

```

## disassembly

```asm
0x75620  ldstr    aPrivilege// "Privilege"
0x75625  ldstr    aPrivilegebase// "PrivilegeBase"
0x7562a  ldnull
0x7562b  ldnull
0x7562c  ldnull
0x7562d  ldnull
0x7562e  ldnull
0x7562f  ldc.i4.0
0x75630  ldc.i4.0
0x75631  ldc.i4.s 9
0x75633  ldloca.s 1
0x75635  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x7563b  ldloc.1
0x7563c  ldloca.s 1
0x7563e  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x75644  ldloc.1
0x75645  ldnull
0x75646  ldnull
0x75647  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadataDescription::.ctor(string metadataEntityName, string tableName, string idsTableName, string logicalViewName, string standardViewName, string logicalAsIfPublishedViewName, string standardAsIfPublishedViewName, bool areSystemRecordsDeletable, bool isPublishable, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode typeCode, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId, string externalName, string externalCollectionName)
0x7564c  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadataDescription description)
0x75651  stloc.0
0x75652  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::get_MetadataForMetadata()
0x75657  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x7565c  ldloc.0
0x7565d  call     class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary metadataEntities, class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity)
0x75662  pop
0x75663  ldloc.0
0x75664  ldc.i4.0
0x75665  ldstr    aPrivilegeid_0// "PrivilegeId"
0x7566a  ldstr    aPrivilegeid_1// "privilegeid"
0x7566f  ldc.i4.0
0x75670  ldc.i4.0
0x75671  ldc.i4.1
0x75672  ldc.i4.1
0x75673  ldc.i4.1
0x75674  ldc.i4.0
0x75675  ldc.i4.0
0x75676  ldc.i4.0
0x75677  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7567c  ldc.i4.0
0x7567d  ldc.i4.0
0x7567e  ldc.i4.0
0x7567f  ldc.i4.1
0x75680  ldnull
0x75681  ldc.i4.0
0x75682  ldnull
0x75683  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75688  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7568d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75692  pop
0x75693  ldloc.0
0x75694  ldc.i4.1
0x75695  ldstr    aName// "Name"
0x7569a  ldstr    aName_0// "name"
0x7569f  ldc.i4.1
0x756a0  ldc.i4.1
0x756a1  ldc.i4.0
0x756a2  ldc.i4.0
0x756a3  ldc.i4.0
0x756a4  ldc.i4.0
0x756a5  ldc.i4.0
0x756a6  ldc.i4.2
0x756a7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x756ac  ldc.i4.0
0x756ad  ldc.i4.0
0x756ae  ldc.i4.0
0x756af  ldc.i4.1
0x756b0  ldnull
0x756b1  ldc.i4.0
0x756b2  ldnull
0x756b3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x756b8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x756bd  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x756c2  pop
0x756c3  ldloc.0
0x756c4  ldc.i4.2
0x756c5  ldstr    aCanbebasic// "CanBeBasic"
0x756ca  ldstr    aCanbebasic_0// "canbebasic"
0x756cf  ldc.i4.1
0x756d0  ldc.i4.1
0x756d1  ldc.i4.0
0x756d2  ldc.i4.0
0x756d3  ldc.i4.0
0x756d4  ldc.i4.0
0x756d5  ldc.i4.0
0x756d6  ldc.i4.3
0x756d7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x756dc  ldc.i4.0
0x756dd  ldc.i4.0
0x756de  ldc.i4.0
0x756df  ldc.i4.1
0x756e0  ldnull
0x756e1  ldc.i4.0
0x756e2  ldnull
0x756e3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x756e8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x756ed  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x756f2  pop
0x756f3  ldloc.0
0x756f4  ldc.i4.3
0x756f5  ldstr    aCanbelocal// "CanBeLocal"
0x756fa  ldstr    aCanbelocal_0// "canbelocal"
0x756ff  ldc.i4.1
0x75700  ldc.i4.1
0x75701  ldc.i4.0
0x75702  ldc.i4.0
0x75703  ldc.i4.0
0x75704  ldc.i4.0
0x75705  ldc.i4.0
0x75706  ldc.i4.3
0x75707  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7570c  ldc.i4.0
0x7570d  ldc.i4.0
0x7570e  ldc.i4.0
0x7570f  ldc.i4.1
0x75710  ldnull
0x75711  ldc.i4.0
0x75712  ldnull
0x75713  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75718  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7571d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75722  pop
0x75723  ldloc.0
0x75724  ldc.i4.4
0x75725  ldstr    aCanbedeep// "CanBeDeep"
0x7572a  ldstr    aCanbedeep_0// "canbedeep"
0x7572f  ldc.i4.1
0x75730  ldc.i4.1
0x75731  ldc.i4.0
0x75732  ldc.i4.0
0x75733  ldc.i4.0
0x75734  ldc.i4.0
0x75735  ldc.i4.0
0x75736  ldc.i4.3
0x75737  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7573c  ldc.i4.0
0x7573d  ldc.i4.0
0x7573e  ldc.i4.0
0x7573f  ldc.i4.1
0x75740  ldnull
0x75741  ldc.i4.0
0x75742  ldnull
0x75743  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75748  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7574d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75752  pop
0x75753  ldloc.0
0x75754  ldc.i4.5
0x75755  ldstr    aCanbeglobal// "CanBeGlobal"
0x7575a  ldstr    aCanbeglobal_0// "canbeglobal"
0x7575f  ldc.i4.1
0x75760  ldc.i4.1
0x75761  ldc.i4.0
0x75762  ldc.i4.0
0x75763  ldc.i4.0
0x75764  ldc.i4.0
0x75765  ldc.i4.0
0x75766  ldc.i4.3
0x75767  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7576c  ldc.i4.0
0x7576d  ldc.i4.0
0x7576e  ldc.i4.0
0x7576f  ldc.i4.1
0x75770  ldnull
0x75771  ldc.i4.0
0x75772  ldnull
0x75773  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75778  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7577d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75782  pop
0x75783  ldloc.0
0x75784  ldc.i4.6
0x75785  ldstr    aAccessright// "AccessRight"
0x7578a  ldstr    aAccessright_0// "accessright"
0x7578f  ldc.i4.1
0x75790  ldc.i4.1
0x75791  ldc.i4.0
0x75792  ldc.i4.0
0x75793  ldc.i4.0
0x75794  ldc.i4.0
0x75795  ldc.i4.0
0x75796  ldc.i4.1
0x75797  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7579c  ldc.i4.0
0x7579d  ldc.i4.0
0x7579e  ldc.i4.0
0x7579f  ldc.i4.1
0x757a0  ldnull
0x757a1  ldc.i4.0
0x757a2  ldnull
0x757a3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x757a8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x757ad  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x757b2  pop
0x757b3  ret
```
