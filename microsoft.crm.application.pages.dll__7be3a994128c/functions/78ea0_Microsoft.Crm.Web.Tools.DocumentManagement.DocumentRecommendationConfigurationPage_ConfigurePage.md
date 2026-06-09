# Microsoft.Crm.Web.Tools.DocumentManagement.DocumentRecommendationConfigurationPage::ConfigurePage

- ea: `0x78ea0`
- end: `0x78fef`
- name: `Microsoft.Crm.Web.Tools.DocumentManagement.DocumentRecommendationConfigurationPage::ConfigurePage`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x78ea0`
- `0x78ff0`

## string_xrefs

- `0x78ed0`: `LOCID_UPDATEFAILURE_TEXT`
- `0x78edb`: `Web.Tools.DocumentRecommendation.SettingsPage.UpdateFailureText`
- `0x78efc`: `Web.Tools.DocumentRecommendation.SettingsPage.SuccessText`
- `0x78f1d`: `Web.Tools.DocumentRecommendation.SettingsPage.FooterText`
- `0x78f3e`: `Web.Tools.DocumentRecommendation.SettingsPage.CheckAll.Tooltip`
- `0x78f5f`: `Web.Tools.DocumentRecommendation.Config.ApplyButton`
- `0x78f80`: `Web.Tools.DocumentRecommendation.SettingsPage.ExternalSuggestions.LabelText`

## pseudocode

```c

```

## disassembly

```asm
0x78ea0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78ea5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x78eaa  ldc.i4.0
0x78eab  ldc.i4.0
0x78eac  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x78eb1  stloc.1
0x78eb2  ldarg.0
0x78eb3  ldloc.1
0x78eb4  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.DocumentRecommendationUtil::IsDocumentRecommendationsEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x78eb9  stfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.DocumentRecommendationConfigurationPage::IsDocumentRecommendationsEnabled
0x78ebe  leave.s  loc_78ECA
0x78ec0  ldloc.1
0x78ec1  brfalse.s loc_78EC9
0x78ec3  ldloc.1
0x78ec4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x78ec9  endfinally
0x78eca  ldarg.0
0x78ecb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78ed0  ldstr    aLocidUpdatefai// "LOCID_UPDATEFAILURE_TEXT"
0x78ed5  ldarg.0
0x78ed6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x78edb  ldstr    aWebToolsDocume_17// "Web.Tools.DocumentRecommendation.Settin"...
0x78ee0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x78ee5  ldc.i4.0
0x78ee6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x78eeb  ldarg.0
0x78eec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78ef1  ldstr    aLocidSuccessTe// "LOCID_SUCCESS_TEXT"
0x78ef6  ldarg.0
0x78ef7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x78efc  ldstr    aWebToolsDocume_18// "Web.Tools.DocumentRecommendation.Settin"...
0x78f01  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x78f06  ldc.i4.0
0x78f07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x78f0c  ldarg.0
0x78f0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78f12  ldstr    aLocidUnsavedTe// "LOCID_UNSAVED_TEXT"
0x78f17  ldarg.0
0x78f18  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x78f1d  ldstr    aWebToolsDocume_19// "Web.Tools.DocumentRecommendation.Settin"...
0x78f22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x78f27  ldc.i4.0
0x78f28  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x78f2d  ldarg.0
0x78f2e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78f33  ldstr    aLocidCheckallt// "LOCID_CHECKALLTOOLTIP_TEXT"
0x78f38  ldarg.0
0x78f39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x78f3e  ldstr    aWebToolsDocume_20// "Web.Tools.DocumentRecommendation.Settin"...
0x78f43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x78f48  ldc.i4.0
0x78f49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x78f4e  ldarg.0
0x78f4f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78f54  ldstr    aLocidApplybott// "LOCID_APPLYBOTTONTOOLTIP"
0x78f59  ldarg.0
0x78f5a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x78f5f  ldstr    aWebToolsDocume_21// "Web.Tools.DocumentRecommendation.Config"...
0x78f64  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x78f69  ldc.i4.0
0x78f6a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x78f6f  ldarg.0
0x78f70  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78f75  ldstr    aLocidExternalb// "LOCID_EXTERNALBASEURLTLTIP_TXT"
0x78f7a  ldarg.0
0x78f7b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x78f80  ldstr    aWebToolsDocume_22// "Web.Tools.DocumentRecommendation.Settin"...
0x78f85  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x78f8a  ldc.i4.0
0x78f8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x78f90  ldarg.0
0x78f91  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::ConfigurePage()
0x78f96  ldarg.0
0x78f97  ldfld    bool Microsoft.Crm.Web.Tools.DocumentManagement.DocumentRecommendationConfigurationPage::IsDocumentRecommendationsEnabled
0x78f9c  brfalse.s loc_78FA4
0x78f9e  ldarg.0
0x78f9f  call     instance void Microsoft.Crm.Web.Tools.DocumentManagement.DocumentRecommendationConfigurationPage::FillTable()
0x78fa4  ldarg.0
0x78fa5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x78faa  ldstr    aEntityCount// "ENTITY_COUNT"
0x78faf  ldc.i4.0
0x78fb0  conv.i8
0x78fb1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x78fb6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x78fbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78fc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x78fc5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78fca  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x78fcf  stloc.0
0x78fd0  ldloc.0
0x78fd1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ExternalBaseUrl()
0x78fd6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x78fdb  brtrue.s loc_78FEE
0x78fdd  ldarg.0
0x78fde  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.DocumentManagement.DocumentRecommendationConfigurationPage::txtExternalBaseUrl
0x78fe3  ldloc.0
0x78fe4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ExternalBaseUrl()
0x78fe9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x78fee  ret
```
