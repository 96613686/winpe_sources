# Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::ConfigureMenus

- ea: `0xaadf0`
- end: `0xab125`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::ConfigureMenus`
- size: `821`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0xaadf0`
- `0xab360`

## string_xrefs

- `0xaaf65`: `/_imgs/ico_16_delete.gif`
- `0xaae2e`: `openObj({0}, '', 'baseentity={1}');`
- `0xaaead`: `btnCreateSimilarityRule`
- `0xaaeea`: `Mscrm.SimilaritySettingsGrid.editExistingRuleFromGridCommand();`
- `0xaaf4b`: `Mscrm.SimilaritySettingsGrid.deleteRuleFromGridCommand();`
- `0xaaf70`: `MenuBar.Button.Delete.ToolTip`
- `0xaaf7a`: `btnDeleteSimilarityRule`
- `0xaafba`: `Mscrm.SimilaritySettingsGrid.activateFromGridCommand();`
- `0xab01a`: `Mscrm.SimilaritySettingsGrid.deactivateFromGridCommand();`
- `0xab07a`: `Mscrm.SimilaritySettingsGrid.showDependenciesFromGridCommand();`
- `0xab0da`: `Mscrm.SimilaritySettingsGrid.showManagedPropertiesFromGridCommand();`

## pseudocode

```c

```

## disassembly

```asm
0xaadf0  ldarg.0
0xaadf1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaadf6  brtrue.s loc_AADF9
0xaadf8  ret
0xaadf9  ldarg.0
0xaadfa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaadff  ldnull
0xaae00  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0xaae05  ldarg.0
0xaae06  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaae0b  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0xaae10  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0xaae15  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateSimilarityRule()
0xaae1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaae1f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaae24  brfalse  loc_AAEC3
0xaae29  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaae2e  ldstr    aOpenobj0Baseen// "openObj({0}, '', 'baseentity={1}');"
0xaae33  ldc.i4.2
0xaae34  newarr   [mscorlib]System.Object
0xaae39  dup
0xaae3a  ldc.i4.0
0xaae3b  ldc.i4   0x26DF
0xaae40  box      [mscorlib]System.Int32
0xaae45  stelem.ref
0xaae46  dup
0xaae47  ldc.i4.1
0xaae48  ldarg.0
0xaae49  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::_entityMD
0xaae4e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xaae53  stloc.1
0xaae54  ldloca.s 1
0xaae56  ldstr    aD// "D"
0xaae5b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaae60  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xaae65  stelem.ref
0xaae66  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaae6b  stloc.0
0xaae6c  ldarg.0
0xaae6d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaae72  ldarg.0
0xaae73  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaae78  ldstr    aButtonLabelNew// "Button_Label_New"
0xaae7d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaae82  ldloc.0
0xaae83  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaae88  ldc.i4.1
0xaae89  newarr   [mscorlib]System.Char
0xaae8e  dup
0xaae8f  ldc.i4.0
0xaae90  ldc.i4.s 0x2F
0xaae92  stelem.i2
0xaae93  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaae98  ldstr    aImgsRibbonSimi// "/_imgs/ribbon/similaritysettings.png"
0xaae9d  call     string [mscorlib]System.String::Concat(string, string)
0xaaea2  ldarg.0
0xaaea3  ldstr    aMenubarButtonN// "MenuBar.Button.New.ToolTip"
0xaaea8  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::GetString(string name)
0xaaead  ldstr    aBtncreatesimil// "btnCreateSimilarityRule"
0xaaeb2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xaaeb7  pop
0xaaeb8  ldarg.0
0xaaeb9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaaebe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaaec3  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteSimilarityRule()
0xaaec8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaaecd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaaed2  brfalse.s loc_AAF2F
0xaaed4  ldarg.0
0xaaed5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaaeda  ldarg.0
0xaaedb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaaee0  ldstr    aMenuitemLabelE_0// "MenuItem_Label_Edit"
0xaaee5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaaeea  ldstr    aMscrmSimilarit// "Mscrm.SimilaritySettingsGrid.editExisti"...
0xaaeef  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaaef4  ldc.i4.1
0xaaef5  newarr   [mscorlib]System.Char
0xaaefa  dup
0xaaefb  ldc.i4.0
0xaaefc  ldc.i4.s 0x2F
0xaaefe  stelem.i2
0xaaeff  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaaf04  ldstr    aImgsGridEditru// "/_imgs/grid/editrule_16.png"
0xaaf09  call     string [mscorlib]System.String::Concat(string, string)
0xaaf0e  ldarg.0
0xaaf0f  ldstr    aMenubarButtonE// "MenuBar.Button.Edit.ToolTip"
0xaaf14  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::GetString(string name)
0xaaf19  ldstr    aBtneditsimilar// "btnEditSimilarityRule"
0xaaf1e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xaaf23  pop
0xaaf24  ldarg.0
0xaaf25  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaaf2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaaf2f  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteSimilarityRule()
0xaaf34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaaf39  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaaf3e  brfalse.s loc_AAF90
0xaaf40  ldarg.0
0xaaf41  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaaf46  ldstr    asc_11EF2A// ""
0xaaf4b  ldstr    aMscrmSimilarit_0// "Mscrm.SimilaritySettingsGrid.deleteRule"...
0xaaf50  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaaf55  ldc.i4.1
0xaaf56  newarr   [mscorlib]System.Char
0xaaf5b  dup
0xaaf5c  ldc.i4.0
0xaaf5d  ldc.i4.s 0x2F
0xaaf5f  stelem.i2
0xaaf60  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaaf65  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xaaf6a  call     string [mscorlib]System.String::Concat(string, string)
0xaaf6f  ldarg.0
0xaaf70  ldstr    aMenubarButtonD// "MenuBar.Button.Delete.ToolTip"
0xaaf75  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::GetString(string name)
0xaaf7a  ldstr    aBtndeletesimil// "btnDeleteSimilarityRule"
0xaaf7f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xaaf84  pop
0xaaf85  ldarg.0
0xaaf86  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaaf8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xaaf90  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteSimilarityRule()
0xaaf95  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaaf9a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaaf9f  brfalse  loc_AB064
0xaafa4  ldarg.0
0xaafa5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaafaa  ldarg.0
0xaafab  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaafb0  ldstr    aSystemcustomiz_415// "SystemCustomization.SimilarityRulesList"...
0xaafb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaafba  ldstr    aMscrmSimilarit_1// "Mscrm.SimilaritySettingsGrid.activateFr"...
0xaafbf  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xaafc4  ldc.i4.1
0xaafc5  newarr   [mscorlib]System.Char
0xaafca  dup
0xaafcb  ldc.i4.0
0xaafcc  ldc.i4.s 0x2F
0xaafce  stelem.i2
0xaafcf  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xaafd4  ldstr    aImgsRibbonActi_0// "/_imgs/ribbon/activate_16.png"
0xaafd9  call     string [mscorlib]System.String::Concat(string, string)
0xaafde  ldarg.0
0xaafdf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaafe4  ldstr    aSystemcustomiz_416// "SystemCustomization.SimilarityRulesList"...
0xaafe9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaafee  ldstr    aBtnactivatesim// "btnActivateSimilarityrule"
0xaaff3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xaaff8  pop
0xaaff9  ldarg.0
0xaaffa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xaafff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xab004  ldarg.0
0xab005  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xab00a  ldarg.0
0xab00b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab010  ldstr    aSystemcustomiz_417// "SystemCustomization.SimilarityRulesList"...
0xab015  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab01a  ldstr    aMscrmSimilarit_2// "Mscrm.SimilaritySettingsGrid.deactivate"...
0xab01f  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xab024  ldc.i4.1
0xab025  newarr   [mscorlib]System.Char
0xab02a  dup
0xab02b  ldc.i4.0
0xab02c  ldc.i4.s 0x2F
0xab02e  stelem.i2
0xab02f  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xab034  ldstr    aImgsRibbonDeac_0// "/_imgs/ribbon/deactivate_16.png"
0xab039  call     string [mscorlib]System.String::Concat(string, string)
0xab03e  ldarg.0
0xab03f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab044  ldstr    aSystemcustomiz_418// "SystemCustomization.SimilarityRulesList"...
0xab049  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab04e  ldstr    aBtndeactivates// "btnDeactivateSimilarityrule"
0xab053  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xab058  pop
0xab059  ldarg.0
0xab05a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xab05f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xab064  ldarg.0
0xab065  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xab06a  ldarg.0
0xab06b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab070  ldstr    aMenuitemLabelS_2// "MenuItem_Label_ShowDependency"
0xab075  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab07a  ldstr    aMscrmSimilarit_3// "Mscrm.SimilaritySettingsGrid.showDepend"...
0xab07f  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xab084  ldc.i4.1
0xab085  newarr   [mscorlib]System.Char
0xab08a  dup
0xab08b  ldc.i4.0
0xab08c  ldc.i4.s 0x2F
0xab08e  stelem.i2
0xab08f  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xab094  ldstr    aImgsSolutionSh// "/_imgs/solution/show_dependency.png"
0xab099  call     string [mscorlib]System.String::Concat(string, string)
0xab09e  ldarg.0
0xab09f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab0a4  ldstr    aMenuitemLabelS_2// "MenuItem_Label_ShowDependency"
0xab0a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab0ae  ldstr    aBtnshowdepende// "btnShowDependencies"
0xab0b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xab0b8  pop
0xab0b9  ldarg.0
0xab0ba  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xab0bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xab0c4  ldarg.0
0xab0c5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xab0ca  ldarg.0
0xab0cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab0d0  ldstr    aMenuitemLabelM// "MenuItem_Label_ManagedProperties"
0xab0d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab0da  ldstr    aMscrmSimilarit_4// "Mscrm.SimilaritySettingsGrid.showManage"...
0xab0df  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xab0e4  ldc.i4.1
0xab0e5  newarr   [mscorlib]System.Char
0xab0ea  dup
0xab0eb  ldc.i4.0
0xab0ec  ldc.i4.s 0x2F
0xab0ee  stelem.i2
0xab0ef  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xab0f4  ldstr    aImgsSolutionPo// "/_imgs/solution/poperties_16.png"
0xab0f9  call     string [mscorlib]System.String::Concat(string, string)
0xab0fe  ldarg.0
0xab0ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xab104  ldstr    aMenuitemLabelM// "MenuItem_Label_ManagedProperties"
0xab109  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab10e  ldstr    aBtnshowmanaged// "btnShowManagedProperties"
0xab113  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0xab118  pop
0xab119  ldarg.0
0xab11a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Web.Tools.SystemCustomization.SimilarityRules.SimilarityRulesListPage::menuBar
0xab11f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xab124  ret
```
