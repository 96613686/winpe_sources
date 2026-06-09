# Microsoft.Crm.Web.Tools.Views.ICDashboardEditorPage::ConfigureHeader

- ea: `0x7d6b0`
- end: `0x7d97a`
- name: `Microsoft.Crm.Web.Tools.Views.ICDashboardEditorPage::ConfigureHeader`
- size: `714`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7d6b0`

## string_xrefs

- `0x7d805`: `DashboardWebService`
- `0x7d841`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x7d871`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x7d6fe`: `LOCID_NETBREEZE_NO_CONFIG`
- `0x7d709`: `NetBreeze.Runtime.ConfigureControl`
- `0x7d74b`: `NetBreeze.Runtime.Dashboard.NoInstanceConfigured`
- `0x7d76c`: `ConfigureSocialInsightsWizard.MslSignInPage.SignInRequired`
- `0x7d815`: `SocialInsightsWebService`
- `0x7d851`: `/_static/_common/scripts/salescrmsoapproxyservice.js`

## pseudocode

```c

```

## disassembly

```asm
0x7d6b0  ldarg.0
0x7d6b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::ConfigureHeader()
0x7d6b6  ldarg.0
0x7d6b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d6bc  ldstr    aLocidMissingNa// "LOCID_MISSING_NAME"
0x7d6c1  ldarg.0
0x7d6c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d6c7  ldstr    aWebDashboarded_0// "Web.DashboardEditor.MissingName"
0x7d6cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6d1  ldc.i4.0
0x7d6d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d6d7  ldarg.0
0x7d6d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d6dd  ldstr    aLocidEditorwin// "LOCID_EDITORWINDOW_NAME"
0x7d6e2  ldarg.0
0x7d6e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d6e8  ldstr    aWebDashboarded_1// "Web.DashboardEditorWindow.Edit"
0x7d6ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6f2  ldc.i4.0
0x7d6f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d6f8  ldarg.0
0x7d6f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d6fe  ldstr    aLocidNetbreeze// "LOCID_NETBREEZE_NO_CONFIG"
0x7d703  ldarg.0
0x7d704  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d709  ldstr    aNetbreezeRunti// "NetBreeze.Runtime.ConfigureControl"
0x7d70e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d713  ldc.i4.0
0x7d714  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d719  ldarg.0
0x7d71a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d71f  ldstr    aLocidNetbreeze_0// "LOCID_NETBREEZE_CONNECTION_ERROR"
0x7d724  ldarg.0
0x7d725  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d72a  ldstr    aErrorMessage0x_24// "Error_Message_0x80060001"
0x7d72f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d734  ldc.i4.0
0x7d735  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d73a  ldarg.0
0x7d73b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d740  ldstr    aLocidNetbreeze_1// "LOCID_NETBREEZE_NO_INSTANCE"
0x7d745  ldarg.0
0x7d746  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d74b  ldstr    aNetbreezeRunti_0// "NetBreeze.Runtime.Dashboard.NoInstanceC"...
0x7d750  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d755  ldc.i4.0
0x7d756  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d75b  ldarg.0
0x7d75c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d761  ldstr    aLocidNetbreeze_2// "LOCID_NETBREEZE_SIGN_IN"
0x7d766  ldarg.0
0x7d767  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d76c  ldstr    aConfiguresocia// "ConfigureSocialInsightsWizard.MslSignIn"...
0x7d771  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d776  ldc.i4.0
0x7d777  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d77c  ldarg.0
0x7d77d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d782  ldstr    aLocidNetbreeze_3// "LOCID_NETBREEZE_DISABLED"
0x7d787  ldarg.0
0x7d788  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d78d  ldstr    aNetbreezeRunti_1// "NetBreeze.Runtime.SocialInsightsDisable"...
0x7d792  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d797  ldc.i4.0
0x7d798  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d79d  ldarg.0
0x7d79e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d7a3  ldstr    aLocidFilterbyN// "LOCID_FILTERBY_NOT_SELECTED"
0x7d7a8  ldarg.0
0x7d7a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d7ae  ldstr    aWebDashboarded_31// "Web.DashboardEditor.FilterByNotSelected"
0x7d7b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d7b8  ldc.i4.0
0x7d7b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7be  ldarg.0
0x7d7bf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d7c4  ldstr    aLocidInconsist// "LOCID_INCONSISTENT_STREAM"
0x7d7c9  ldarg.0
0x7d7ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d7cf  ldstr    aStreamInconsis// "Stream_Inconsistent_Error"
0x7d7d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d7d9  ldc.i4.0
0x7d7da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7df  ldarg.0
0x7d7e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d7e5  ldstr    aToolsDashboard_2// "/tools/dashboardeditor/dashboardeditor."...
0x7d7ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7d7ef  ldarg.0
0x7d7f0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d7f5  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0x7d7fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7d7ff  ldarg.0
0x7d800  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d805  ldstr    aDashboardwebse// "DashboardWebService"
0x7d80a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x7d80f  ldarg.0
0x7d810  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d815  ldstr    aSocialinsights// "SocialInsightsWebService"
0x7d81a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x7d81f  ldarg.0
0x7d820  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d825  ldstr    aStaticToolsDas// "/_static/tools/DashboardEditor/scripts/"...
0x7d82a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7d82f  ldarg.0
0x7d830  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d835  ldc.i4.1
0x7d836  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x7d83b  ldarg.0
0x7d83c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d841  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0x7d846  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7d84b  ldarg.0
0x7d84c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d851  ldstr    aStaticCommonSc_35// "/_static/_common/scripts/salescrmsoappr"...
0x7d856  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7d85b  ldarg.0
0x7d85c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d861  ldstr    aStaticControls_26// "/_static/_controls/SocialInsights/Socia"...
0x7d866  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7d86b  ldarg.0
0x7d86c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d871  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0x7d876  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7d87b  ldarg.0
0x7d87c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7d881  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7d886  ldstr    aEntitytypecode// "entitytypecode"
0x7d88b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d890  brfalse.s loc_7D8B7
0x7d892  ldarg.0
0x7d893  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d898  ldstr    aEntityTypeCode// "ENTITY_TYPE_CODE"
0x7d89d  ldarg.0
0x7d89e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7d8a3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7d8a8  ldstr    aEntitytypecode// "entitytypecode"
0x7d8ad  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d8b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d8b7  ldarg.0
0x7d8b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d8bd  ldstr    aPublicQueues// "Public_Queues"
0x7d8c2  ldarg.0
0x7d8c3  ldfld    string Microsoft.Crm.Web.Tools.Views.ICDashboardEditorPage::publicQueuesUniqueId
0x7d8c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d8cd  ldarg.0
0x7d8ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d8d3  ldstr    aPrivateQueues// "Private_Queues"
0x7d8d8  ldarg.0
0x7d8d9  ldfld    string Microsoft.Crm.Web.Tools.Views.ICDashboardEditorPage::privateQueuesUniqueId
0x7d8de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d8e3  ldarg.0
0x7d8e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d8e9  ldstr    aAllQueues// "All_Queues"
0x7d8ee  ldarg.0
0x7d8ef  ldfld    string Microsoft.Crm.Web.Tools.Views.ICDashboardEditorPage::uniqueIdForAllQueues
0x7d8f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d8f9  ldarg.0
0x7d8fa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d8ff  ldstr    aPublicQueuesNa// "Public_Queues_Name"
0x7d904  ldarg.0
0x7d905  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d90a  ldstr    aWorkplaceQueue// "Workplace_Queue_Selector_Public"
0x7d90f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d914  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d919  ldarg.0
0x7d91a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d91f  ldstr    aPrivateQueuesN// "Private_Queues_Name"
0x7d924  ldarg.0
0x7d925  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d92a  ldstr    aWorkplaceQueue_0// "Workplace_Queue_Selector_Private"
0x7d92f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d934  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d939  ldarg.0
0x7d93a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d93f  ldstr    aAllQueuesName// "All_Queues_Name"
0x7d944  ldarg.0
0x7d945  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d94a  ldstr    aWorkplaceQueue_1// "Workplace_Queue_Selector_All"
0x7d94f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d954  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d959  ldarg.0
0x7d95a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7d95f  ldstr    aLocidIcSelectS// "LOCID_IC_SELECT_STREAM"
0x7d964  ldarg.0
0x7d965  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7d96a  ldstr    aIcDashboardSel// "IC_Dashboard_Select_Stream"
0x7d96f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d974  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7d979  ret
```
