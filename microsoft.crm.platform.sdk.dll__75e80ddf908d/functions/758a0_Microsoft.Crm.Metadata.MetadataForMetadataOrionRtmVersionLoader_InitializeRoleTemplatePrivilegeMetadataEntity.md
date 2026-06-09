# Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeRoleTemplatePrivilegeMetadataEntity

- ea: `0x758a0`
- end: `0x75a34`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::InitializeRoleTemplatePrivilegeMetadataEntity`
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

- `0x758a0`: `RoleTemplatePrivilege`
- `0x75945`: `PrivilegeId`
- `0x7594a`: `privilegeid`
- `0x758e5`: `RoleTemplatePrivilegeId`
- `0x75915`: `RoleTemplateId`
- `0x758ea`: `roletemplateprivilegeid`
- `0x7591a`: `roletemplateid`
- `0x758a5`: `RoleTemplatePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x758a0  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x758a5  ldstr    aRoletemplatepr_9// "RoleTemplatePrivileges"
0x758aa  ldnull
0x758ab  ldnull
0x758ac  ldnull
0x758ad  ldnull
0x758ae  ldnull
0x758af  ldc.i4.0
0x758b0  ldc.i4.0
0x758b1  ldc.i4.s 0xB
0x758b3  ldloca.s 1
0x758b5  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x758bb  ldloc.1
0x758bc  ldloca.s 1
0x758be  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x758c4  ldloc.1
0x758c5  ldnull
0x758c6  ldnull
0x758c7  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadataDescription::.ctor(string metadataEntityName, string tableName, string idsTableName, string logicalViewName, string standardViewName, string logicalAsIfPublishedViewName, string standardAsIfPublishedViewName, bool areSystemRecordsDeletable, bool isPublishable, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode typeCode, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId, string externalName, string externalCollectionName)
0x758cc  newobj   instance void Microsoft.Crm.Metadata.MetadataEntityMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataEntityMetadataDescription description)
0x758d1  stloc.0
0x758d2  call     class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::get_MetadataForMetadata()
0x758d7  callvirt instance class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x758dc  ldloc.0
0x758dd  call     class Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary metadataEntities, class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity)
0x758e2  pop
0x758e3  ldloc.0
0x758e4  ldc.i4.0
0x758e5  ldstr    aRoletemplatepr_1// "RoleTemplatePrivilegeId"
0x758ea  ldstr    aRoletemplatepr_4// "roletemplateprivilegeid"
0x758ef  ldc.i4.0
0x758f0  ldc.i4.0
0x758f1  ldc.i4.1
0x758f2  ldc.i4.1
0x758f3  ldc.i4.0
0x758f4  ldc.i4.0
0x758f5  ldc.i4.0
0x758f6  ldc.i4.0
0x758f7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x758fc  ldc.i4.0
0x758fd  ldc.i4.0
0x758fe  ldc.i4.0
0x758ff  ldc.i4.1
0x75900  ldnull
0x75901  ldc.i4.0
0x75902  ldnull
0x75903  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75908  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7590d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75912  pop
0x75913  ldloc.0
0x75914  ldc.i4.1
0x75915  ldstr    aRoletemplateid_0// "RoleTemplateId"
0x7591a  ldstr    aRoletemplateid_1// "roletemplateid"
0x7591f  ldc.i4.0
0x75920  ldc.i4.0
0x75921  ldc.i4.0
0x75922  ldc.i4.0
0x75923  ldc.i4.1
0x75924  ldc.i4.0
0x75925  ldc.i4.0
0x75926  ldc.i4.0
0x75927  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7592c  ldc.i4.0
0x7592d  ldc.i4.0
0x7592e  ldc.i4.0
0x7592f  ldc.i4.1
0x75930  ldnull
0x75931  ldc.i4.0
0x75932  ldnull
0x75933  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75938  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7593d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75942  pop
0x75943  ldloc.0
0x75944  ldc.i4.2
0x75945  ldstr    aPrivilegeid_0// "PrivilegeId"
0x7594a  ldstr    aPrivilegeid_1// "privilegeid"
0x7594f  ldc.i4.0
0x75950  ldc.i4.0
0x75951  ldc.i4.0
0x75952  ldc.i4.0
0x75953  ldc.i4.1
0x75954  ldc.i4.0
0x75955  ldc.i4.0
0x75956  ldc.i4.0
0x75957  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7595c  ldc.i4.0
0x7595d  ldc.i4.0
0x7595e  ldc.i4.0
0x7595f  ldc.i4.1
0x75960  ldnull
0x75961  ldc.i4.0
0x75962  ldnull
0x75963  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75968  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7596d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75972  pop
0x75973  ldloc.0
0x75974  ldc.i4.3
0x75975  ldstr    aIsbasic// "IsBasic"
0x7597a  ldstr    aIsbasic_0// "isbasic"
0x7597f  ldc.i4.1
0x75980  ldc.i4.0
0x75981  ldc.i4.0
0x75982  ldc.i4.0
0x75983  ldc.i4.0
0x75984  ldc.i4.0
0x75985  ldc.i4.0
0x75986  ldc.i4.3
0x75987  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x7598c  ldc.i4.0
0x7598d  ldc.i4.0
0x7598e  ldc.i4.0
0x7598f  ldc.i4.1
0x75990  ldnull
0x75991  ldc.i4.0
0x75992  ldnull
0x75993  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75998  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x7599d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x759a2  pop
0x759a3  ldloc.0
0x759a4  ldc.i4.4
0x759a5  ldstr    aIslocal// "IsLocal"
0x759aa  ldstr    aIslocal_0// "islocal"
0x759af  ldc.i4.1
0x759b0  ldc.i4.0
0x759b1  ldc.i4.0
0x759b2  ldc.i4.0
0x759b3  ldc.i4.0
0x759b4  ldc.i4.0
0x759b5  ldc.i4.0
0x759b6  ldc.i4.3
0x759b7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x759bc  ldc.i4.0
0x759bd  ldc.i4.0
0x759be  ldc.i4.0
0x759bf  ldc.i4.1
0x759c0  ldnull
0x759c1  ldc.i4.0
0x759c2  ldnull
0x759c3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x759c8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x759cd  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x759d2  pop
0x759d3  ldloc.0
0x759d4  ldc.i4.5
0x759d5  ldstr    aIsdeep// "IsDeep"
0x759da  ldstr    aIsdeep_0// "isdeep"
0x759df  ldc.i4.1
0x759e0  ldc.i4.0
0x759e1  ldc.i4.0
0x759e2  ldc.i4.0
0x759e3  ldc.i4.0
0x759e4  ldc.i4.0
0x759e5  ldc.i4.0
0x759e6  ldc.i4.3
0x759e7  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x759ec  ldc.i4.0
0x759ed  ldc.i4.0
0x759ee  ldc.i4.0
0x759ef  ldc.i4.1
0x759f0  ldnull
0x759f1  ldc.i4.0
0x759f2  ldnull
0x759f3  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x759f8  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x759fd  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75a02  pop
0x75a03  ldloc.0
0x75a04  ldc.i4.6
0x75a05  ldstr    aIsglobal// "IsGlobal"
0x75a0a  ldstr    aIsglobal_0// "isglobal"
0x75a0f  ldc.i4.1
0x75a10  ldc.i4.0
0x75a11  ldc.i4.0
0x75a12  ldc.i4.0
0x75a13  ldc.i4.0
0x75a14  ldc.i4.0
0x75a15  ldc.i4.0
0x75a16  ldc.i4.3
0x75a17  ldsfld   class [mscorlib]System.Version Microsoft.Crm.Metadata.MetadataForMetadataOrionRtmVersionLoader::CrmPreOrionVersion
0x75a1c  ldc.i4.0
0x75a1d  ldc.i4.0
0x75a1e  ldc.i4.0
0x75a1f  ldc.i4.1
0x75a20  ldnull
0x75a21  ldc.i4.0
0x75a22  ldnull
0x75a23  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription::.ctor(int32 columnNumber, string physicalName, string name, bool validForUpdate, bool isNullable, bool isPrimaryIdField, bool isPrimaryKeyField, bool isLogicalIdentityField, bool isValidForInheritanceCopying, bool isRowIdField, valuetype Microsoft.Crm.Metadata.MetadataAttributeType attributeType, class [mscorlib]System.Version introducedVersion, [opt] bool isUnmanagedAttribute, [opt] bool isOneWayBooleanAttribute, [opt] bool isSolutionRelatedAttribute, [opt] bool validForInsert, [opt] class [mscorlib]System.Type filterTypeForBackCompatSupport, [opt] bool doNotSerializeToOutlook, [opt] string externalName)
0x75a28  newobj   instance void Microsoft.Crm.Metadata.MetadataAttributeMetadata::.ctor(class Microsoft.Crm.Metadata.MetadataAttributeMetadataDescription description)
0x75a2d  call     class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataForMetadataLoaderHelper::AddMetadataAttributeToMetadataEntity(class Microsoft.Crm.Metadata.MetadataEntityMetadata metadataEntity, class Microsoft.Crm.Metadata.MetadataAttributeMetadata metadataAttribute)
0x75a32  pop
0x75a33  ret
```
