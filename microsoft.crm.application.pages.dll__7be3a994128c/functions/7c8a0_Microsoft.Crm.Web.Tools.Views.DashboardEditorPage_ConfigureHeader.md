# Microsoft.Crm.Web.Tools.Views.DashboardEditorPage::ConfigureHeader

- ea: `0x7c8a0`
- end: `0x7cb06`
- name: `Microsoft.Crm.Web.Tools.Views.DashboardEditorPage::ConfigureHeader`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7c850`
- `0x7c8a0`

## string_xrefs

- `0x7ca8f`: `DashboardWebService`
- `0x7cacb`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x7cafb`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x7c8ee`: `LOCID_NETBREEZE_NO_CONFIG`
- `0x7c8f9`: `NetBreeze.Runtime.ConfigureControl`
- `0x7c93b`: `NetBreeze.Runtime.Dashboard.NoInstanceConfigured`
- `0x7c95c`: `ConfigureSocialInsightsWizard.MslSignInPage.SignInRequired`
- `0x7ca9f`: `SocialInsightsWebService`
- `0x7cadb`: `/_static/_common/scripts/salescrmsoapproxyservice.js`

## pseudocode

```c

```

## disassembly

```asm
0x7c8a0  ldarg.0
0x7c8a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::ConfigureHeader()
0x7c8a6  ldarg.0
0x7c8a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c8ac  ldstr    aLocidMissingNa// "LOCID_MISSING_NAME"
0x7c8b1  ldarg.0
0x7c8b2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c8b7  ldstr    aWebDashboarded_0// "Web.DashboardEditor.MissingName"
0x7c8bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c8c1  ldc.i4.0
0x7c8c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c8c7  ldarg.0
0x7c8c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c8cd  ldstr    aLocidEditorwin// "LOCID_EDITORWINDOW_NAME"
0x7c8d2  ldarg.0
0x7c8d3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c8d8  ldstr    aWebDashboarded_1// "Web.DashboardEditorWindow.Edit"
0x7c8dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c8e2  ldc.i4.0
0x7c8e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c8e8  ldarg.0
0x7c8e9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c8ee  ldstr    aLocidNetbreeze// "LOCID_NETBREEZE_NO_CONFIG"
0x7c8f3  ldarg.0
0x7c8f4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c8f9  ldstr    aNetbreezeRunti// "NetBreeze.Runtime.ConfigureControl"
0x7c8fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c903  ldc.i4.0
0x7c904  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c909  ldarg.0
0x7c90a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c90f  ldstr    aLocidNetbreeze_0// "LOCID_NETBREEZE_CONNECTION_ERROR"
0x7c914  ldarg.0
0x7c915  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c91a  ldstr    aErrorMessage0x_24// "Error_Message_0x80060001"
0x7c91f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c924  ldc.i4.0
0x7c925  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c92a  ldarg.0
0x7c92b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c930  ldstr    aLocidNetbreeze_1// "LOCID_NETBREEZE_NO_INSTANCE"
0x7c935  ldarg.0
0x7c936  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c93b  ldstr    aNetbreezeRunti_0// "NetBreeze.Runtime.Dashboard.NoInstanceC"...
0x7c940  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c945  ldc.i4.0
0x7c946  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c94b  ldarg.0
0x7c94c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c951  ldstr    aLocidNetbreeze_2// "LOCID_NETBREEZE_SIGN_IN"
0x7c956  ldarg.0
0x7c957  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c95c  ldstr    aConfiguresocia// "ConfigureSocialInsightsWizard.MslSignIn"...
0x7c961  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c966  ldc.i4.0
0x7c967  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c96c  ldarg.0
0x7c96d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c972  ldstr    aLocidNetbreeze_3// "LOCID_NETBREEZE_DISABLED"
0x7c977  ldarg.0
0x7c978  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c97d  ldstr    aNetbreezeRunti_1// "NetBreeze.Runtime.SocialInsightsDisable"...
0x7c982  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c987  ldc.i4.0
0x7c988  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c98d  ldarg.0
0x7c98e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c993  ldstr    aLocidDelveTitl// "LOCID_DELVE_TITLE"
0x7c998  ldarg.0
0x7c999  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7c99e  ldstr    aWebDashboarded_2// "Web.DashboardEditor.DelveTitle"
0x7c9a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7c9a8  ldc.i4.0
0x7c9a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c9ae  ldarg.0
0x7c9af  call     instance bool Microsoft.Crm.Web.Tools.Views.DashboardEditorPage::get_SupportPowerBITile()
0x7c9b4  brfalse  loc_7CA69
0x7c9b9  ldarg.0
0x7c9ba  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c9bf  ldstr    aLocidPowerbiti// "LOCID_POWERBITILE_FIRSTPARTYURL"
0x7c9c4  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_FirstPartyIntegrationUrl()
0x7c9c9  ldc.i4.0
0x7c9ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7c9cf  leave.s  loc_7C9FB
0x7c9d1  stloc.0
0x7c9d2  ldnull
0x7c9d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7c9d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7c9dd  ldc.i4.0
0x7c9de  ldstr    aUnableToRetrie// "Unable to retrieve FirstPartyIntegratio"...
0x7c9e3  ldloc.0
0x7c9e4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7c9e9  call     string [mscorlib]System.String::Concat(string, string)
0x7c9ee  ldc.i4.0
0x7c9ef  newarr   [mscorlib]System.Object
0x7c9f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7c9f9  leave.s  loc_7C9FB
0x7c9fb  ldarg.0
0x7c9fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca01  ldstr    aLocidLoginLabe// "LOCID_LOGIN_LABEL"
0x7ca06  ldarg.0
0x7ca07  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ca0c  ldstr    aPowerbitileLog// "PowerBITile_LoginButton_Label"
0x7ca11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ca16  ldc.i4.0
0x7ca17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7ca1c  ldarg.0
0x7ca1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca22  ldstr    aLocidTextDirec// "LOCID_TEXT_DIRECTION"
0x7ca27  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TextDirection()
0x7ca2c  ldc.i4.0
0x7ca2d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7ca32  ldarg.0
0x7ca33  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca38  ldstr    aLocidLoginText// "LOCID_LOGIN_TEXT"
0x7ca3d  ldarg.0
0x7ca3e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ca43  ldstr    aPowerbitileAut// "PowerBITile_AuthError_Label"
0x7ca48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ca4d  ldc.i4.0
0x7ca4e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7ca53  ldarg.0
0x7ca54  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca59  ldstr    aLocidPowerbiEn// "LOCID_POWERBI_ENV"
0x7ca5e  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_EnvironmentType()
0x7ca63  ldc.i4.0
0x7ca64  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7ca69  ldarg.0
0x7ca6a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca6f  ldstr    aToolsDashboard_2// "/tools/dashboardeditor/dashboardeditor."...
0x7ca74  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7ca79  ldarg.0
0x7ca7a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca7f  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0x7ca84  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7ca89  ldarg.0
0x7ca8a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca8f  ldstr    aDashboardwebse// "DashboardWebService"
0x7ca94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x7ca99  ldarg.0
0x7ca9a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ca9f  ldstr    aSocialinsights// "SocialInsightsWebService"
0x7caa4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x7caa9  ldarg.0
0x7caaa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7caaf  ldstr    aStaticToolsDas// "/_static/tools/DashboardEditor/scripts/"...
0x7cab4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7cab9  ldarg.0
0x7caba  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7cabf  ldc.i4.1
0x7cac0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x7cac5  ldarg.0
0x7cac6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7cacb  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0x7cad0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7cad5  ldarg.0
0x7cad6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7cadb  ldstr    aStaticCommonSc_35// "/_static/_common/scripts/salescrmsoappr"...
0x7cae0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7cae5  ldarg.0
0x7cae6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7caeb  ldstr    aStaticControls_26// "/_static/_controls/SocialInsights/Socia"...
0x7caf0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7caf5  ldarg.0
0x7caf6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7cafb  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0x7cb00  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7cb05  ret
```
