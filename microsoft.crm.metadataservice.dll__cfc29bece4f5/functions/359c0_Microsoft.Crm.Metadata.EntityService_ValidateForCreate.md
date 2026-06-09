# Microsoft.Crm.Metadata.EntityService::ValidateForCreate

- ea: `0x359c0`
- end: `0x35c8d`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateForCreate`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `service_task, broker_com_uri`

## callers

- `0x32b80`

## callees

- `0x18530`
- `0x18760`
- `0x2cb30`
- `0x2cb70`
- `0x2cba0`
- `0x2cc50`
- `0x2cc70`
- `0x2cc90`
- `0x2ccb0`
- `0x2cd70`
- `0x2cd90`
- `0x2cdd0`
- `0x2cdf0`
- `0x2ce10`
- `0x2cf30`
- `0x2d1b0`
- `0x2d530`
- `0x359c0`
- `0x35c90`
- `0x35d10`
- `0x35fd0`
- `0x36160`
- `0x361c0`
- `0x361f0`
- `0x36280`
- `0x363d0`
- `0x36780`
- `0x367e0`
- `0x39dd0`
- `0x39ea0`
- `0x39fc0`
- `0x49cc0`
- `0x565f0`
- `0x56710`

## string_xrefs

- `0x359ee`: `Feature Bit for VirtualEntity not enabled, create Virtual Entity not allowed.`

## pseudocode

```c

```

## disassembly

```asm
0x359c0  ldarg.3
0x359c1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x359c6  stloc.0
0x359c7  ldarg.1
0x359c8  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x359cd  stloc.2
0x359ce  ldloca.s 2
0x359d0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x359d5  brfalse.s loc_35A05
0x359d7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x359dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x359e1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_VirtualEntity()
0x359e6  ldloc.0
0x359e7  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x359ec  brtrue.s loc_359FE
0x359ee  ldstr    aFeatureBitForV// "Feature Bit for VirtualEntity not enabl"...
0x359f3  ldc.i4   0x80081113
0x359f8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x359fd  throw
0x359fe  ldarg.0
0x359ff  ldarg.1
0x35a00  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateVirtualEntityCreate(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo)
0x35a05  ldstr    aEntity_0// "Entity"
0x35a0a  ldarg.1
0x35a0b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x35a10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x35a15  ldstr    aEntityid// "entityid"
0x35a1a  ldloc.0
0x35a1b  call     void Microsoft.Crm.Metadata.MetadataValidator::ValidateMetadataIdIsSetAndUnique(string metadataEntityName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataBusinessEntity, string metadataIdColumnName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x35a20  ldarg.1
0x35a21  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_ExternalName()
0x35a26  ldloc.0
0x35a27  ldarg.1
0x35a28  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x35a2d  ldarg.1
0x35a2e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataSourceId()
0x35a33  call     void Microsoft.Crm.Metadata.EntityService::ValidateEntityExternalNameForCreate(string entityExternalName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId)
0x35a38  ldarg.1
0x35a39  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_ExternalCollectionName()
0x35a3e  ldarg.1
0x35a3f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x35a44  call     void Microsoft.Crm.Metadata.EntityService::ValidateEntityExternalCollectionName(string entityExternalCollectionName, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId)
0x35a49  ldarg.1
0x35a4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x35a4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x35a54  brfalse.s loc_35AA1
0x35a56  ldarg.0
0x35a57  ldarg.1
0x35a58  ldarg.2
0x35a59  ldloc.0
0x35a5a  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntityNameAndLabels(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x35a5f  ldarg.2
0x35a60  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x35a65  brtrue.s loc_35AA1
0x35a67  ldarg.1
0x35a68  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35a6d  ldc.i4.8
0x35a6e  beq.s    loc_35AA1
0x35a70  ldarg.1
0x35a71  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35a76  ldc.i4.1
0x35a77  beq.s    loc_35AA1
0x35a79  ldarg.1
0x35a7a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35a7f  brfalse.s loc_35AA1
0x35a81  ldstr    aOwnershiptypem_1// "OwnershipTypeMask: {0} is invalid/not s"...
0x35a86  ldarg.1
0x35a87  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35a8c  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x35a91  call     string [mscorlib]System.String::Format(string, object)
0x35a96  ldc.i4   0x8004700D
0x35a9b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x35aa0  throw
0x35aa1  ldarg.1
0x35aa2  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_AutoRouteToOwnerQueue()
0x35aa7  brfalse.s loc_35AD3
0x35aa9  ldarg.1
0x35aaa  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsCollaboration()
0x35aaf  brfalse.s loc_35AD3
0x35ab1  ldarg.1
0x35ab2  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35ab7  ldc.i4.1
0x35ab8  beq.s    loc_35AD3
0x35aba  ldarg.1
0x35abb  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35ac0  ldc.i4.2
0x35ac1  beq.s    loc_35AD3
0x35ac3  ldarg.1
0x35ac4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_OwnershipTypeMask()
0x35ac9  brtrue.s loc_35AD3
0x35acb  ldarg.2
0x35acc  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x35ad1  brfalse.s loc_35AE3
0x35ad3  ldarg.1
0x35ad4  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_AutoRouteToOwnerQueue()
0x35ad9  brfalse.s loc_35B27
0x35adb  ldarg.1
0x35adc  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsCollaboration()
0x35ae1  brtrue.s loc_35B27
0x35ae3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35ae8  ldstr    aAutoroutetoown_0// "AutoRouteToOwnerQueue can be set only i"...
0x35aed  ldc.i4.2
0x35aee  newarr   [mscorlib]System.Object
0x35af3  dup
0x35af4  ldc.i4.0
0x35af5  ldc.i4.1
0x35af6  stloc.3
0x35af7  ldloca.s 3
0x35af9  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x35aff  callvirt instance string [mscorlib]System.Object::ToString()
0x35b04  stelem.ref
0x35b05  dup
0x35b06  ldc.i4.1
0x35b07  ldc.i4.2
0x35b08  stloc.3
0x35b09  ldloca.s 3
0x35b0b  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x35b11  callvirt instance string [mscorlib]System.Object::ToString()
0x35b16  stelem.ref
0x35b17  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35b1c  ldc.i4   0x80040203
0x35b21  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x35b26  throw
0x35b27  ldarg.1
0x35b28  callvirt instance class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.EntityCreateInfo::get_PrimaryField()
0x35b2d  stloc.1
0x35b2e  ldloc.1
0x35b2f  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x35b34  ldstr    aNvarchar// "nvarchar"
0x35b39  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x35b3e  brfalse.s loc_35B5B
0x35b40  ldstr    aPrimaryfieldCa// "PrimaryField Can only be of Type String"...
0x35b45  ldloc.1
0x35b46  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x35b4b  call     string [mscorlib]System.String::Format(string, object)
0x35b50  ldc.i4   0x8004700E
0x35b55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x35b5a  throw
0x35b5b  ldarg.1
0x35b5c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x35b61  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x35b66  ldstr    aIsonenoteinteg// "isonenoteintegrationenabled"
0x35b6b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x35b70  brtrue.s loc_35B92
0x35b72  ldarg.1
0x35b73  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsOneNoteIntegrationEnabled()
0x35b78  brfalse.s loc_35B92
0x35b7a  ldarg.1
0x35b7b  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsDocumentManagementEnabled()
0x35b80  brtrue.s loc_35B92
0x35b82  ldstr    aYouMustEnableD// "You must enable document management for"...
0x35b87  ldc.i4   0x80060908
0x35b8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x35b91  throw
0x35b92  ldarg.0
0x35b93  ldarg.1
0x35b94  ldloc.0
0x35b95  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateDocumentRecommendationEnabledSettingsForCreate(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x35b9a  ldarg.1
0x35b9b  ldarg.3
0x35b9c  call     void Microsoft.Crm.Metadata.EntityService::ValidateIsVisibleInMobileClientForCreate(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x35ba1  ldarg.2
0x35ba2  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x35ba7  brfalse.s loc_35BC0
0x35ba9  ldloc.1
0x35baa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x35baf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeOf()
0x35bb4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35bb9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x35bbe  brtrue.s loc_35BC8
0x35bc0  ldarg.0
0x35bc1  ldloc.1
0x35bc2  ldloc.0
0x35bc3  callvirt instance void Microsoft.Crm.Metadata.EntityService::ValidatePrimaryAttributeProperties(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x35bc8  ldarg.1
0x35bc9  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x35bce  brtrue.s loc_35BFC
0x35bd0  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ActivityTypeMasks
0x35bd5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35bda  ldarg.1
0x35bdb  callvirt instance int32 Microsoft.Crm.Metadata.EntityCreateInfo::get_ActivityTypeMask()
0x35be0  box      [mscorlib]System.Int32
0x35be5  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x35bea  brtrue.s loc_35BFC
0x35bec  ldstr    aTheActivitytyp// "The ActivityTypeMask property must be s"...
0x35bf1  ldc.i4   0x80040203
0x35bf6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x35bfb  throw
0x35bfc  ldarg.2
0x35bfd  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x35c02  brfalse.s loc_35C2F
0x35c04  ldarg.3
0x35c05  newobj   instance void Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x35c0a  ldarg.1
0x35c0b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x35c10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x35c15  stloc.s  4
0x35c17  ldloca.s 4
0x35c19  ldstr    aN// "N"
0x35c1e  call     instance string [mscorlib]System.Guid::ToString(string)
0x35c23  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x35c28  call     instance bool Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::ShouldValidateChangeTrackingSettings(string entityId)
0x35c2d  brfalse.s loc_35C37
0x35c2f  ldarg.0
0x35c30  ldarg.1
0x35c31  ldarg.3
0x35c32  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateChangeTrackingSettingsForCreateEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x35c37  ldarg.0
0x35c38  ldarg.1
0x35c39  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateDaysSinceRecordLastModifiedForCreateEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo)
0x35c3e  ldarg.1
0x35c3f  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityColor()
0x35c44  call     void Microsoft.Crm.Metadata.EntityService::ValidateEntityColor(string entityColor)
0x35c49  ldarg.1
0x35c4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x35c4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x35c54  brfalse.s loc_35C6A
0x35c56  ldarg.2
0x35c57  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x35c5c  brtrue.s loc_35C6A
0x35c5e  ldarg.0
0x35c5f  ldarg.1
0x35c60  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntitySetName()
0x35c65  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsCompliant(string entitySetName)
0x35c6a  ldarg.1
0x35c6b  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntitySetName()
0x35c70  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35c75  brtrue.s loc_35C84
0x35c77  ldarg.0
0x35c78  ldarg.1
0x35c79  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_EntitySetName()
0x35c7e  ldloc.0
0x35c7f  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsUnique(string entitySetName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x35c84  ldarg.0
0x35c85  ldarg.1
0x35c86  ldloc.0
0x35c87  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateExternalSearchSettingsForCreate(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x35c8c  ret
```
