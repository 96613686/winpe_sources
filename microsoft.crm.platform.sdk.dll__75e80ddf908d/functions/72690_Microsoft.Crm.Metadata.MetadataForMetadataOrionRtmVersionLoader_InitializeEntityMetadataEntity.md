# Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeEntityMetadataEntity

- ea: `0x72690`
- end: `0x73bee`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeEntityMetadataEntity`
- size: `5470`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x72170`

## callees

- `0x70970`
- `0x70f50`
- `0x712f0`
- `0x71790`
- `0x71970`
- `0x71c80`
- `0x71ce0`
- `0x71cf0`
- `0x71fa0`
- `0x71fb0`
- `0x71fc0`
- `0x72000`
- `0x72050`
- `0x72120`

## string_xrefs

- `0x73458`: `IsRenameable`
- `0x728dc`: `IsSecurityIntersect`
- `0x72c4e`: `MobileAccessLevelMask`
- `0x738f0`: `IsReadOnlyInMobileClient`
- `0x7382c`: `IsAIRUpdated`
- `0x72efc`: `ExtensionTableName`
- `0x73117`: `ServiceClassName`
- `0x73179`: `ServiceAssembly`
- `0x73921`: `CanModifyMobileClientReadOnly`
- `0x733c5`: `IsReadingPaneEnabled`
- `0x737fb`: `IsQuickCreateEnabled`
- `0x73611`: `CanCreateAttributes`
- `0x736d5`: `CanCreateForms`
- `0x73706`: `CanCreateCharts`
- `0x73737`: `CanCreateViews`
- `0x73301`: `ParentComponentType`
- `0x7345d`: `isrenameable`
- `0x7399c`: `isrenameable`
- `0x739a1`: `isrenameable`
- `0x7388e`: `AutoCreateAccessTeams`
- `0x73952`: `HasIdsTable`
- `0x72f01`: `extensiontablename`
- `0x728e1`: `issecurityintersect`
- `0x72c53`: `mobileaccesslevelmask`
- `0x738f5`: `isreadonlyinmobileclient`
- `0x73831`: `isairupdated`
- `0x7311c`: `serviceclassname`
- `0x7317e`: `serviceassembly`
- `0x73306`: `parentcomponenttype`
- `0x733ca`: `isreadingpaneenabled`
- `0x73957`: `hasidstable`
- `0x73893`: `autocreateaccessteams`
- `0x73800`: `isquickcreateenabled`
- `0x73926`: `canmodifymobileclientreadonly`
- `0x73a62`: `canmodifymobileclientreadonly`
- `0x73a67`: `canmodifymobileclientreadonly`
- `0x73616`: `cancreateattributes`
- `0x73b07`: `cancreateattributes`
- `0x73b0c`: `cancreateattributes`
- `0x736da`: `cancreateforms`
- `0x73b8b`: `cancreateforms`
- `0x73b90`: `cancreateforms`
- `0x7370b`: `cancreatecharts`
- `0x73bac`: `cancreatecharts`
- `0x73bb1`: `cancreatecharts`
- `0x7373c`: `cancreateviews`
- `0x73bcd`: `cancreateviews`
- `0x73bd2`: `cancreateviews`

## pseudocode

```c

```

## disassembly

```asm
0x72690  ldstr    aEntity_0// "Entity"
0x72695  ldc.i4.1
0x72696  ldc.i4.0
0x72697  ldc.i4.0
0x72698  ldc.i4.1
0x72699  ldloca.s 1
0x7269b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x726a1  ldloc.1
0x726a2  ldloca.s 1
0x726a4  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x726aa  ldloc.1
0x726ab  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadataDescription::.ctor(string metadataEntityName, bool hasIdsTable, bool areSystemRecordsDeletable, bool isPublishable, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode typeCode, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId)
0x726b0  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadataDescription description)
0x726b5  stloc.0
0x726b6  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::get_MetadataForMetadata()
0x726bb  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x726c0  ldloc.0
0x726c1  call     class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary metadataEntities, class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity)
0x726c6  pop
0x726c7  ldloc.0
0x726c8  ldstr    aEntityid// "EntityId"
0x726cd  ldstr    aEntityid_1// "entityid"
0x726d2  ldstr    aEntityrowid// "EntityRowId"
0x726d7  ldstr    aEntityrowid_0// "entityrowid"
0x726dc  ldc.i4.1
0x726dd  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x726e2  call     void Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddPrimaryKeyProperties(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, string pkName, string pkPlatformName, string pkRowName, string pkRowPlatformName, bool isPrimaryIdFieldLogicalIdentityField, class [mscorlib]System.Version introducedVersion)
0x726e7  ldloc.0
0x726e8  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x726ed  call     void Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddSolutionProperties(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class [mscorlib]System.Version introducedVersion)
0x726f2  ldloc.0
0x726f3  ldc.i4.6
0x726f4  ldstr    aName// "Name"
0x726f9  ldstr    aName_0// "name"
0x726fe  ldc.i4.0
0x726ff  ldc.i4.1
0x72700  ldc.i4.0
0x72701  ldc.i4.0
0x72702  ldc.i4.0
0x72703  ldc.i4.0
0x72704  ldc.i4.0
0x72705  ldc.i4.2
0x72706  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7270b  ldc.i4.0
0x7270c  ldc.i4.0
0x7270d  ldc.i4.0
0x7270e  ldc.i4.1
0x7270f  ldnull
0x72710  ldc.i4.0
0x72711  ldnull
0x72712  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x72717  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7271c  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72721  pop
0x72722  ldloc.0
0x72723  ldc.i4.7
0x72724  ldstr    aObjecttypecode// "ObjectTypeCode"
0x72729  ldstr    aObjecttypecode_0// "objecttypecode"
0x7272e  ldc.i4.0
0x7272f  ldc.i4.1
0x72730  ldc.i4.0
0x72731  ldc.i4.0
0x72732  ldc.i4.0
0x72733  ldc.i4.0
0x72734  ldc.i4.0
0x72735  ldc.i4.1
0x72736  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7273b  ldc.i4.0
0x7273c  ldc.i4.0
0x7273d  ldc.i4.0
0x7273e  ldc.i4.1
0x7273f  ldnull
0x72740  ldc.i4.0
0x72741  ldnull
0x72742  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x72747  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7274c  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72751  pop
0x72752  ldloc.0
0x72753  ldc.i4.8
0x72754  ldstr    aPhysicalname// "PhysicalName"
0x72759  ldstr    aPhysicalname_0// "physicalname"
0x7275e  ldc.i4.0
0x7275f  ldc.i4.1
0x72760  ldc.i4.0
0x72761  ldc.i4.0
0x72762  ldc.i4.0
0x72763  ldc.i4.0
0x72764  ldc.i4.0
0x72765  ldc.i4.2
0x72766  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7276b  ldc.i4.0
0x7276c  ldc.i4.0
0x7276d  ldc.i4.0
0x7276e  ldc.i4.1
0x7276f  ldnull
0x72770  ldc.i4.0
0x72771  ldnull
0x72772  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x72777  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7277c  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72781  pop
0x72782  ldloc.0
0x72783  ldc.i4.s 9
0x72785  ldstr    aLogicalname// "LogicalName"
0x7278a  ldstr    aLogicalname_0// "logicalname"
0x7278f  ldc.i4.0
0x72790  ldc.i4.1
0x72791  ldc.i4.0
0x72792  ldc.i4.0
0x72793  ldc.i4.0
0x72794  ldc.i4.0
0x72795  ldc.i4.0
0x72796  ldc.i4.2
0x72797  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7279c  ldc.i4.0
0x7279d  ldc.i4.0
0x7279e  ldc.i4.0
0x7279f  ldc.i4.1
0x727a0  ldnull
0x727a1  ldc.i4.0
0x727a2  ldnull
0x727a3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x727a8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x727ad  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x727b2  pop
0x727b3  ldloc.0
0x727b4  ldc.i4.s 0xA
0x727b6  ldstr    aCollectionname// "CollectionName"
0x727bb  ldstr    aCollectionname_0// "collectionname"
0x727c0  ldc.i4.0
0x727c1  ldc.i4.1
0x727c2  ldc.i4.0
0x727c3  ldc.i4.0
0x727c4  ldc.i4.0
0x727c5  ldc.i4.0
0x727c6  ldc.i4.0
0x727c7  ldc.i4.2
0x727c8  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x727cd  ldc.i4.0
0x727ce  ldc.i4.0
0x727cf  ldc.i4.0
0x727d0  ldc.i4.1
0x727d1  ldnull
0x727d2  ldc.i4.0
0x727d3  ldnull
0x727d4  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x727d9  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x727de  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x727e3  pop
0x727e4  ldloc.0
0x727e5  ldc.i4.s 0xB
0x727e7  ldstr    aOriginallocali// "OriginalLocalizedName"
0x727ec  ldstr    aOriginallocali_1// "originallocalizedname"
0x727f1  ldc.i4.0
0x727f2  ldc.i4.1
0x727f3  ldc.i4.0
0x727f4  ldc.i4.0
0x727f5  ldc.i4.0
0x727f6  ldc.i4.0
0x727f7  ldc.i4.0
0x727f8  ldc.i4.2
0x727f9  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x727fe  ldc.i4.0
0x727ff  ldc.i4.0
0x72800  ldc.i4.0
0x72801  ldc.i4.1
0x72802  ldnull
0x72803  ldc.i4.0
0x72804  ldnull
0x72805  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7280a  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7280f  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72814  pop
0x72815  ldloc.0
0x72816  ldc.i4.s 0xC
0x72818  ldstr    aOriginallocali_0// "OriginalLocalizedCollectionName"
0x7281d  ldstr    aOriginallocali_2// "originallocalizedcollectionname"
0x72822  ldc.i4.0
0x72823  ldc.i4.1
0x72824  ldc.i4.0
0x72825  ldc.i4.0
0x72826  ldc.i4.0
0x72827  ldc.i4.0
0x72828  ldc.i4.0
0x72829  ldc.i4.2
0x7282a  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7282f  ldc.i4.0
0x72830  ldc.i4.0
0x72831  ldc.i4.0
0x72832  ldc.i4.1
0x72833  ldnull
0x72834  ldc.i4.0
0x72835  ldnull
0x72836  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7283b  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x72840  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72845  pop
0x72846  ldloc.0
0x72847  ldc.i4.s 0xD
0x72849  ldstr    aBasetablename// "BaseTableName"
0x7284e  ldstr    aBasetablename_0// "basetablename"
0x72853  ldc.i4.0
0x72854  ldc.i4.1
0x72855  ldc.i4.0
0x72856  ldc.i4.0
0x72857  ldc.i4.0
0x72858  ldc.i4.1
0x72859  ldc.i4.0
0x7285a  ldc.i4.2
0x7285b  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x72860  ldc.i4.0
0x72861  ldc.i4.0
0x72862  ldc.i4.0
0x72863  ldc.i4.1
0x72864  ldnull
0x72865  ldc.i4.0
0x72866  ldnull
0x72867  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7286c  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x72871  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72876  pop
0x72877  ldloc.0
0x72878  ldc.i4.s 0xE
0x7287a  ldstr    aLogicalcollect// "LogicalCollectionName"
0x7287f  ldstr    aLogicalcollect_0// "logicalcollectionname"
0x72884  ldc.i4.0
0x72885  ldc.i4.1
0x72886  ldc.i4.0
0x72887  ldc.i4.0
0x72888  ldc.i4.0
0x72889  ldc.i4.0
0x7288a  ldc.i4.0
0x7288b  ldc.i4.2
0x7288c  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x72891  ldc.i4.0
0x72892  ldc.i4.0
0x72893  ldc.i4.0
0x72894  ldc.i4.1
0x72895  ldnull
0x72896  ldc.i4.0
0x72897  ldnull
0x72898  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x7289d  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x728a2  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x728a7  pop
0x728a8  ldloc.0
0x728a9  ldc.i4.s 0xF
0x728ab  ldstr    aIsintersect// "IsIntersect"
0x728b0  ldstr    aIsintersect_0// "isintersect"
0x728b5  ldc.i4.0
0x728b6  ldc.i4.0
0x728b7  ldc.i4.0
0x728b8  ldc.i4.0
0x728b9  ldc.i4.0
0x728ba  ldc.i4.1
0x728bb  ldc.i4.0
0x728bc  ldc.i4.3
0x728bd  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x728c2  ldc.i4.0
0x728c3  ldc.i4.0
0x728c4  ldc.i4.0
0x728c5  ldc.i4.1
0x728c6  ldnull
0x728c7  ldc.i4.0
0x728c8  ldnull
0x728c9  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x728ce  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x728d3  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x728d8  pop
0x728d9  ldloc.0
0x728da  ldc.i4.s 0x10
0x728dc  ldstr    aIssecurityinte// "IsSecurityIntersect"
0x728e1  ldstr    aIssecurityinte_0// "issecurityintersect"
0x728e6  ldc.i4.0
0x728e7  ldc.i4.0
0x728e8  ldc.i4.0
0x728e9  ldc.i4.0
0x728ea  ldc.i4.0
0x728eb  ldc.i4.1
0x728ec  ldc.i4.0
0x728ed  ldc.i4.3
0x728ee  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x728f3  ldc.i4.0
0x728f4  ldc.i4.0
0x728f5  ldc.i4.0
0x728f6  ldc.i4.1
0x728f7  ldnull
0x728f8  ldc.i4.0
0x728f9  ldnull
0x728fa  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x728ff  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x72904  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x72909  pop
0x7290a  ldloc.0
0x7290b  ldc.i4.s 0x11
0x7290d  ldstr    aIslookuptable// "IsLookupTable"
0x72912  ldstr    aIslookuptable_0// "islookuptable"
0x72917  ldc.i4.1
0x72918  ldc.i4.0
  ... truncated ...
```
