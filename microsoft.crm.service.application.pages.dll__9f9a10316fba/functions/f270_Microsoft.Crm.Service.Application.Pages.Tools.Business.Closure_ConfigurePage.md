# Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::ConfigurePage

- ea: `0xf270`
- end: `0xf4cd`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::ConfigurePage`
- size: `605`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xf200`
- `0xf230`
- `0xf240`
- `0xf260`
- `0xf270`

## string_xrefs

- `0xf286`: `/_static/_common/scripts/stage.js`
- `0xf2c6`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0xf2a6`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xf296`: `/_static/_common/scripts/ribbonactions.js`
- `0xf2b6`: `/_static/_common/scripts/Mscrm.Caching.js`

## pseudocode

```c

```

## disassembly

```asm
0xf270  ldarg.0
0xf271  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf276  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0xf27b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf280  ldarg.0
0xf281  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf286  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/stage.js"
0xf28b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf290  ldarg.0
0xf291  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf296  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/ribbonactions."...
0xf29b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf2a0  ldarg.0
0xf2a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf2a6  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/CrmInternalUti"...
0xf2ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf2b0  ldarg.0
0xf2b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf2b6  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/Mscrm.Caching."...
0xf2bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf2c0  ldarg.0
0xf2c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf2c6  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0xf2cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0xf2d0  ldarg.0
0xf2d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf2d6  ldstr    aStaticFormsLoo// "/_static/_forms/lookupbehavior.js"
0xf2db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf2e0  ldarg.0
0xf2e1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmDateNavBar
0xf2e6  ldc.i4.s 0xC
0xf2e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::set_DateIncrement(int32)
0xf2ed  ldarg.0
0xf2ee  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmDateNavBar
0xf2f3  ldarg.0
0xf2f4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2f9  ldstr    aSmPrevYear// "SM_Prev_Year"
0xf2fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf303  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::set_PrevToolTip(string)
0xf308  ldarg.0
0xf309  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmDateNavBar
0xf30e  ldarg.0
0xf30f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf314  ldstr    aSmNextYear// "SM_Next_Year"
0xf319  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf31e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::set_NextToolTip(string)
0xf323  ldarg.0
0xf324  ldarg.0
0xf325  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf32a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf32f  ldstr    aCtype// "cType"
0xf334  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf339  callvirt instance string [mscorlib]System.Object::ToString()
0xf33e  call     instance void Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::set_CalendarType(string value)
0xf343  ldloca.s 0
0xf345  initobj  [mscorlib]System.Guid
0xf34b  ldarg.0
0xf34c  call     instance string Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::get_CalendarType()
0xf351  stloc.1
0xf352  ldloc.1
0xf353  ldstr    aBc// "bc"
0xf358  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf35d  brtrue.s loc_F36E
0xf35f  ldloc.1
0xf360  ldstr    aHs// "hs"
0xf365  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf36a  brtrue.s loc_F38B
0xf36c  br.s     loc_F3CD
0xf36e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf373  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::GetOrgCalendar(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf378  stloc.0
0xf379  ldarg.0
0xf37a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf37f  ldstr    aF751f47d6a6e42// "{F751F47D-6A6E-42d1-9F11-33AA7B42C13A}"
0xf384  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0xf389  br.s     loc_F3CD
0xf38b  ldloca.s 0
0xf38d  ldarg.0
0xf38e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf393  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf398  ldstr    aCalendarid// "calendarId"
0xf39d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf3a2  callvirt instance string [mscorlib]System.Object::ToString()
0xf3a7  call     instance void [mscorlib]System.Guid::.ctor(string)
0xf3ac  ldarg.0
0xf3ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf3b2  ldloc.0
0xf3b3  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::GetHolidayCalendarName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, valuetype [mscorlib]System.Guid)
0xf3b8  call     instance void Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::set_CalendarName(string value)
0xf3bd  ldarg.0
0xf3be  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf3c3  ldstr    a44be8643A33242// "{44BE8643-A332-42E5-B3A3-4184ADB60671}"
0xf3c8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0xf3cd  ldarg.0
0xf3ce  ldloca.s 0
0xf3d0  ldstr    aB// "B"
0xf3d5  call     instance string [mscorlib]System.Guid::ToString(string)
0xf3da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf3df  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xf3e4  call     instance void Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::set_CalendarId(string value)
0xf3e9  ldarg.0
0xf3ea  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf3ef  ldc.i4.0
0xf3f0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0xf3f5  ldarg.0
0xf3f6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf3fb  ldc.i4.1
0xf3fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0xf401  ldarg.0
0xf402  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf407  ldstr    aOid// "oId"
0xf40c  ldarg.0
0xf40d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0xf412  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xf417  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xf41c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xf421  ldarg.0
0xf422  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf427  ldstr    aOtype// "oType"
0xf42c  ldarg.0
0xf42d  ldflda   int32 Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::_otype
0xf432  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf437  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf43c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xf441  ldarg.0
0xf442  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf447  ldstr    aDate// "date"
0xf44c  ldarg.0
0xf44d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppDateNavigationBar Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmDateNavBar
0xf452  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.DateNavigationBar::get_CurrentDisplayDate()
0xf457  call     string [Microsoft.Crm]Microsoft.Crm.CrmCalendarUtil::DateTimeToIsoDateTimeString(valuetype [mscorlib]System.DateTime)
0xf45c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xf461  ldarg.0
0xf462  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf467  ldstr    aHolidaycalenda// "holidayCalendarId"
0xf46c  ldloca.s 0
0xf46e  ldstr    aB// "B"
0xf473  call     instance string [mscorlib]System.Guid::ToString(string)
0xf478  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf47d  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xf482  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xf487  ldarg.0
0xf488  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf48d  ldstr    aCalendartype// "calendarType"
0xf492  ldarg.0
0xf493  call     instance string Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::get_CalendarType()
0xf498  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf49d  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0xf4a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xf4a7  ldarg.0
0xf4a8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf4ad  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.HolidaysGridDataProvider::.ctor()
0xf4b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0xf4b7  ldarg.0
0xf4b8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.Tools.Business.Closure::crmGrid
0xf4bd  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0xf4c2  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0xf4c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0xf4cc  ret
```
