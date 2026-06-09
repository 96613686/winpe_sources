# Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigurePreviewsTab

- ea: `0x918b0`
- end: `0x91e06`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ConfigurePreviewsTab`
- size: `1366`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x90ec0`

## callees

- `0x918b0`
- `0x91e10`

## string_xrefs

- `0x91d42`: `http://go.microsoft.com/fwlink/p/?LinkId=723110`
- `0x919d6`: `taskbasedflowenabled`
- `0x9194a`: `productrecommendationsenabled`
- `0x9191c`: `SystemCustomization.SystemSettingsDialog.PreviewTab.TaskBasedFlowPreview.Enable`
- `0x919ef`: `SystemCustomization.SystemSettingsDialog.PreviewTab.TaskBasedFlowPreview.Enable`
- `0x9192c`: `SystemCustomization.SystemSettingsDialog.PreviewTab.TaskBasedFlowPreview.Disable`
- `0x919ff`: `SystemCustomization.SystemSettingsDialog.PreviewTab.TaskBasedFlowPreview.Disable`
- `0x91bb7`: `<a id='CortanaProactiveExperiencePreviewHelpLink' class='default-link' target='_blank' href='`
- `0x91bbc`: `http://go.microsoft.com/fwlink/p/?LinkId=691455`
- `0x91bee`: `SystemCustomization.SystemSettingsDialog.PreviewTab.Note.ProductRecommendationsPreview`
- `0x91c05`: `<a id='CRMProductRecommendationsPreviewHelpLink' class='default-link' target='_blank' href='`
- `0x91c0a`: `http://go.microsoft.com/fwlink/p/?LinkID=746141`
- `0x91c3c`: `SystemCustomization.SystemSettingsDialog.PreviewTab.Note.TaskBasedFlowPreview`
- `0x91c53`: `<a id='CRMTaskBasedFlowPreviewHelpLink' class='default-link' target='_blank' href='`
- `0x91c58`: `http://go.microsoft.com/fwlink/p/?LinkId=624316`
- `0x91ca1`: `<a id='CRMRelationshipAnalyticsPreviewText' class='default-link' target='_blank' href='`
- `0x91ca6`: `https://go.microsoft.com/fwlink/?linkid=869888`
- `0x91cef`: `<a id='CRMLeadScoringPreviewText' class='default-link' target='_blank' href='`
- `0x91cf4`: `https://go.microsoft.com/fwlink/p/?linkid=870069`
- `0x91d3d`: `<a id='CRMOrgInsightsPreviewHelpLink' class='default-link' target='_blank' href='`
- `0x91d8b`: `<a id='CRMTextAnalyticsPreviewHelpLink' class='default-link' target='_blank' href='`
- `0x91d90`: `http://go.microsoft.com/fwlink/p/?LinkID=746138`
- `0x91dc2`: `SystemCustomization.SystemSettingsDialog.PreviewTab.Preview.EULALink`
- `0x91dd9`: `<a id='PreviewEULALinkUrl' class='default-link' target='_blank' href='`
- `0x91dde`: `http://go.microsoft.com/fwlink/?LinkId=511446`

## pseudocode

```c

```

## disassembly

```asm
0x918b0  ldarg.0
0x918b1  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsCortanaProactiveExperienceFeatureEnabled
0x918b6  brfalse.s loc_918F6
0x918b8  ldarg.0
0x918b9  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x918be  ldstr    aCortanaproacti// "cortanaproactiveexperienceenabled"
0x918c3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x918c8  stloc.0
0x918c9  ldarg.0
0x918ca  ldarg.0
0x918cb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdCortanaProactiveExperiencePreview
0x918d0  ldarg.0
0x918d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x918d6  ldstr    aSystemcustomiz_121// "SystemCustomization.SystemSettingsDialo"...
0x918db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x918e0  ldarg.0
0x918e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x918e6  ldstr    aSystemcustomiz_122// "SystemCustomization.SystemSettingsDialo"...
0x918eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x918f0  ldloc.0
0x918f1  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x918f6  ldarg.0
0x918f7  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsOrgInsightsFeatureEnabled
0x918fc  brfalse.s loc_9193C
0x918fe  ldarg.0
0x918ff  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x91904  ldstr    aOrginsightsena// "orginsightsenabled"
0x91909  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x9190e  stloc.1
0x9190f  ldarg.0
0x91910  ldarg.0
0x91911  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdorgInsightsPreview
0x91916  ldarg.0
0x91917  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9191c  ldstr    aSystemcustomiz_123// "SystemCustomization.SystemSettingsDialo"...
0x91921  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91926  ldarg.0
0x91927  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9192c  ldstr    aSystemcustomiz_124// "SystemCustomization.SystemSettingsDialo"...
0x91931  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91936  ldloc.1
0x91937  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x9193c  ldarg.0
0x9193d  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsProductRecommendationsFeatureAvailable
0x91942  brfalse.s loc_91982
0x91944  ldarg.0
0x91945  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x9194a  ldstr    aProductrecomme// "productrecommendationsenabled"
0x9194f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x91954  stloc.2
0x91955  ldarg.0
0x91956  ldarg.0
0x91957  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdProductRecommendationsPreview
0x9195c  ldarg.0
0x9195d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91962  ldstr    aSystemcustomiz_125// "SystemCustomization.SystemSettingsDialo"...
0x91967  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9196c  ldarg.0
0x9196d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91972  ldstr    aSystemcustomiz_126// "SystemCustomization.SystemSettingsDialo"...
0x91977  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9197c  ldloc.2
0x9197d  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x91982  ldarg.0
0x91983  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ShouldShowActionSupportItem
0x91988  brfalse.s loc_919C8
0x9198a  ldarg.0
0x9198b  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x91990  ldstr    aIsactionsuppor_0// "isactionsupportfeatureenabled"
0x91995  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x9199a  stloc.3
0x9199b  ldarg.0
0x9199c  ldarg.0
0x9199d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdActionSupportFeaturePreview
0x919a2  ldarg.0
0x919a3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x919a8  ldstr    aSystemcustomiz_127// "SystemCustomization.SystemSettingsDialo"...
0x919ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x919b2  ldarg.0
0x919b3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x919b8  ldstr    aSystemcustomiz_128// "SystemCustomization.SystemSettingsDialo"...
0x919bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x919c2  ldloc.3
0x919c3  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x919c8  ldarg.0
0x919c9  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ShouldShowTaskBasedFlowItem
0x919ce  brfalse.s loc_91A10
0x919d0  ldarg.0
0x919d1  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x919d6  ldstr    aTaskbasedflowe// "taskbasedflowenabled"
0x919db  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x919e0  stloc.s  4
0x919e2  ldarg.0
0x919e3  ldarg.0
0x919e4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdTaskBasedFlowPreview
0x919e9  ldarg.0
0x919ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x919ef  ldstr    aSystemcustomiz_123// "SystemCustomization.SystemSettingsDialo"...
0x919f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x919f9  ldarg.0
0x919fa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x919ff  ldstr    aSystemcustomiz_124// "SystemCustomization.SystemSettingsDialo"...
0x91a04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91a09  ldloc.s  4
0x91a0b  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x91a10  ldarg.0
0x91a11  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsTextAnalyticsFeatureAvailable
0x91a16  brfalse.s loc_91A58
0x91a18  ldarg.0
0x91a19  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x91a1e  ldstr    aTextanalyticse// "textanalyticsenabled"
0x91a23  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x91a28  stloc.s  5
0x91a2a  ldarg.0
0x91a2b  ldarg.0
0x91a2c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdTextAnalyticsPreview
0x91a31  ldarg.0
0x91a32  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91a37  ldstr    aSystemcustomiz_125// "SystemCustomization.SystemSettingsDialo"...
0x91a3c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91a41  ldarg.0
0x91a42  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91a47  ldstr    aSystemcustomiz_126// "SystemCustomization.SystemSettingsDialo"...
0x91a4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91a51  ldloc.s  5
0x91a53  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x91a58  ldarg.0
0x91a59  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsSyncFeatureEnabled
0x91a5e  brfalse  loc_91AF8
0x91a63  ldarg.0
0x91a64  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x91a69  ldstr    aSyncoptinselec// "syncoptinselection"
0x91a6e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x91a73  stloc.s  6
0x91a75  ldarg.0
0x91a76  ldarg.0
0x91a77  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdSyncOptInSelection
0x91a7c  ldarg.0
0x91a7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91a82  ldstr    aSystemcustomiz_125// "SystemCustomization.SystemSettingsDialo"...
0x91a87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91a8c  ldarg.0
0x91a8d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91a92  ldstr    aSystemcustomiz_126// "SystemCustomization.SystemSettingsDialo"...
0x91a97  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91a9c  ldloc.s  6
0x91a9e  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::InitializeFeatureRadio(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio featureRadio, string enabledOption, string disabledOption, bool isFeatureEnabled)
0x91aa3  ldarg.0
0x91aa4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::syncOptInSelectionStatus
0x91aa9  ldc.i4.1
0x91aaa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x91aaf  ldarg.0
0x91ab0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::syncOptInSelectionStatus
0x91ab5  ldarg.0
0x91ab6  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x91abb  ldstr    aSyncoptinselec_0// "syncoptinselectionstatus"
0x91ac0  ldstr    aName// "name"
0x91ac5  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAttrValue(string, string, string)
0x91aca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x91acf  ldarg.0
0x91ad0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdSyncOptInSelection
0x91ad5  ldarg.0
0x91ad6  ldfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::_OrgXml
0x91adb  ldstr    aSyncoptinselec// "syncoptinselection"
0x91ae0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x91ae5  brtrue.s loc_91AEE
0x91ae7  ldstr    a0_1// "0"
0x91aec  br.s     loc_91AF3
0x91aee  ldstr    a1// "1"
0x91af3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio::set_Value(string)
0x91af8  ldarg.0
0x91af9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::cbPreviewEULA
0x91afe  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::get_Checked()
0x91b03  brfalse.s loc_91B6A
0x91b05  ldc.i4.7
0x91b06  newarr   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio
0x91b0b  dup
0x91b0c  ldc.i4.0
0x91b0d  ldarg.0
0x91b0e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdCortanaProactiveExperiencePreview
0x91b13  stelem.ref
0x91b14  dup
0x91b15  ldc.i4.1
0x91b16  ldarg.0
0x91b17  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdorgInsightsPreview
0x91b1c  stelem.ref
0x91b1d  dup
0x91b1e  ldc.i4.2
0x91b1f  ldarg.0
0x91b20  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdProductRecommendationsPreview
0x91b25  stelem.ref
0x91b26  dup
0x91b27  ldc.i4.3
0x91b28  ldarg.0
0x91b29  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdTaskBasedFlowPreview
0x91b2e  stelem.ref
0x91b2f  dup
0x91b30  ldc.i4.4
0x91b31  ldarg.0
0x91b32  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdActionSupportFeaturePreview
0x91b37  stelem.ref
0x91b38  dup
0x91b39  ldc.i4.5
0x91b3a  ldarg.0
0x91b3b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdTextAnalyticsPreview
0x91b40  stelem.ref
0x91b41  dup
0x91b42  ldc.i4.6
0x91b43  ldarg.0
0x91b44  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdSyncOptInSelection
0x91b49  stelem.ref
0x91b4a  stloc.s  7
0x91b4c  ldc.i4.0
0x91b4d  stloc.s  8
0x91b4f  br.s     loc_91B62
0x91b51  ldloc.s  7
0x91b53  ldloc.s  8
0x91b55  ldelem.ref
0x91b56  ldc.i4.0
0x91b57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x91b5c  ldloc.s  8
0x91b5e  ldc.i4.1
0x91b5f  add
0x91b60  stloc.s  8
0x91b62  ldloc.s  8
0x91b64  ldloc.s  7
0x91b66  ldlen
0x91b67  conv.i4
0x91b68  blt.s    loc_91B51
0x91b6a  ldarg.0
0x91b6b  ldfld    bool Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::IsSyncFeatureEnabled
0x91b70  brfalse.s loc_91B95
0x91b72  ldarg.0
0x91b73  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::syncOptInSelectionStatus
0x91b78  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::get_Text()
0x91b7d  ldstr    aProcessing// "Processing"
0x91b82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91b87  brfalse.s loc_91B95
0x91b89  ldarg.0
0x91b8a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::rdSyncOptInSelection
0x91b8f  ldc.i4.1
0x91b90  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x91b95  ldarg.0
0x91b96  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91b9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x91ba0  ldstr    aCortanaCrmFeat// "Cortana.CRM.Feature.Help"
0x91ba5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91baa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x91baf  ldc.i4.2
0x91bb0  newarr   [mscorlib]System.Object
0x91bb5  dup
0x91bb6  ldc.i4.0
0x91bb7  ldstr    aAIdCortanaproa// "<a id='CortanaProactiveExperiencePrevie"...
0x91bbc  ldstr    aHttpGoMicrosof_8// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x91bc1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x91bc6  ldstr    asc_144456// "'>"
0x91bcb  call     string [mscorlib]System.String::Concat(string, string, string)
0x91bd0  stelem.ref
0x91bd1  dup
0x91bd2  ldc.i4.1
0x91bd3  ldstr    aA// "</a>"
0x91bd8  stelem.ref
0x91bd9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x91bde  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::CortanaProactiveExperiencePreviewHelpLink
0x91be3  ldarg.0
0x91be4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91be9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x91bee  ldstr    aSystemcustomiz_129// "SystemCustomization.SystemSettingsDialo"...
0x91bf3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91bf8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x91bfd  ldc.i4.2
0x91bfe  newarr   [mscorlib]System.Object
0x91c03  dup
0x91c04  ldc.i4.0
0x91c05  ldstr    aAIdCrmproductr// "<a id='CRMProductRecommendationsPreview"...
0x91c0a  ldstr    aHttpGoMicrosof_9// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x91c0f  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x91c14  ldstr    asc_144456// "'>"
0x91c19  call     string [mscorlib]System.String::Concat(string, string, string)
0x91c1e  stelem.ref
0x91c1f  dup
0x91c20  ldc.i4.1
0x91c21  ldstr    aA// "</a>"
0x91c26  stelem.ref
0x91c27  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x91c2c  stfld    string Microsoft.Crm.Web.Tools.SystemSettings.SystemSettingsPage::ProductRecommendationsPreviewHelpLink
0x91c31  ldarg.0
0x91c32  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91c37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x91c3c  ldstr    aSystemcustomiz_130// "SystemCustomization.SystemSettingsDialo"...
0x91c41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91c46  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x91c4b  ldc.i4.2
0x91c4c  newarr   [mscorlib]System.Object
0x91c51  dup
0x91c52  ldc.i4.0
0x91c53  ldstr    aAIdCrmtaskbase// "<a id='CRMTaskBasedFlowPreviewHelpLink'"...
0x91c58  ldstr    aHttpGoMicrosof_10// "http://go.microsoft.com/fwlink/p/?LinkI"...
0x91c5d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::AppendUserUILanguageClcid(string)
0x91c62  ldstr    asc_144456// "'>"
  ... truncated ...
```
