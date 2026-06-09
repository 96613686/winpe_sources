# Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeAttributeMetadataEntity

- ea: `0x73bf0`
- end: `0x74b02`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeAttributeMetadataEntity`
- size: `3858`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x72170`

## callees

- `0x70970`
- `0x70f50`
- `0x712b0`
- `0x712f0`
- `0x71690`
- `0x716f0`
- `0x71790`
- `0x71970`
- `0x71c80`
- `0x71cf0`
- `0x71fa0`
- `0x71fb0`
- `0x71fc0`
- `0x72000`
- `0x72050`
- `0x72120`

## string_xrefs

- `0x73d78`: `XmlAbbreviation`
- `0x7433f`: `LinkedAttributeId`
- `0x74186`: `IsIdentity`
- `0x74465`: `CanBeSecuredForCreate`
- `0x74496`: `CanBeSecuredForRead`
- `0x744c7`: `CanBeSecuredForUpdate`
- `0x7455a`: `ManagedPropertyParentComponentType`
- `0x748e7`: `IsRenameable`
- `0x73e6d`: `ValidForUpdateAPI`
- `0x73ecf`: `ValidForReadAPI`
- `0x73f00`: `ValidForCreateAPI`
- `0x73d7d`: `xmlabbreviation`
- `0x73e72`: `validforupdateapi`
- `0x73ed4`: `validforreadapi`
- `0x73f05`: `validforcreateapi`
- `0x7418b`: `isidentity`
- `0x74344`: `linkedattributeid`
- `0x7446a`: `canbesecuredforcreate`
- `0x7449b`: `canbesecuredforread`
- `0x744cc`: `canbesecuredforupdate`
- `0x748ec`: `isrenameable`
- `0x74a2c`: `isrenameable`
- `0x74a31`: `isrenameable`
- `0x7455f`: `managedpropertyparentcomponenttype`
- `0x7489f`: `cancreateattributes`

## pseudocode

```c

```

## disassembly

```asm
0x73bf0  ldstr    aAttribute// "Attribute"
0x73bf5  ldc.i4.1
0x73bf6  ldc.i4.0
0x73bf7  ldc.i4.1
0x73bf8  ldc.i4.2
0x73bf9  ldloca.s 1
0x73bfb  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x73c01  ldloc.1
0x73c02  ldloca.s 1
0x73c04  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x73c0a  ldloc.1
0x73c0b  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadataDescription::.ctor(string metadataEntityName, bool hasIdsTable, bool areSystemRecordsDeletable, bool isPublishable, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode typeCode, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId)
0x73c10  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadataDescription description)
0x73c15  stloc.0
0x73c16  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::get_MetadataForMetadata()
0x73c1b  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x73c20  ldloc.0
0x73c21  call     class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary metadataEntities, class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity)
0x73c26  pop
0x73c27  ldloc.0
0x73c28  ldstr    aAttributeid// "AttributeId"
0x73c2d  ldstr    aAttributeid_1// "attributeid"
0x73c32  ldstr    aAttributerowid// "AttributeRowId"
0x73c37  ldstr    aAttributerowid_0// "attributerowid"
0x73c3c  ldc.i4.1
0x73c3d  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73c42  call     void Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddPrimaryKeyProperties(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, string pkName, string pkPlatformName, string pkRowName, string pkRowPlatformName, bool isPrimaryIdFieldLogicalIdentityField, class [mscorlib]System.Version introducedVersion)
0x73c47  ldloc.0
0x73c48  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73c4d  call     void Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddSolutionProperties(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class [mscorlib]System.Version introducedVersion)
0x73c52  ldloc.0
0x73c53  ldc.i4.6
0x73c54  ldstr    aAttributetypei_0// "AttributeTypeId"
0x73c59  ldstr    aAttributetypei// "attributetypeid"
0x73c5e  ldc.i4.0
0x73c5f  ldc.i4.1
0x73c60  ldc.i4.0
0x73c61  ldc.i4.0
0x73c62  ldc.i4.0
0x73c63  ldc.i4.1
0x73c64  ldc.i4.0
0x73c65  ldc.i4.0
0x73c66  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73c6b  ldc.i4.0
0x73c6c  ldc.i4.0
0x73c6d  ldc.i4.0
0x73c6e  ldc.i4.1
0x73c6f  ldnull
0x73c70  ldc.i4.0
0x73c71  ldnull
0x73c72  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73c77  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73c7c  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73c81  pop
0x73c82  ldloc.0
0x73c83  ldc.i4.7
0x73c84  ldstr    aName// "Name"
0x73c89  ldstr    aName_0// "name"
0x73c8e  ldc.i4.0
0x73c8f  ldc.i4.1
0x73c90  ldc.i4.0
0x73c91  ldc.i4.0
0x73c92  ldc.i4.0
0x73c93  ldc.i4.1
0x73c94  ldc.i4.0
0x73c95  ldc.i4.2
0x73c96  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73c9b  ldc.i4.0
0x73c9c  ldc.i4.0
0x73c9d  ldc.i4.0
0x73c9e  ldc.i4.1
0x73c9f  ldnull
0x73ca0  ldc.i4.0
0x73ca1  ldnull
0x73ca2  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73ca7  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73cac  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73cb1  pop
0x73cb2  ldloc.0
0x73cb3  ldc.i4.8
0x73cb4  ldstr    aPhysicalname// "PhysicalName"
0x73cb9  ldstr    aPhysicalname_0// "physicalname"
0x73cbe  ldc.i4.0
0x73cbf  ldc.i4.1
0x73cc0  ldc.i4.0
0x73cc1  ldc.i4.0
0x73cc2  ldc.i4.0
0x73cc3  ldc.i4.1
0x73cc4  ldc.i4.0
0x73cc5  ldc.i4.2
0x73cc6  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73ccb  ldc.i4.0
0x73ccc  ldc.i4.0
0x73ccd  ldc.i4.0
0x73cce  ldc.i4.1
0x73ccf  ldnull
0x73cd0  ldc.i4.0
0x73cd1  ldnull
0x73cd2  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73cd7  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73cdc  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73ce1  pop
0x73ce2  ldloc.0
0x73ce3  ldc.i4.s 9
0x73ce5  ldstr    aTablecolumnnam// "TableColumnName"
0x73cea  ldstr    aTablecolumnnam_0// "tablecolumnname"
0x73cef  ldc.i4.0
0x73cf0  ldc.i4.1
0x73cf1  ldc.i4.0
0x73cf2  ldc.i4.0
0x73cf3  ldc.i4.0
0x73cf4  ldc.i4.1
0x73cf5  ldc.i4.0
0x73cf6  ldc.i4.2
0x73cf7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73cfc  ldc.i4.0
0x73cfd  ldc.i4.0
0x73cfe  ldc.i4.0
0x73cff  ldc.i4.1
0x73d00  ldnull
0x73d01  ldc.i4.0
0x73d02  ldnull
0x73d03  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73d08  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73d0d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73d12  pop
0x73d13  ldloc.0
0x73d14  ldc.i4.s 0xA
0x73d16  ldstr    aLength// "Length"
0x73d1b  ldstr    aLength_0// "length"
0x73d20  ldc.i4.1
0x73d21  ldc.i4.1
0x73d22  ldc.i4.0
0x73d23  ldc.i4.0
0x73d24  ldc.i4.0
0x73d25  ldc.i4.1
0x73d26  ldc.i4.0
0x73d27  ldc.i4.1
0x73d28  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73d2d  ldc.i4.0
0x73d2e  ldc.i4.0
0x73d2f  ldc.i4.0
0x73d30  ldc.i4.1
0x73d31  ldnull
0x73d32  ldc.i4.0
0x73d33  ldnull
0x73d34  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73d39  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73d3e  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73d43  pop
0x73d44  ldloc.0
0x73d45  ldc.i4.s 0xB
0x73d47  ldstr    aIsnullable// "IsNullable"
0x73d4c  ldstr    aIsnullable_0// "isnullable"
0x73d51  ldc.i4.1
0x73d52  ldc.i4.1
0x73d53  ldc.i4.0
0x73d54  ldc.i4.0
0x73d55  ldc.i4.0
0x73d56  ldc.i4.1
0x73d57  ldc.i4.0
0x73d58  ldc.i4.3
0x73d59  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73d5e  ldc.i4.0
0x73d5f  ldc.i4.0
0x73d60  ldc.i4.0
0x73d61  ldc.i4.1
0x73d62  ldnull
0x73d63  ldc.i4.0
0x73d64  ldnull
0x73d65  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73d6a  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73d6f  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73d74  pop
0x73d75  ldloc.0
0x73d76  ldc.i4.s 0xC
0x73d78  ldstr    aXmlabbreviatio_0// "XmlAbbreviation"
0x73d7d  ldstr    aXmlabbreviatio_1// "xmlabbreviation"
0x73d82  ldc.i4.1
0x73d83  ldc.i4.1
0x73d84  ldc.i4.0
0x73d85  ldc.i4.0
0x73d86  ldc.i4.0
0x73d87  ldc.i4.1
0x73d88  ldc.i4.0
0x73d89  ldc.i4.2
0x73d8a  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73d8f  ldc.i4.0
0x73d90  ldc.i4.0
0x73d91  ldc.i4.0
0x73d92  ldc.i4.1
0x73d93  ldnull
0x73d94  ldc.i4.0
0x73d95  ldnull
0x73d96  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73d9b  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73da0  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73da5  pop
0x73da6  ldloc.0
0x73da7  ldc.i4.s 0xD
0x73da9  ldstr    aEntityid// "EntityId"
0x73dae  ldstr    aEntityid_1// "entityid"
0x73db3  ldc.i4.0
0x73db4  ldc.i4.0
0x73db5  ldc.i4.0
0x73db6  ldc.i4.0
0x73db7  ldc.i4.0
0x73db8  ldc.i4.0
0x73db9  ldc.i4.0
0x73dba  ldc.i4.0
0x73dbb  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73dc0  ldc.i4.0
0x73dc1  ldc.i4.0
0x73dc2  ldc.i4.0
0x73dc3  ldc.i4.1
0x73dc4  ldnull
0x73dc5  ldc.i4.0
0x73dc6  ldnull
0x73dc7  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73dcc  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73dd1  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73dd6  pop
0x73dd7  ldloc.0
0x73dd8  ldc.i4.s 0xE
0x73dda  ldstr    aDefaultvalue// "DefaultValue"
0x73ddf  ldstr    aDefaultvalue_0// "defaultvalue"
0x73de4  ldc.i4.1
0x73de5  ldc.i4.1
0x73de6  ldc.i4.0
0x73de7  ldc.i4.0
0x73de8  ldc.i4.0
0x73de9  ldc.i4.1
0x73dea  ldc.i4.0
0x73deb  ldc.i4.2
0x73dec  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73df1  ldc.i4.0
0x73df2  ldc.i4.0
0x73df3  ldc.i4.0
0x73df4  ldc.i4.1
0x73df5  ldnull
0x73df6  ldc.i4.0
0x73df7  ldnull
0x73df8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73dfd  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73e02  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73e07  pop
0x73e08  ldloc.0
0x73e09  ldc.i4.s 0xF
0x73e0b  ldstr    aUpgradedefault// "UpgradeDefaultValue"
0x73e10  ldstr    aUpgradedefault_0// "upgradedefaultvalue"
0x73e15  ldc.i4.0
0x73e16  ldc.i4.1
0x73e17  ldc.i4.0
0x73e18  ldc.i4.0
0x73e19  ldc.i4.0
0x73e1a  ldc.i4.1
0x73e1b  ldc.i4.0
0x73e1c  ldc.i4.2
0x73e1d  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73e22  ldc.i4.0
0x73e23  ldc.i4.0
0x73e24  ldc.i4.0
0x73e25  ldc.i4.1
0x73e26  ldnull
0x73e27  ldc.i4.0
0x73e28  ldnull
0x73e29  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73e2e  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73e33  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73e38  pop
0x73e39  ldloc.0
0x73e3a  ldc.i4.s 0x10
0x73e3c  ldstr    aColumnnumber// "ColumnNumber"
0x73e41  ldstr    aColumnnumber_0// "columnnumber"
0x73e46  ldc.i4.0
0x73e47  ldc.i4.1
0x73e48  ldc.i4.0
0x73e49  ldc.i4.0
0x73e4a  ldc.i4.0
0x73e4b  ldc.i4.0
0x73e4c  ldc.i4.0
0x73e4d  ldc.i4.1
0x73e4e  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x73e53  ldc.i4.0
0x73e54  ldc.i4.0
0x73e55  ldc.i4.0
0x73e56  ldc.i4.1
0x73e57  ldnull
0x73e58  ldc.i4.0
0x73e59  ldnull
0x73e5a  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x73e5f  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x73e64  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x73e69  pop
0x73e6a  ldloc.0
0x73e6b  ldc.i4.s 0x11
0x73e6d  ldstr    aValidforupdate_0// "ValidForUpdateAPI"
0x73e72  ldstr    aValidforupdate_1// "validforupdateapi"
0x73e77  ldc.i4.1
0x73e78  ldc.i4.1
  ... truncated ...
```
