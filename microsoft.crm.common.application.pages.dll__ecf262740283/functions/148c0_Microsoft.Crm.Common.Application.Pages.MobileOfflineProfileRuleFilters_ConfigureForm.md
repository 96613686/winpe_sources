# Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::ConfigureForm

- ea: `0x148c0`
- end: `0x14a98`
- name: `Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::ConfigureForm`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x147a0`
- `0x147b0`
- `0x147c0`
- `0x147d0`
- `0x148c0`
- `0x14aa0`
- `0x14cd0`
- `0x14d00`

## pseudocode

```c

```

## disassembly

```asm
0x148c0  ldarg.0
0x148c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x148c6  ldarg.0
0x148c7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x148cc  ldc.i4.2
0x148cd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Modes(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindModes)
0x148d2  ldarg.0
0x148d3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x148d8  ldc.i4.2
0x148d9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_StartupMode(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindStartupMode)
0x148de  ldarg.0
0x148df  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x148e4  ldc.i4.0
0x148e5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_TitleVisible(bool)
0x148ea  ldarg.0
0x148eb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x148f0  ldc.i4.0
0x148f1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ValidQueryType(int32)
0x148f6  ldarg.0
0x148f7  call     instance bool Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::get_IsReadOnly()
0x148fc  brfalse.s loc_1490A
0x148fe  ldarg.0
0x148ff  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x14904  ldc.i4.1
0x14905  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IsReadOnly(bool)
0x1490a  ldarg.0
0x1490b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x14910  ldarg.0
0x14911  call     instance bool Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::GetShowChangeGroupMenuValue()
0x14916  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ShowChangeGroupMenu(bool)
0x1491b  ldc.i4.1
0x1491c  stloc.0
0x1491d  ldarg.0
0x1491e  ldarg.0
0x1491f  call     instance bool Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::IsProfileItemAssociationFiltersPage()
0x14924  call     instance void Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::set_IsProfileItemAssociationPage(bool value)
0x14929  ldarg.0
0x1492a  call     instance bool Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::get_IsProfileItemAssociationPage()
0x1492f  brfalse.s loc_1496C
0x14931  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x14936  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1493b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfflineProfileRuleEnhancementsORSupportForProfileItemAssociation()
0x14940  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14945  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1494a  stloc.0
0x1494b  ldarg.0
0x1494c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x14951  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x14956  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfflineProfileRuleEnhancementsSlidingWindowForProfileItemAssociation()
0x1495b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14960  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14965  call     instance void Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::set_GetSlidingWindowFCBValue(bool value)
0x1496a  br.s     loc_149A5
0x1496c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x14971  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x14976  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfflineProfileRuleEnhancementsORSupportForProfileItem()
0x1497b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14980  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14985  stloc.0
0x14986  ldarg.0
0x14987  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1498c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x14991  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OfflineProfileRuleEnhancementsSlidingWindowForProfileItem()
0x14996  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1499b  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x149a0  call     instance void Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::set_GetSlidingWindowFCBValue(bool value)
0x149a5  ldloc.0
0x149a6  brfalse.s loc_149BA
0x149a8  ldarg.0
0x149a9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x149ae  ldc.i4   0x8E
0x149b3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Buttons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AdvancedFindButtons)
0x149b8  br.s     loc_149C6
0x149ba  ldarg.0
0x149bb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x149c0  ldc.i4.2
0x149c1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Buttons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AdvancedFindButtons)
0x149c6  ldarg.0
0x149c7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x149cc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x149d1  ldstr    aEntitycode// "entityCode"
0x149d6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x149db  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x149e0  brtrue.s loc_14A24
0x149e2  ldarg.0
0x149e3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x149e8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x149ed  ldstr    aEntitycode// "entityCode"
0x149f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x149f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x149fc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x14a01  stloc.1
0x14a02  ldarg.0
0x14a03  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x14a08  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14a0d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14a12  ldloc.1
0x14a13  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x14a18  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x14a1d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_EntityName(string)
0x14a22  br.s     loc_14A7F
0x14a24  ldarg.0
0x14a25  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14a2a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14a2f  ldstr    aRelationshipdi// "relationshipDisplayName"
0x14a34  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14a39  callvirt instance string [mscorlib]System.Object::ToString()
0x14a3e  stloc.2
0x14a3f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14a44  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14a49  ldloc.2
0x14a4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetRelationship(string)
0x14a4f  pop
0x14a50  ldloca.s 3
0x14a52  ldarg.0
0x14a53  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14a58  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14a5d  ldstr    aMobileofflinep_3// "mobileOfflineProfileItemId"
0x14a62  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14a67  call     instance void [mscorlib]System.Guid::.ctor(string)
0x14a6c  ldarg.0
0x14a6d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x14a72  ldarg.0
0x14a73  ldloc.3
0x14a74  ldloc.2
0x14a75  call     instance string Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::GetEntityName(valuetype [mscorlib]System.Guid mobileOfflineProfileItemId, string relationshipSchemaName)
0x14a7a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_EntityName(string)
0x14a7f  ldarg.0
0x14a80  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x14a85  ldc.i4.0
0x14a86  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_EntityListVisible(bool)
0x14a8b  ldarg.0
0x14a8c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::advFind
0x14a91  ldc.i4.0
0x14a92  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_RelatedEntitiesVisible(bool)
0x14a97  ret
```
