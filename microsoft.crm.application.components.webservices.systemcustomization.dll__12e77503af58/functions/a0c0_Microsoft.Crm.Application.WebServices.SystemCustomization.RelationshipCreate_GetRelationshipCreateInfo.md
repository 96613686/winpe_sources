# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetRelationshipCreateInfo

- ea: `0xa0c0`
- end: `0xa295`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetRelationshipCreateInfo`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x9e50`

## callees

- `0x190`
- `0x1a0`
- `0x200`
- `0x220`
- `0x240`
- `0x290`
- `0x310`
- `0x360`
- `0xa0c0`
- `0xa2a0`
- `0xa300`
- `0xa3d0`

## string_xrefs

- `0xa1de`: `isfieldsecurityenabled`
- `0xa1c8`: `linkedattributeid`
- `0xa144`: `CreateExternalPartyEnabledEntityRelationshipCall`

## pseudocode

```c

```

## disassembly

```asm
0xa0c0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::.ctor()
0xa0c5  stloc.0
0xa0c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa0cb  stloc.1
0xa0cc  ldloc.1
0xa0cd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa0d2  stloc.2
0xa0d3  ldloc.0
0xa0d4  ldarg.0
0xa0d5  ldstr    aReferencedenti// "referencedentityname"
0xa0da  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa0df  ldloc.1
0xa0e0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::EntityPlatformNameFromLogicalName(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa0e5  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_PrimaryEntityName(string)
0xa0ea  ldloc.0
0xa0eb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_PrimaryEntityInstanceName()
0xa0f0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa0f5  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa0fa  ldarg.0
0xa0fb  ldstr    aReferencedinst// "referencedinstancename"
0xa100  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa105  ldloc.1
0xa106  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa10b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xa110  ldloc.0
0xa111  ldarg.0
0xa112  ldstr    aReferencingent// "referencingentityname"
0xa117  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa11c  ldloc.1
0xa11d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::EntityPlatformNameFromLogicalName(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa122  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelatedEntityName(string)
0xa127  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xa12c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xa131  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0xa136  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xa13b  ldloc.1
0xa13c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa141  brfalse.s loc_A163
0xa143  ldarg.0
0xa144  ldstr    aCreateexternal// "CreateExternalPartyEnabledEntityRelatio"...
0xa149  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa14e  brfalse.s loc_A163
0xa150  ldloc.0
0xa151  ldarg.0
0xa152  ldstr    aAttributeschem// "attributeschemaname"
0xa157  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa15c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeName(string)
0xa161  br.s     loc_A179
0xa163  ldloc.0
0xa164  ldarg.0
0xa165  ldstr    aAttributeschem// "attributeschemaname"
0xa16a  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa16f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetSchemaName(string)
0xa174  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeName(string)
0xa179  ldloc.0
0xa17a  ldarg.0
0xa17b  ldstr    aReqlevel// "reqlevel"
0xa180  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0xa185  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa18a  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa18f  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0xa194  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeRequiredLevel(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel)
0xa199  ldloc.0
0xa19a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_Description()
0xa19f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa1a4  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa1a9  ldarg.0
0xa1aa  ldstr    aDescription// "description"
0xa1af  ldloc.2
0xa1b0  ldloc.0
0xa1b1  call     string Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetDefaultDecription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo relationshipInfo)
0xa1b6  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xa1bb  ldloc.1
0xa1bc  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1c1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xa1c6  ldloc.0
0xa1c7  ldarg.0
0xa1c8  ldstr    aLinkedattribut_0// "linkedattributeid"
0xa1cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa1d2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0xa1d7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_LinkedAttributeId(valuetype [mscorlib]System.Guid)
0xa1dc  ldloc.0
0xa1dd  ldarg.0
0xa1de  ldstr    aIsfieldsecurit// "isfieldsecurityenabled"
0xa1e3  ldc.i4.0
0xa1e4  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name, bool defaultValue)
0xa1e9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeIsSecured(bool)
0xa1ee  ldloc.0
0xa1ef  ldarg.0
0xa1f0  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0xa1f5  ldc.i4.1
0xa1f6  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0xa1fb  ldc.i4.0
0xa1fc  cgt.un
0xa1fe  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipValidForAdvancedFind(bool)
0xa203  ldloc.0
0xa204  ldarg.0
0xa205  ldstr    aIshierarchical_0// "ishierarchical"
0xa20a  ldc.i4.0
0xa20b  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0xa210  ldc.i4.0
0xa211  cgt.un
0xa213  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsHierarchical(bool)
0xa218  ldarg.0
0xa219  ldstr    aCascading// "cascading"
0xa21e  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa223  ldloc.0
0xa224  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetCascadingInfo(class Microsoft.Crm.Application.WebServices.ParameterBag cascadingBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo relationshipInfo)
0xa229  ldloc.0
0xa22a  ldloc.1
0xa22b  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa230  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ReferencingEntityRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xa235  ldarg.0
0xa236  ldstr    aAssociatedmenu// "associatedmenu"
0xa23b  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa240  ldloc.0
0xa241  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_ReferencingEntityRoleInfo()
0xa246  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa24b  ldloc.0
0xa24c  ldarg.0
0xa24d  ldstr    aSchemaname// "schemaname"
0xa252  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa257  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_SchemaName(string)
0xa25c  ldloc.2
0xa25d  ldloc.0
0xa25e  callvirt instance string [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::get_RelatedEntityName()
0xa263  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0xa268  stloc.3
0xa269  ldloc.3
0xa26a  brfalse.s loc_A293
0xa26c  ldloc.3
0xa26d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_DataProviderId()
0xa272  stloc.s  4
0xa274  ldloca.s 4
0xa276  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xa27b  brfalse.s loc_A293
0xa27d  ldloc.0
0xa27e  ldarg.0
0xa27f  ldstr    aExternalname// "externalname"
0xa284  ldsfld   string [mscorlib]System.String::Empty
0xa289  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xa28e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ExternalName(string)
0xa293  ldloc.0
0xa294  ret
```
