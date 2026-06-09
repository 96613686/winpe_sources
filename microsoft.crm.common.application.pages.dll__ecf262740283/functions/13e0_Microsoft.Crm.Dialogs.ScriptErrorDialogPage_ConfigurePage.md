# Microsoft.Crm.Dialogs.ScriptErrorDialogPage::ConfigurePage

- ea: `0x13e0`
- end: `0x15fe`
- name: `Microsoft.Crm.Dialogs.ScriptErrorDialogPage::ConfigurePage`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13e0`

## string_xrefs

- `0x1507`: `Web__common_error_scriptError_aspx_Title`
- `0x1549`: `Web__common_error_scriptError_aspx_BtnSendReport`
- `0x1577`: `Web__common_error_scriptError_aspx_BtnSendReport`
- `0x15ad`: `Web__common_error_scriptError_aspx_BtnSendReport`
- `0x155f`: `Web__common_error_scriptError_aspx_BtnDoNotSendReport`
- `0x1592`: `Web__common_error_scriptError_aspx_BtnDoNotSendReport`
- `0x15c8`: `Web__common_error_scriptError_aspx_BtnDoNotSendReport`

## pseudocode

```c

```

## disassembly

```asm
0x13e0  ldarg.0
0x13e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13e6  ldstr    aOrglanguage// "OrgLanguage"
0x13eb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x13f0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x13f5  conv.i8
0x13f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x13fb  ldarg.0
0x13fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1401  ldstr    aOrgculture// "OrgCulture"
0x1406  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x140b  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrgCultureInfo()
0x1410  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1415  conv.i8
0x1416  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x141b  ldarg.0
0x141c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1421  ldstr    aUserlanguage// "UserLanguage"
0x1426  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x142b  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1430  conv.i8
0x1431  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x1436  ldarg.0
0x1437  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x143c  ldstr    aUserculture// "UserCulture"
0x1441  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1446  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x144b  conv.i8
0x144c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x1451  ldarg.0
0x1452  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1457  ldstr    aOrgid// "OrgID"
0x145c  ldarg.0
0x145d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x1462  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x1467  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x146c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1471  ldarg.0
0x1472  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1477  ldstr    aOrgname// "OrgName"
0x147c  ldarg.0
0x147d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x1482  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_BusinessName()
0x1487  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x148c  ldarg.0
0x148d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1492  ldstr    aUserid// "UserID"
0x1497  ldarg.0
0x1498  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x149d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x14a2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x14a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x14ac  ldarg.0
0x14ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14b2  ldstr    aCrmversion// "CRMVersion"
0x14b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x14bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_FullVersion()
0x14c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x14c6  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x14cb  brfalse.s loc_1500
0x14cd  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x14d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_ActivityId()
0x14d7  pop
0x14d8  ldarg.0
0x14d9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14de  ldstr    aActivityid// "ActivityId"
0x14e3  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x14e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_ActivityId()
0x14ed  stloc.2
0x14ee  ldloca.s 2
0x14f0  constrained. [mscorlib]System.Guid
0x14f6  callvirt instance string [mscorlib]System.Object::ToString()
0x14fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1500  ldarg.0
0x1501  ldarg.0
0x1502  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1507  ldstr    aWebCommonError// "Web__common_error_scriptError_aspx_Titl"...
0x150c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1511  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x1516  ldarg.0
0x1517  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x151c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ScriptErrorReportingPreference()
0x1521  ldc.i4.0
0x1522  ceq
0x1524  stfld    bool Microsoft.Crm.Dialogs.ScriptErrorDialogPage::showChangeErrorNotification
0x1529  ldarg.0
0x152a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Dialogs.ScriptErrorDialogPage::ErrorImage
0x152f  ldstr    aImgsErrorNotif// "/_imgs/error/notif_icn_warn.png"
0x1534  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x1539  ldarg.0
0x153a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x153f  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x1544  ldstr    aBtnsendreport// "btnSendReport"
0x1549  ldstr    aWebCommonError_0// "Web__common_error_scriptError_aspx_BtnS"...
0x154e  ldstr    aReportallerror// "ReportAllErrors(); closeWindow();"
0x1553  ldc.i4.0
0x1554  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x1559  stloc.0
0x155a  ldstr    aBtndonotsendre// "btnDoNotSendReport"
0x155f  ldstr    aWebCommonError_1// "Web__common_error_scriptError_aspx_BtnD"...
0x1564  ldstr    aClosewindow// "closeWindow();"
0x1569  ldc.i4.0
0x156a  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0x156f  stloc.1
0x1570  ldloc.0
0x1571  ldarg.0
0x1572  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1577  ldstr    aWebCommonError_0// "Web__common_error_scriptError_aspx_BtnS"...
0x157c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1581  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x1586  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x158b  ldloc.1
0x158c  ldarg.0
0x158d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1592  ldstr    aWebCommonError_1// "Web__common_error_scriptError_aspx_BtnD"...
0x1597  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x159c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x15a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x15a6  ldloc.0
0x15a7  ldarg.0
0x15a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15ad  ldstr    aWebCommonError_0// "Web__common_error_scriptError_aspx_BtnS"...
0x15b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15b7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x15bc  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x15c1  ldloc.1
0x15c2  ldarg.0
0x15c3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15c8  ldstr    aWebCommonError_1// "Web__common_error_scriptError_aspx_BtnD"...
0x15cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15d2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x15d7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x15dc  ldarg.0
0x15dd  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x15e2  ldloc.0
0x15e3  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x15e8  pop
0x15e9  ldarg.0
0x15ea  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x15ef  ldloc.1
0x15f0  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0x15f5  pop
0x15f6  ldarg.0
0x15f7  ldc.i4.0
0x15f8  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_ShowHeader(bool)
0x15fd  ret
```
