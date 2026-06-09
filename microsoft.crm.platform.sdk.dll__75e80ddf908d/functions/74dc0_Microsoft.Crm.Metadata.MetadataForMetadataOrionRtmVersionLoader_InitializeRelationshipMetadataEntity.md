# Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeRelationshipMetadataEntity

- ea: `0x74dc0`
- end: `0x75192`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeRelationshipMetadataEntity`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x72170`

## callees

- `0x70970`
- `0x70f50`
- `0x712f0`
- `0x71790`
- `0x71970`
- `0x71fa0`
- `0x71fb0`
- `0x72000`
- `0x72050`
- `0x72120`

## string_xrefs

- `0x74f79`: `CascadeDelete`
- `0x7509f`: `CascadeLinkMask`
- `0x74f7e`: `cascadedelete`
- `0x750a4`: `cascadelinkmask`

## pseudocode

```c

```

## disassembly

```asm
0x74dc0  ldstr    aRelationship_0// "Relationship"
0x74dc5  ldc.i4.1
0x74dc6  ldc.i4.0
0x74dc7  ldc.i4.0
0x74dc8  ldc.i4.3
0x74dc9  ldloca.s 1
0x74dcb  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x74dd1  ldloc.1
0x74dd2  ldloca.s 1
0x74dd4  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x74dda  ldloc.1
0x74ddb  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadataDescription::.ctor(string metadataEntityName, bool hasIdsTable, bool areSystemRecordsDeletable, bool isPublishable, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode typeCode, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId)
0x74de0  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadataDescription description)
0x74de5  stloc.0
0x74de6  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::get_MetadataForMetadata()
0x74deb  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x74df0  ldloc.0
0x74df1  call     class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary metadataEntities, class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity)
0x74df6  pop
0x74df7  ldloc.0
0x74df8  ldstr    aRelationshipid_0// "RelationshipId"
0x74dfd  ldstr    aRelationshipid// "relationshipid"
0x74e02  ldstr    aRelationshipro_1// "RelationshipRowId"
0x74e07  ldstr    aRelationshipro_2// "relationshiprowid"
0x74e0c  ldc.i4.1
0x74e0d  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74e12  call     void Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddPrimaryKeyProperties(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, string pkName, string pkPlatformName, string pkRowName, string pkRowPlatformName, bool isPrimaryIdFieldLogicalIdentityField, class [mscorlib]System.Version introducedVersion)
0x74e17  ldloc.0
0x74e18  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74e1d  call     void Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddSolutionProperties(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class [mscorlib]System.Version introducedVersion)
0x74e22  ldloc.0
0x74e23  ldc.i4.6
0x74e24  ldstr    aName// "Name"
0x74e29  ldstr    aName_0// "name"
0x74e2e  ldc.i4.0
0x74e2f  ldc.i4.1
0x74e30  ldc.i4.0
0x74e31  ldc.i4.0
0x74e32  ldc.i4.0
0x74e33  ldc.i4.0
0x74e34  ldc.i4.0
0x74e35  ldc.i4.2
0x74e36  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74e3b  ldc.i4.0
0x74e3c  ldc.i4.0
0x74e3d  ldc.i4.0
0x74e3e  ldc.i4.1
0x74e3f  ldnull
0x74e40  ldc.i4.0
0x74e41  ldnull
0x74e42  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74e47  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74e4c  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74e51  pop
0x74e52  ldloc.0
0x74e53  ldc.i4.7
0x74e54  ldstr    aReferencingent// "ReferencingEntityId"
0x74e59  ldstr    aReferencingent_1// "referencingentityid"
0x74e5e  ldc.i4.0
0x74e5f  ldc.i4.0
0x74e60  ldc.i4.0
0x74e61  ldc.i4.0
0x74e62  ldc.i4.0
0x74e63  ldc.i4.0
0x74e64  ldc.i4.0
0x74e65  ldc.i4.0
0x74e66  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74e6b  ldc.i4.0
0x74e6c  ldc.i4.0
0x74e6d  ldc.i4.0
0x74e6e  ldc.i4.1
0x74e6f  ldnull
0x74e70  ldc.i4.0
0x74e71  ldnull
0x74e72  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74e77  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74e7c  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74e81  pop
0x74e82  ldloc.0
0x74e83  ldc.i4.8
0x74e84  ldstr    aReferencingatt// "ReferencingAttributeId"
0x74e89  ldstr    aReferencingatt_1// "referencingattributeid"
0x74e8e  ldc.i4.0
0x74e8f  ldc.i4.0
0x74e90  ldc.i4.0
0x74e91  ldc.i4.0
0x74e92  ldc.i4.0
0x74e93  ldc.i4.0
0x74e94  ldc.i4.0
0x74e95  ldc.i4.0
0x74e96  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74e9b  ldc.i4.0
0x74e9c  ldc.i4.0
0x74e9d  ldc.i4.0
0x74e9e  ldc.i4.1
0x74e9f  ldnull
0x74ea0  ldc.i4.0
0x74ea1  ldnull
0x74ea2  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74ea7  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74eac  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74eb1  pop
0x74eb2  ldloc.0
0x74eb3  ldc.i4.s 9
0x74eb5  ldstr    aReferencedenti_0// "ReferencedEntityId"
0x74eba  ldstr    aReferencedenti_3// "referencedentityid"
0x74ebf  ldc.i4.0
0x74ec0  ldc.i4.0
0x74ec1  ldc.i4.0
0x74ec2  ldc.i4.0
0x74ec3  ldc.i4.0
0x74ec4  ldc.i4.1
0x74ec5  ldc.i4.0
0x74ec6  ldc.i4.0
0x74ec7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74ecc  ldc.i4.0
0x74ecd  ldc.i4.0
0x74ece  ldc.i4.0
0x74ecf  ldc.i4.1
0x74ed0  ldnull
0x74ed1  ldc.i4.0
0x74ed2  ldnull
0x74ed3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74ed8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74edd  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74ee2  pop
0x74ee3  ldloc.0
0x74ee4  ldc.i4.s 0xA
0x74ee6  ldstr    aReferencedattr// "ReferencedAttributeId"
0x74eeb  ldstr    aReferencedattr_1// "referencedattributeid"
0x74ef0  ldc.i4.0
0x74ef1  ldc.i4.0
0x74ef2  ldc.i4.0
0x74ef3  ldc.i4.0
0x74ef4  ldc.i4.0
0x74ef5  ldc.i4.1
0x74ef6  ldc.i4.0
0x74ef7  ldc.i4.0
0x74ef8  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74efd  ldc.i4.0
0x74efe  ldc.i4.0
0x74eff  ldc.i4.0
0x74f00  ldc.i4.1
0x74f01  ldnull
0x74f02  ldc.i4.0
0x74f03  ldnull
0x74f04  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74f09  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74f0e  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74f13  pop
0x74f14  ldloc.0
0x74f15  ldc.i4.s 0xB
0x74f17  ldstr    aRelationshipty// "RelationshipType"
0x74f1c  ldstr    aRelationshipty_0// "relationshiptype"
0x74f21  ldc.i4.0
0x74f22  ldc.i4.1
0x74f23  ldc.i4.0
0x74f24  ldc.i4.0
0x74f25  ldc.i4.0
0x74f26  ldc.i4.1
0x74f27  ldc.i4.0
0x74f28  ldc.i4.1
0x74f29  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74f2e  ldc.i4.0
0x74f2f  ldc.i4.0
0x74f30  ldc.i4.0
0x74f31  ldc.i4.1
0x74f32  ldnull
0x74f33  ldc.i4.0
0x74f34  ldnull
0x74f35  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74f3a  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74f3f  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74f44  pop
0x74f45  ldloc.0
0x74f46  ldc.i4.s 0xC
0x74f48  ldstr    aIslogical// "IsLogical"
0x74f4d  ldstr    aIslogical_0// "islogical"
0x74f52  ldc.i4.0
0x74f53  ldc.i4.0
0x74f54  ldc.i4.0
0x74f55  ldc.i4.0
0x74f56  ldc.i4.0
0x74f57  ldc.i4.1
0x74f58  ldc.i4.0
0x74f59  ldc.i4.3
0x74f5a  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74f5f  ldc.i4.0
0x74f60  ldc.i4.0
0x74f61  ldc.i4.0
0x74f62  ldc.i4.1
0x74f63  ldnull
0x74f64  ldc.i4.0
0x74f65  ldnull
0x74f66  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74f6b  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74f70  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74f75  pop
0x74f76  ldloc.0
0x74f77  ldc.i4.s 0xD
0x74f79  ldstr    aCascadedelete// "CascadeDelete"
0x74f7e  ldstr    aCascadedelete_0// "cascadedelete"
0x74f83  ldc.i4.1
0x74f84  ldc.i4.1
0x74f85  ldc.i4.0
0x74f86  ldc.i4.0
0x74f87  ldc.i4.0
0x74f88  ldc.i4.1
0x74f89  ldc.i4.0
0x74f8a  ldc.i4.5
0x74f8b  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74f90  ldc.i4.0
0x74f91  ldc.i4.0
0x74f92  ldc.i4.0
0x74f93  ldc.i4.1
0x74f94  ldnull
0x74f95  ldc.i4.0
0x74f96  ldnull
0x74f97  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74f9c  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74fa1  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74fa6  pop
0x74fa7  ldloc.0
0x74fa8  ldc.i4.s 0xE
0x74faa  ldstr    aCascadeassign// "CascadeAssign"
0x74faf  ldstr    aCascadeassign_0// "cascadeassign"
0x74fb4  ldc.i4.1
0x74fb5  ldc.i4.1
0x74fb6  ldc.i4.0
0x74fb7  ldc.i4.0
0x74fb8  ldc.i4.0
0x74fb9  ldc.i4.1
0x74fba  ldc.i4.0
0x74fbb  ldc.i4.5
0x74fbc  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74fc1  ldc.i4.0
0x74fc2  ldc.i4.0
0x74fc3  ldc.i4.0
0x74fc4  ldc.i4.1
0x74fc5  ldnull
0x74fc6  ldc.i4.0
0x74fc7  ldnull
0x74fc8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74fcd  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x74fd2  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x74fd7  pop
0x74fd8  ldloc.0
0x74fd9  ldc.i4.s 0xF
0x74fdb  ldstr    aCascadeshare// "CascadeShare"
0x74fe0  ldstr    aCascadeshare_0// "cascadeshare"
0x74fe5  ldc.i4.1
0x74fe6  ldc.i4.1
0x74fe7  ldc.i4.0
0x74fe8  ldc.i4.0
0x74fe9  ldc.i4.0
0x74fea  ldc.i4.1
0x74feb  ldc.i4.0
0x74fec  ldc.i4.5
0x74fed  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x74ff2  ldc.i4.0
0x74ff3  ldc.i4.0
0x74ff4  ldc.i4.0
0x74ff5  ldc.i4.1
0x74ff6  ldnull
0x74ff7  ldc.i4.0
0x74ff8  ldnull
0x74ff9  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x74ffe  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x75003  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75008  pop
0x75009  ldloc.0
0x7500a  ldc.i4.s 0x10
0x7500c  ldstr    aCascadeunshare_1// "CascadeUnShare"
0x75011  ldstr    aCascadeunshare_0// "cascadeunshare"
0x75016  ldc.i4.1
0x75017  ldc.i4.1
0x75018  ldc.i4.0
0x75019  ldc.i4.0
0x7501a  ldc.i4.0
0x7501b  ldc.i4.1
0x7501c  ldc.i4.0
0x7501d  ldc.i4.5
0x7501e  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x75023  ldc.i4.0
0x75024  ldc.i4.0
0x75025  ldc.i4.0
0x75026  ldc.i4.1
0x75027  ldnull
0x75028  ldc.i4.0
0x75029  ldnull
0x7502a  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7502f  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x75034  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75039  pop
0x7503a  ldloc.0
0x7503b  ldc.i4.s 0x11
0x7503d  ldstr    aCascademerge// "CascadeMerge"
0x75042  ldstr    aCascademerge_0// "cascademerge"
0x75047  ldc.i4.1
0x75048  ldc.i4.1
  ... truncated ...
```
