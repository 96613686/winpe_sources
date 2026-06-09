# Microsoft.Crm.Application.Controls.CrmFolderView::ConfigureHeader

- ea: `0xa1f40`
- end: `0xa212b`
- name: `Microsoft.Crm.Application.Controls.CrmFolderView::ConfigureHeader`
- size: `491`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa1ef0`
- `0xa1f40`

## string_xrefs

- `0xa1f67`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xa1f81`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xa1f9b`: `/_static/_common/scripts/jquery.hotkeys.js`
- `0xa1fb5`: `/_static/_common/scripts/jquery.jstree.js`

## pseudocode

```c

```

## disassembly

```asm
0xa1f40  ldarg.0
0xa1f41  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0xa1f46  ldarg.0
0xa1f47  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xa1f4c  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl
0xa1f51  stloc.0
0xa1f52  ldloc.0
0xa1f53  brfalse.s loc_A1F61
0xa1f55  ldarg.0
0xa1f56  ldloc.0
0xa1f57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0xa1f5c  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_EventManager(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager)
0xa1f61  ldarg.0
0xa1f62  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa1f67  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/jquery_ui_1.8."...
0xa1f6c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa1f71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1f76  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa1f7b  ldarg.0
0xa1f7c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa1f81  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/CrmInternalUti"...
0xa1f86  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa1f8b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1f90  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa1f95  ldarg.0
0xa1f96  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa1f9b  ldstr    aStaticCommonSc_27// "/_static/_common/scripts/jquery.hotkeys"...
0xa1fa0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa1fa5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1faa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa1faf  ldarg.0
0xa1fb0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa1fb5  ldstr    aStaticCommonSc_28// "/_static/_common/scripts/jquery.jstree."...
0xa1fba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa1fbf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1fc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa1fc9  ldarg.0
0xa1fca  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa1fcf  ldstr    aStaticControls_29// "/_static/_controls/TreeViewControl/Tree"...
0xa1fd4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa1fd9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa1fde  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa1fe3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xa1fe8  stloc.1
0xa1fe9  ldloc.1
0xa1fea  ldstr    aCrmhierarchyda// "crmHierarchyDataManager"
0xa1fef  ldstr    aCrmhierarchyda// "crmHierarchyDataManager"
0xa1ff4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa1ff9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xa1ffe  stloc.2
0xa1fff  ldloc.2
0xa2000  ldstr    aHeronodeid_0// "HeroNodeId"
0xa2005  ldarg.0
0xa2006  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Controls.CrmFolderView::get_HeroNodeId()
0xa200b  stloc.3
0xa200c  ldloca.s 3
0xa200e  constrained. [mscorlib]System.Guid
0xa2014  callvirt instance string [mscorlib]System.Object::ToString()
0xa2019  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xa201e  ldarg.0
0xa201f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa2024  ldstr    aFolderviewDril// "FOLDERVIEW_DRILLDOWN_ALT_TEXT_AND_TITLE"
0xa2029  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa202e  ldstr    aDrilldownAltTe// "DrillDown_Alt_Text_And_Title"
0xa2033  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa2038  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa203d  ldarg.0
0xa203e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa2043  ldstr    aFolderviewHome// "FOLDERVIEW_HOME_ALT_TEXT_AND_TITLE"
0xa2048  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa204d  ldstr    aHomeAltTextAnd// "Home_Alt_Text_And_Title"
0xa2052  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa2057  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa205c  ldarg.0
0xa205d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa2062  ldstr    aFolderviewUpAl// "FOLDERVIEW_UP_ALT_TEXT_AND_TITLE"
0xa2067  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa206c  ldstr    aUpAltTextAndTi// "Up_Alt_Text_And_Title"
0xa2071  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa2076  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa207b  ldarg.0
0xa207c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa2081  ldstr    aFolderviewShow// "FOLDERVIEW_SHOWMORE_TOOLTIP"
0xa2086  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa208b  ldstr    aShowmoreToolti// "ShowMore_ToolTip"
0xa2090  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa2095  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa209a  ldarg.0
0xa209b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa20a0  ldstr    aFolderviewShow_0// "FOLDERVIEW_SHOWMORE"
0xa20a5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa20aa  ldstr    aFolderviewShow_1// "FolderView_ShowMore"
0xa20af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa20b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa20b9  ldarg.0
0xa20ba  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa20bf  ldstr    aFolderviewLoad// "FOLDERVIEW_LOADINGTEXT"
0xa20c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa20c9  ldstr    aFolderviewLoad_0// "FolderView_LoadingText"
0xa20ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa20d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa20d8  ldarg.0
0xa20d9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa20de  ldstr    aFolderviewExpa// "FOLDERVIEW_EXPAND_ANNOUNCEMENT"
0xa20e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa20e8  ldstr    aFolderviewExpa_0// "FolderView_Expand_Announcement"
0xa20ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa20f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa20f7  ldarg.0
0xa20f8  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xa20fd  ldstr    aFolderviewColl// "FOLDERVIEW_COLLAPSE_ANNOUNCEMENT"
0xa2102  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa2107  ldstr    aFolderviewColl_0// "FolderView_Collapse_Announcement"
0xa210c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa2111  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xa2116  ldarg.0
0xa2117  ldstr    aMscrmCrmfolder// "Mscrm.CrmFolderView"
0xa211c  ldloc.2
0xa211d  ldnull
0xa211e  ldloc.1
0xa211f  ldarg.0
0xa2120  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa2125  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0xa212a  ret
```
