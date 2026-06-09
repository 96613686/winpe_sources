# Microsoft.Crm.Application.Components.UI.ExternalApplications::.ctor

- ea: `0x18040`
- end: `0x18317`
- name: `Microsoft.Crm.Application.Components.UI.ExternalApplications::.ctor`
- size: `727`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14ef0`
- `0x15090`
- `0x150d0`
- `0x15170`
- `0x18040`
- `0x23c50`
- `0x24040`
- `0x26530`
- `0x26750`

## string_xrefs

- `0x1819b`: `ms-crm-ExternalPartyEnabledConfig-Button`
- `0x181f0`: `ms-crm-ExternalPartyEnabledConfig-Button`
- `0x181b6`: `SelectAutoCreateExternalPartyEnabledEntities`
- `0x181cb`: `External_Applications_Setup_AutoCreate_ExternalParty_Entities_ButtonText`
- `0x181e0`: `SelectAutoCreateExternalPartyEntitiesButtonClicked()`

## pseudocode

```c

```

## disassembly

```asm
0x18040  ldarg.0
0x18041  ldc.i4   0x409
0x18046  stfld    int32 Microsoft.Crm.Application.Components.UI.ExternalApplications::userLanguageCode
0x1804b  ldarg.0
0x1804c  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor()
0x18051  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x18056  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1805b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x18060  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x18065  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1806a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1806f  brfalse  loc_18316
0x18074  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18079  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1807e  stloc.0
0x1807f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18084  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x18089  stloc.1
0x1808a  ldloca.s 1
0x1808c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x18091  brfalse.s loc_180AB
0x18093  ldarg.0
0x18094  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18099  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x1809e  stloc.1
0x1809f  ldloca.s 1
0x180a1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x180a6  stfld    int32 Microsoft.Crm.Application.Components.UI.ExternalApplications::userLanguageCode
0x180ab  ldarg.0
0x180ac  ldstr    aContact// "contact"
0x180b1  stfld    string Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectedExternalPartyEntityLogicalName
0x180b6  ldarg.0
0x180b7  ldloc.0
0x180b8  ldstr    aContact// "contact"
0x180bd  ldc.i4.1
0x180be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x180c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x180c8  ldarg.0
0x180c9  ldfld    int32 Microsoft.Crm.Application.Components.UI.ExternalApplications::userLanguageCode
0x180ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x180d3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x180d8  stfld    string Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectedExternalPartyEntityDisplayName
0x180dd  ldarg.0
0x180de  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x180e3  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_corrAttributeSelect
0x180e8  ldarg.0
0x180e9  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_corrAttributeSelect
0x180ee  ldstr    aCorrattributes// "corrAttributesFields"
0x180f3  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x180f8  ldarg.0
0x180f9  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_corrAttributeSelect
0x180fe  ldstr    aOncorrelationk// "onCorrelationKeyMapFieldChange(this);"
0x18103  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string value)
0x18108  ldarg.0
0x18109  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_corrAttributeSelect
0x1810e  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x18113  ldarg.0
0x18114  ldnull
0x18115  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_extChannelattributeSelect
0x1811a  ldarg.0
0x1811b  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x18120  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_parentAttributeSelect
0x18125  ldarg.0
0x18126  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_parentAttributeSelect
0x1812b  ldstr    aParentattribut// "parentAttributeField"
0x18130  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x18135  ldarg.0
0x18136  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_parentAttributeSelect
0x1813b  ldstr    aOnparentfieldc// "onParentFieldChange(this);"
0x18140  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string value)
0x18145  ldarg.0
0x18146  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.ExternalApplications::_parentAttributeSelect
0x1814b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x18150  ldarg.0
0x18151  newobj   instance void Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x18156  stfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectExternalPartyEnabledEntities
0x1815b  ldarg.0
0x1815c  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectExternalPartyEnabledEntities
0x18161  ldstr    aSelectexternal// "SelectExternalPartyEnabledEntities"
0x18166  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1816b  ldarg.0
0x1816c  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectExternalPartyEnabledEntities
0x18171  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18176  ldstr    aExternalApplic// "External_Applications_Setup_ExternalPar"...
0x1817b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18180  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_Text(string value)
0x18185  ldarg.0
0x18186  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectExternalPartyEnabledEntities
0x1818b  ldstr    aSelectexternal_0// "SelectExternalPartyEntitiesButtonClicke"...
0x18190  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_OnClick(string value)
0x18195  ldarg.0
0x18196  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectExternalPartyEnabledEntities
0x1819b  ldstr    aMsCrmExternalp// "ms-crm-ExternalPartyEnabledConfig-Butto"...
0x181a0  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_CssClass(string value)
0x181a5  ldarg.0
0x181a6  newobj   instance void Microsoft.Crm.Application.Components.UI.Button::.ctor()
0x181ab  stfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectAutoCreateExternalPartyEnabledEntities
0x181b0  ldarg.0
0x181b1  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectAutoCreateExternalPartyEnabledEntities
0x181b6  ldstr    aSelectautocrea// "SelectAutoCreateExternalPartyEnabledEnt"...
0x181bb  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x181c0  ldarg.0
0x181c1  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectAutoCreateExternalPartyEnabledEntities
0x181c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x181cb  ldstr    aExternalApplic_0// "External_Applications_Setup_AutoCreate_"...
0x181d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x181d5  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_Text(string value)
0x181da  ldarg.0
0x181db  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectAutoCreateExternalPartyEnabledEntities
0x181e0  ldstr    aSelectautocrea_0// "SelectAutoCreateExternalPartyEntitiesBu"...
0x181e5  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_OnClick(string value)
0x181ea  ldarg.0
0x181eb  ldfld    class Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Components.UI.ExternalApplications::_selectAutoCreateExternalPartyEnabledEntities
0x181f0  ldstr    aMsCrmExternalp// "ms-crm-ExternalPartyEnabledConfig-Butto"...
0x181f5  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_CssClass(string value)
0x181fa  ldarg.0
0x181fb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::.ctor()
0x18200  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalPartyEnabledEntityMetaList
0x18205  ldarg.0
0x18206  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::.ctor()
0x1820b  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalChannelEnabledEntityMetaList
0x18210  ldarg.0
0x18211  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x18216  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalChannelEntityNames
0x1821b  ldarg.0
0x1821c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x18221  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalPartyEnabledEntityNames
0x18226  ldarg.0
0x18227  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1822c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x18231  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x18236  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x1823b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x18240  ldarg.0
0x18241  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18246  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1824b  ldarg.0
0x1824c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18251  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x18256  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetExternalPartyEnabledEntityNames()
0x1825b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x18260  stloc.2
0x18261  ldc.i4.0
0x18262  stloc.3
0x18263  br.s     loc_182A6
0x18265  ldloc.2
0x18266  ldloc.3
0x18267  ldelem.ref
0x18268  stloc.s  4
0x1826a  ldarg.0
0x1826b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Application.Components.UI.ExternalApplications::orgContext
0x18270  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18275  ldloc.s  4
0x18277  ldc.i4.1
0x18278  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1827d  stloc.s  5
0x1827f  ldloc.s  5
0x18281  brfalse.s loc_182A2
0x18283  ldarg.0
0x18284  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalPartyEnabledEntityMetaList
0x18289  ldloc.s  5
0x1828b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::Add(var<u1>)
0x18290  ldarg.0
0x18291  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalPartyEnabledEntityNames
0x18296  ldloc.s  5
0x18298  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1829d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x182a2  ldloc.3
0x182a3  ldc.i4.1
0x182a4  add
0x182a5  stloc.3
0x182a6  ldloc.3
0x182a7  ldloc.2
0x182a8  ldlen
0x182a9  conv.i4
0x182aa  blt.s    loc_18265
0x182ac  ldloc.0
0x182ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x182b2  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x182b7  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x182bc  stloc.s  6
0x182be  br.s     loc_182F6
0x182c0  ldloc.s  6
0x182c2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x182c7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata
0x182cc  stloc.s  7
0x182ce  ldloc.s  7
0x182d0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsEnabledForExternalChannels()
0x182d5  brfalse.s loc_182F6
0x182d7  ldarg.0
0x182d8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalChannelEnabledEntityMetaList
0x182dd  ldloc.s  7
0x182df  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::Add(var<u1>)
0x182e4  ldarg.0
0x182e5  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalChannelEntityNames
0x182ea  ldloc.s  7
0x182ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x182f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x182f6  ldloc.s  6
0x182f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x182fd  brtrue.s loc_182C0
0x182ff  leave.s  loc_18316
0x18301  ldloc.s  6
0x18303  isinst   [mscorlib]System.IDisposable
0x18308  stloc.s  8
0x1830a  ldloc.s  8
0x1830c  brfalse.s loc_18315
0x1830e  ldloc.s  8
0x18310  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18315  endfinally
0x18316  ret
```
