# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::ConfigurePage

- ea: `0x3db0`
- end: `0x3ee2`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::ConfigurePage`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x3db6`: `/_static/_common/scripts/stage.js`
- `0x3dd1`: `Web._common.scripts.stage.js_30`
- `0x3df2`: `Web._common.scripts.stage.js_17`
- `0x3e08`: `LOCID_SEARCH_LIST_NOT_OPEN`
- `0x3e13`: `Web._common.scripts.stage.js_35`

## pseudocode

```c

```

## disassembly

```asm
0x3db0  ldarg.0
0x3db1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3db6  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/stage.js"
0x3dbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3dc0  ldarg.0
0x3dc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3dc6  ldstr    aLocidSearchRes// "LOCID_SEARCH_RESULTS"
0x3dcb  ldarg.0
0x3dcc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3dd1  ldstr    aWebCommonScrip// "Web._common.scripts.stage.js_30"
0x3dd6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3ddb  ldc.i4.0
0x3ddc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3de1  ldarg.0
0x3de2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3de7  ldstr    aLocidSearchAle// "LOCID_SEARCH_ALERT_NO_CRITERIA"
0x3dec  ldarg.0
0x3ded  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3df2  ldstr    aWebCommonScrip_0// "Web._common.scripts.stage.js_17"
0x3df7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3dfc  ldc.i4.0
0x3dfd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3e02  ldarg.0
0x3e03  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3e08  ldstr    aLocidSearchLis// "LOCID_SEARCH_LIST_NOT_OPEN"
0x3e0d  ldarg.0
0x3e0e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3e13  ldstr    aWebCommonScrip_1// "Web._common.scripts.stage.js_35"
0x3e18  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3e1d  ldc.i4.0
0x3e1e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3e23  ldarg.0
0x3e24  ldstr    aBulkoperation// "bulkoperation"
0x3e29  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3e2e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3e33  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3e38  ldarg.0
0x3e39  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid_SavedQuerySelector
0x3e3e  ldstr    aHandleminicamp// "handleMiniCampView(this)"
0x3e43  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector::set_OnChange(string)
0x3e48  ldarg.0
0x3e49  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid_SavedQuerySelector
0x3e4e  ldstr    aBulkoperation// "bulkoperation"
0x3e53  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3e58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3e5d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector::set_ReturnedEntityType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3e62  ldarg.0
0x3e63  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid_SavedQuerySelector
0x3e68  ldstr    aFd4df17c386e4e// "{FD4DF17C-386E-4e29-9D31-529A568A3BBC}"
0x3e6d  ldc.i4   0x40F
0x3e72  ldstr    asc_8C46// ""
0x3e77  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector::AddSingleView(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType, string)
0x3e7c  ldarg.0
0x3e7d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid_SavedQuerySelector
0x3e82  ldstr    aBa8257771a7b48// "{BA825777-1A7B-4837-8778-B86904D1115C}"
0x3e87  ldc.i4   0x40F
0x3e8c  ldstr    asc_8C46// ""
0x3e91  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector::AddSingleView(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType, string)
0x3e96  ldarg.0
0x3e97  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid_SavedQuerySelector
0x3e9c  ldstr    a2c9e85433e3b4f// "{2C9E8543-3E3B-4f8d-AEDF-B8A43446619D}"
0x3ea1  ldc.i4   0x40F
0x3ea6  ldstr    asc_8C46// ""
0x3eab  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector::AddSingleQuickFindView(string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType, string)
0x3eb0  ldarg.0
0x3eb1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid
0x3eb6  ldarg.0
0x3eb7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid_SavedQuerySelector
0x3ebc  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Controls.ViewSelector::get_DefaultSavedQuery()
0x3ec1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0x3ec6  ldarg.0
0x3ec7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3ecc  ldstr    aCurrentviewid// "_currentViewId"
0x3ed1  ldarg.0
0x3ed2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid
0x3ed7  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewId()
0x3edc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x3ee1  ret
```
