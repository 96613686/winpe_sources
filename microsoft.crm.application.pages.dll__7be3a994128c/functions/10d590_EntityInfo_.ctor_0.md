# EntityInfo::.ctor_0

- ea: `0x10d590`
- end: `0x10e168`
- name: `EntityInfo::.ctor_0`
- size: `3032`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0xb0810`

## callees

- `0xb0e20`
- `0x10d3c0`
- `0x10d3e0`
- `0x10d590`
- `0x10e170`
- `0x10e280`
- `0x10e3b0`

## string_xrefs

- `0x10d743`: `isrenameable`
- `0x10d773`: `isrenameable`
- `0x10d7af`: `isrenameable`
- `0x10d7d8`: `isrenameable`
- `0x10d909`: `isrenameable`
- `0x10df25`: `canmodifymobileclientreadonly`

## pseudocode

```c

```

## disassembly

```asm
0x10d590  ldarg.0
0x10d591  ldsfld   string [mscorlib]System.String::Empty
0x10d596  stfld    string EntityInfo::singularName
0x10d59b  ldarg.0
0x10d59c  ldsfld   string [mscorlib]System.String::Empty
0x10d5a1  stfld    string EntityInfo::pluralName
0x10d5a6  ldarg.0
0x10d5a7  ldsfld   string [mscorlib]System.String::Empty
0x10d5ac  stfld    string EntityInfo::schemaName
0x10d5b1  ldarg.0
0x10d5b2  ldsfld   string [mscorlib]System.String::Empty
0x10d5b7  stfld    string EntityInfo::externalName
0x10d5bc  ldarg.0
0x10d5bd  ldsfld   string [mscorlib]System.String::Empty
0x10d5c2  stfld    string EntityInfo::externalCollectionName
0x10d5c7  ldarg.0
0x10d5c8  ldc.i4.1
0x10d5c9  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes EntityInfo::ownershipType
0x10d5ce  ldarg.0
0x10d5cf  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, string>::.ctor()
0x10d5d4  stfld    class [System]System.Collections.Generic.SortedList`2<string, string> EntityInfo::imageFields
0x10d5d9  ldarg.0
0x10d5da  ldsfld   string [mscorlib]System.String::Empty
0x10d5df  stfld    string EntityInfo::entityColor
0x10d5e4  ldarg.0
0x10d5e5  ldc.i4.2
0x10d5e6  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x10d5eb  dup
0x10d5ec  ldc.i4.0
0x10d5ed  ldc.i4.1
0x10d5ee  stelem.i4
0x10d5ef  dup
0x10d5f0  ldc.i4.1
0x10d5f1  ldc.i4.8
0x10d5f2  stelem.i4
0x10d5f3  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes[] EntityInfo::ownershipTypes
0x10d5f8  ldarg.0
0x10d5f9  ldsfld   string [mscorlib]System.String::Empty
0x10d5fe  stfld    string EntityInfo::description
0x10d603  ldarg.0
0x10d604  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x10d609  stfld    class [mscorlib]System.Collections.ArrayList EntityInfo::displayAreas
0x10d60e  ldarg.0
0x10d60f  ldc.i4.1
0x10d610  stfld    bool EntityInfo::IsCommunicationActivityChecked
0x10d615  ldarg.0
0x10d616  ldc.i4.1
0x10d617  stfld    bool EntityInfo::supportsDupCheck
0x10d61c  ldarg.0
0x10d61d  ldc.i4.1
0x10d61e  stfld    bool EntityInfo::supportsMailMerge
0x10d623  ldarg.0
0x10d624  ldc.i4.1
0x10d625  stfld    bool EntityInfo::supportsAudit
0x10d62a  ldarg.0
0x10d62b  ldc.i4.1
0x10d62c  stfld    bool EntityInfo::showPrimaryAttribute
0x10d631  ldarg.0
0x10d632  ldc.i4.1
0x10d633  stfld    bool EntityInfo::daysSinceRecordLastModifiedDisabled
0x10d638  ldarg.0
0x10d639  ldsfld   string [mscorlib]System.String::Empty
0x10d63e  stfld    string EntityInfo::attributeDisplayName
0x10d643  ldarg.0
0x10d644  ldsfld   string [mscorlib]System.String::Empty
0x10d649  stfld    string EntityInfo::attributeSchemaName
0x10d64e  ldarg.0
0x10d64f  ldsfld   string [mscorlib]System.String::Empty
0x10d654  stfld    string EntityInfo::attributeExternalName
0x10d659  ldarg.0
0x10d65a  ldsfld   string [mscorlib]System.String::Empty
0x10d65f  stfld    string EntityInfo::attributeDescription
0x10d664  ldarg.0
0x10d665  ldc.i4.2
0x10d666  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel EntityInfo::attributeReqLevel
0x10d66b  ldarg.0
0x10d66c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x10d671  stfld    class [mscorlib]System.Collections.ArrayList EntityInfo::attributeReqLevels
0x10d676  ldarg.0
0x10d677  ldstr    aNvarchar// "nvarchar"
0x10d67c  stfld    string EntityInfo::attributeType
0x10d681  ldarg.0
0x10d682  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeFormats::get_Text()
0x10d687  stfld    string EntityInfo::attributeFormat
0x10d68c  ldarg.0
0x10d68d  ldc.i4.s 0x64
0x10d68f  stfld    int32 EntityInfo::attributeLen
0x10d694  ldarg.0
0x10d695  ldc.i4.1
0x10d696  stfld    int32 EntityInfo::attributeMinLen
0x10d69b  ldarg.0
0x10d69c  ldc.i4   0xFA0
0x10d6a1  stfld    int32 EntityInfo::attributeMaxLen
0x10d6a6  ldarg.0
0x10d6a7  ldc.i4.1
0x10d6a8  stfld    bool EntityInfo::readingPaneEnabled
0x10d6ad  ldarg.0
0x10d6ae  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10d6b3  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x10d6b8  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> EntityInfo::dataSourceId
0x10d6bd  ldarg.0
0x10d6be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10d6c3  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x10d6c8  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> EntityInfo::dataProviderId
0x10d6cd  ldarg.0
0x10d6ce  call     instance void [mscorlib]System.Object::.ctor()
0x10d6d3  ldarg.3
0x10d6d4  stloc.0
0x10d6d5  ldarg.2
0x10d6d6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_DataProviderId()
0x10d6db  stloc.s  5
0x10d6dd  ldloca.s 5
0x10d6df  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x10d6e4  stloc.1
0x10d6e5  ldc.i4.0
0x10d6e6  stloc.2
0x10d6e7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x10d6ec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x10d6f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessUnification()
0x10d6f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10d6fb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10d700  brfalse.s loc_10D725
0x10d702  ldarg.2
0x10d703  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x10d708  brfalse.s loc_10D725
0x10d70a  ldarg.0
0x10d70b  ldc.i4.1
0x10d70c  stfld    bool EntityInfo::isBPFEntity
0x10d711  ldc.i4.1
0x10d712  starg.s  3
0x10d714  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10d719  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsProcessUnificationV2EntityCustomizationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10d71e  brfalse.s loc_10D725
0x10d720  ldc.i4.0
0x10d721  starg.s  3
0x10d723  ldc.i4.1
0x10d724  stloc.2
0x10d725  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10d72a  stloc.3
0x10d72b  ldarg.0
0x10d72c  ldarg.2
0x10d72d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x10d732  ldarg.2
0x10d733  ldc.i4.1
0x10d734  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x10d739  stfld    string EntityInfo::singularName
0x10d73e  ldarg.0
0x10d73f  ldarg.3
0x10d740  brtrue.s loc_10D755
0x10d742  ldarg.2
0x10d743  ldstr    aIsrenameable// "isrenameable"
0x10d748  ldarg.2
0x10d749  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsRenameable()
0x10d74e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x10d753  br.s     loc_10D756
0x10d755  ldc.i4.1
0x10d756  stfld    bool EntityInfo::singularNameDisabled
0x10d75b  ldarg.0
0x10d75c  ldarg.2
0x10d75d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x10d762  ldarg.2
0x10d763  ldc.i4.2
0x10d764  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x10d769  stfld    string EntityInfo::pluralName
0x10d76e  ldarg.0
0x10d76f  ldarg.3
0x10d770  brtrue.s loc_10D785
0x10d772  ldarg.2
0x10d773  ldstr    aIsrenameable// "isrenameable"
0x10d778  ldarg.2
0x10d779  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsRenameable()
0x10d77e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x10d783  br.s     loc_10D786
0x10d785  ldc.i4.1
0x10d786  stfld    bool EntityInfo::pluralNameDisabled
0x10d78b  ldarg.0
0x10d78c  ldarg.2
0x10d78d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x10d792  stfld    string EntityInfo::schemaName
0x10d797  ldarg.0
0x10d798  ldc.i4.1
0x10d799  stfld    bool EntityInfo::schemaNameDisabled
0x10d79e  ldarg.0
0x10d79f  ldarg.2
0x10d7a0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ExternalName()
0x10d7a5  stfld    string EntityInfo::externalName
0x10d7aa  ldarg.0
0x10d7ab  ldarg.3
0x10d7ac  brtrue.s loc_10D7C1
0x10d7ae  ldarg.2
0x10d7af  ldstr    aIsrenameable// "isrenameable"
0x10d7b4  ldarg.2
0x10d7b5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsRenameable()
0x10d7ba  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x10d7bf  br.s     loc_10D7C2
0x10d7c1  ldc.i4.1
0x10d7c2  stfld    bool EntityInfo::externalNameDisabled
0x10d7c7  ldarg.0
0x10d7c8  ldarg.2
0x10d7c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ExternalCollectionName()
0x10d7ce  stfld    string EntityInfo::externalCollectionName
0x10d7d3  ldarg.0
0x10d7d4  ldarg.3
0x10d7d5  brtrue.s loc_10D7EA
0x10d7d7  ldarg.2
0x10d7d8  ldstr    aIsrenameable// "isrenameable"
0x10d7dd  ldarg.2
0x10d7de  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsRenameable()
0x10d7e3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x10d7e8  br.s     loc_10D7EB
0x10d7ea  ldc.i4.1
0x10d7eb  stfld    bool EntityInfo::externalCollectionNameDisabled
0x10d7f0  ldarg.0
0x10d7f1  ldc.i4.4
0x10d7f2  newarr   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes
0x10d7f7  dup
0x10d7f8  ldtoken  valuetype __StaticArrayInitTypeSize=16 <PrivateImplementationDetails>::'89CDDC6F2B178E76E863F5442FFA5CB792CC089A'
0x10d7fd  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x10d802  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes[] EntityInfo::ownershipTypes
0x10d807  ldarg.0
0x10d808  ldarg.2
0x10d809  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_OwnershipTypeMask()
0x10d80e  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OwnershipTypes EntityInfo::ownershipType
0x10d813  ldarg.0
0x10d814  ldc.i4.1
0x10d815  stfld    bool EntityInfo::ownershipTypeDisabled
0x10d81a  ldarg.0
0x10d81b  ldarg.2
0x10d81c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryImageField()
0x10d821  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata EntityInfo::primaryImageField
0x10d826  ldarg.2
0x10d827  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x10d82c  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x10d831  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x10d836  stloc.s  6
0x10d838  br.s     loc_10D88A
0x10d83a  ldloc.s  6
0x10d83c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x10d841  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x10d846  stloc.s  7
0x10d848  ldloc.s  7
0x10d84a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x10d84f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x10d854  ldstr    aImage_2// "image"
0x10d859  ldc.i4.4
0x10d85a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10d85f  brfalse.s loc_10D88A
0x10d861  ldarg.0
0x10d862  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> EntityInfo::imageFields
0x10d867  ldloc.s  7
0x10d869  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x10d86e  ldloc.s  7
0x10d870  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x10d875  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x10d87a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x10d87f  ldloc.3
0x10d880  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10d885  callvirt instance void class [System]System.Collections.Generic.SortedList`2<string, string>::Add(var<u1>, !!T0)
0x10d88a  ldloc.s  6
0x10d88c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10d891  brtrue.s loc_10D83A
0x10d893  leave.s  loc_10D8AA
0x10d895  ldloc.s  6
0x10d897  isinst   [mscorlib]System.IDisposable
0x10d89c  stloc.s  8
0x10d89e  ldloc.s  8
0x10d8a0  brfalse.s loc_10D8A9
0x10d8a2  ldloc.s  8
0x10d8a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10d8a9  endfinally
0x10d8aa  ldarg.0
0x10d8ab  ldarg.3
0x10d8ac  brtrue.s loc_10D8CA
0x10d8ae  ldarg.0
0x10d8af  ldfld    class [System]System.Collections.Generic.SortedList`2<string, string> EntityInfo::imageFields
0x10d8b4  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, string>::get_Count()
0x10d8b9  brfalse.s loc_10D8CA
0x10d8bb  ldarg.2
0x10d8bc  ldnull
0x10d8bd  ldarg.2
0x10d8be  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyAdditionalSettings()
0x10d8c3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ManagedPropertyCheckUtil::IsPropertyDisabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, string, bool)
0x10d8c8  br.s     loc_10D8CB
0x10d8ca  ldc.i4.1
0x10d8cb  stfld    bool EntityInfo::isPrimaryImageFieldDisabled
0x10d8d0  ldarg.0
0x10d8d1  ldarg.2
0x10d8d2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityColor()
0x10d8d7  stfld    string EntityInfo::entityColor
0x10d8dc  ldarg.0
0x10d8dd  ldarg.2
0x10d8de  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x10d8e3  stfld    bool EntityInfo::isCustomEntity
0x10d8e8  ldarg.0
0x10d8e9  ldarg.2
0x10d8ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Description()
0x10d8ef  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x10d8f4  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x10d8f9  ldloc.3
0x10d8fa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
  ... truncated ...
```
