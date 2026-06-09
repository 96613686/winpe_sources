# Microsoft.Crm.Application.Components.UI.ExternalApplications::ConfigureHeader

- ea: `0x183a0`
- end: `0x184cf`
- name: `Microsoft.Crm.Application.Components.UI.ExternalApplications::ConfigureHeader`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2ef0`
- `0x3270`
- `0x3380`
- `0x18320`
- `0x18340`
- `0x18360`
- `0x18380`
- `0x183a0`
- `0x23b60`
- `0x24080`

## string_xrefs

- `0x183cf`: `/_static/tools/_common/scripts/ExternalApplications.js`
- `0x183df`: `_correlationKeyMapSettingsXml`
- `0x183f5`: `_externalPartyEnabledEntitiesSettingsXml`

## pseudocode

```c

```

## disassembly

```asm
0x183a0  ldarg.0
0x183a1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x183a6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x183ab  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x183b0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x183b5  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x183ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x183bf  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x183c4  brfalse  loc_184CE
0x183c9  ldarg.0
0x183ca  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x183cf  ldstr    aStaticToolsCom// "/_static/tools/_common/scripts/External"...
0x183d4  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x183d9  ldarg.0
0x183da  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x183df  ldstr    aCorrelationkey// "_correlationKeyMapSettingsXml"
0x183e4  ldarg.0
0x183e5  call     instance string Microsoft.Crm.Application.Components.UI.ExternalApplications::get_CorrelationKeyMapSettingsXml()
0x183ea  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x183ef  ldarg.0
0x183f0  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x183f5  ldstr    aExternalpartye// "_externalPartyEnabledEntitiesSettingsXm"...
0x183fa  ldarg.0
0x183fb  call     instance string Microsoft.Crm.Application.Components.UI.ExternalApplications::get_ExternalPartyEnabledEntitiesSettingsXml()
0x18400  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x18405  ldarg.0
0x18406  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1840b  ldstr    aDefaultselecte// "_defaultSelectedEntityLogicalName"
0x18410  ldarg.0
0x18411  call     instance string Microsoft.Crm.Application.Components.UI.ExternalApplications::get_SelectedExternalPartyEntityLogicalName()
0x18416  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x1841b  ldarg.0
0x1841c  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x18421  ldstr    aDefaultselecte_0// "_defaultSelectedEntityDisplayName"
0x18426  ldarg.0
0x18427  call     instance string Microsoft.Crm.Application.Components.UI.ExternalApplications::get_SelectedExternalPartyEntityDisplayName()
0x1842c  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x18431  ldarg.0
0x18432  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x18437  ldstr    aExternalchanne// "_externalChannelEnabledEntities"
0x1843c  ldarg.0
0x1843d  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalChannelEntityNames
0x18442  call     T0x2B000003
0x18447  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVarArray(string varId, class [mscorlib]System.Collections.IEnumerable arrayItems)
0x1844c  ldarg.0
0x1844d  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x18452  ldstr    aExternalpartye_0// "_externalPartyEnabledEntities"
0x18457  ldarg.0
0x18458  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.UI.ExternalApplications::externalPartyEnabledEntityNames
0x1845d  call     T0x2B000003
0x18462  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVarArray(string varId, class [mscorlib]System.Collections.IEnumerable arrayItems)
0x18467  ldarg.0
0x18468  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1846d  ldstr    aRecordassocdes// "_recordAssocDescription"
0x18472  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18477  ldstr    aExternalApplic_1// "External_Applications_RecordAssociation"...
0x1847c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x18481  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x18486  ldarg.0
0x18487  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1848c  ldstr    aParentassocdes// "_parentAssocDescription"
0x18491  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x18496  ldstr    aExternalApplic_2// "External_Applications_ParentAssociation"...
0x1849b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x184a0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x184a5  ldarg.0
0x184a6  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x184ab  ldstr    aRecords// "_records"
0x184b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x184b5  ldstr    aRibbonHomepage// "Ribbon.HomepageGrid.MainTab.Management"
0x184ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x184bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x184c4  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x184c9  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x184ce  ret
```
