# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::InitDialog

- ea: `0xb260`
- end: `0xb4fd`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::InitDialog`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb0a0`
- `0xb0b0`
- `0xb0c0`
- `0xb260`
- `0xc090`

## string_xrefs

- `0xb3dd`: `Tab_Label_Service_Rules`
- `0xb4aa`: `serviceRestrictionRulesXml`

## pseudocode

```c

```

## disassembly

```asm
0xb260  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0xb265  stloc.s  4
0xb267  ldloca.s 4
0xb269  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xb26e  stloc.1
0xb26f  ldarg.0
0xb270  ldarg.0
0xb271  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb276  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb27b  ldstr    aDay_0// "day"
0xb280  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb285  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::set_Day(string value)
0xb28a  ldarg.0
0xb28b  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::get_Day()
0xb290  brtrue.s loc_B29D
0xb292  ldarg.0
0xb293  ldsfld   string [mscorlib]System.String::Empty
0xb298  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::set_Day(string value)
0xb29d  ldarg.0
0xb29e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::dateControl
0xb2a3  ldstr    aDate// "date"
0xb2a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_DisplayFormat(string)
0xb2ad  ldarg.0
0xb2ae  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb2b3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb2b8  ldstr    aSelecteddates// "selecteddates"
0xb2bd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb2c2  stloc.2
0xb2c3  ldloc.2
0xb2c4  brfalse  loc_B351
0xb2c9  ldloc.2
0xb2ca  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb2cf  ldc.i4.0
0xb2d0  ble.s    loc_B327
0xb2d2  ldloc.2
0xb2d3  ldc.i4.1
0xb2d4  newarr   [mscorlib]System.Char
0xb2d9  dup
0xb2da  ldc.i4.0
0xb2db  ldc.i4.s 0x2C
0xb2dd  stelem.i2
0xb2de  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb2e3  dup
0xb2e4  ldlen
0xb2e5  conv.i4
0xb2e6  newarr   [mscorlib]System.DateTime
0xb2eb  stloc.0
0xb2ec  ldc.i4.0
0xb2ed  stloc.s  5
0xb2ef  stloc.s  6
0xb2f1  ldc.i4.0
0xb2f2  stloc.s  7
0xb2f4  br.s     loc_B31D
0xb2f6  ldloc.s  6
0xb2f8  ldloc.s  7
0xb2fa  ldelem.ref
0xb2fb  stloc.s  8
0xb2fd  ldloc.0
0xb2fe  ldloc.s  5
0xb300  ldloc.s  8
0xb302  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb307  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xb30c  stelem   [mscorlib]System.DateTime
0xb311  ldloc.s  5
0xb313  ldc.i4.1
0xb314  add
0xb315  stloc.s  5
0xb317  ldloc.s  7
0xb319  ldc.i4.1
0xb31a  add
0xb31b  stloc.s  7
0xb31d  ldloc.s  7
0xb31f  ldloc.s  6
0xb321  ldlen
0xb322  conv.i4
0xb323  blt.s    loc_B2F6
0xb325  br.s     loc_B336
0xb327  ldc.i4.1
0xb328  newarr   [mscorlib]System.DateTime
0xb32d  stloc.0
0xb32e  ldloc.0
0xb32f  ldc.i4.0
0xb330  ldloc.1
0xb331  stelem   [mscorlib]System.DateTime
0xb336  ldarg.0
0xb337  ldc.i4.1
0xb338  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::set_ExceptionMode(bool value)
0xb33d  ldarg.0
0xb33e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::dateControl
0xb343  ldloc.0
0xb344  ldc.i4.0
0xb345  ldelem   [mscorlib]System.DateTime
0xb34a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xb34f  br.s     loc_B35D
0xb351  ldarg.0
0xb352  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUI Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::dateControl
0xb357  ldloc.1
0xb358  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.DateTimeUIBase::set_Value(valuetype [mscorlib]System.DateTime)
0xb35d  ldarg.0
0xb35e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb363  ldarg.0
0xb364  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb369  ldstr    aWebSmWorkplans_5// "Web.SM.WorkPlans.Dialogs.workinghours.a"...
0xb36e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb373  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xb378  ldarg.0
0xb379  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xb37e  ldarg.0
0xb37f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb384  ldstr    aTabLabelWorkin// "Tab_Label_Working_Hours"
0xb389  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb38e  ldstr    aTab1// "tab1"
0xb393  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xb398  ldarg.0
0xb399  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xb39e  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xb3a3  stloc.3
0xb3a4  ldarg.0
0xb3a5  ldarg.0
0xb3a6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb3ab  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb3b0  ldstr    aCalendartype// "calendarType"
0xb3b5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb3ba  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::calendarType
0xb3bf  ldarg.0
0xb3c0  ldfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::calendarType
0xb3c5  ldstr    a1// "1"
0xb3ca  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xb3cf  brfalse.s loc_B41F
0xb3d1  ldarg.0
0xb3d2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0xb3d7  ldarg.0
0xb3d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb3dd  ldstr    aTabLabelServic// "Tab_Label_Service_Rules"
0xb3e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb3e7  ldstr    aTab2// "tab2"
0xb3ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0xb3f1  ldloc.3
0xb3f2  ldarg.0
0xb3f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb3f8  ldstr    aWorkingHoursDe// "Working_Hours_Description"
0xb3fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb402  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xb407  ldloc.3
0xb408  ldarg.0
0xb409  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb40e  ldstr    aSmDialogWorkin// "SM_Dialog_Working_Hours"
0xb413  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb418  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xb41d  br.s     loc_B435
0xb41f  ldloc.3
0xb420  ldarg.0
0xb421  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb426  ldstr    aSmSetWorkingHo// "SM_Set_Working_Hours"
0xb42b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb430  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xb435  ldarg.0
0xb436  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xb43b  brfalse.s loc_B471
0xb43d  ldarg.0
0xb43e  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xb443  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb448  ldc.i4.0
0xb449  ble.s    loc_B471
0xb44b  ldarg.0
0xb44c  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xb451  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xb456  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb45b  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb460  stloc.s  9
0xb462  ldarg.0
0xb463  ldloc.s  9
0xb465  callvirt instance string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::RetrieveAllServiceRestrictions()
0xb46a  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::serviceRestrictionsXml
0xb46f  br.s     loc_B47C
0xb471  ldarg.0
0xb472  ldstr    aCalendarrulesM// "<calendarrules morerecords='0'></calend"...
0xb477  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::serviceRestrictionsXml
0xb47c  ldarg.0
0xb47d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb482  ldstr    aA7c07bc4B80f4b// "{A7C07BC4-B80F-4BCA-926B-A11FFF6EA0F2}"
0xb487  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewId(string)
0xb48c  ldarg.0
0xb48d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb492  ldc.i4.0
0xb493  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0xb498  ldarg.0
0xb499  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb49e  ldc.i4.1
0xb49f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_EnablePaging(bool)
0xb4a4  ldarg.0
0xb4a5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb4aa  ldstr    aServicerestric// "serviceRestrictionRulesXml"
0xb4af  ldarg.0
0xb4b0  ldfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::serviceRestrictionsXml
0xb4b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::AddParameter(string, string)
0xb4ba  ldarg.0
0xb4bb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb4c0  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.ServiceRestrictionsGridDataProvider::.ctor()
0xb4c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0xb4ca  ldarg.0
0xb4cb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb4d0  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0xb4d5  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0xb4da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0xb4df  ldarg.0
0xb4e0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGridMenuBar
0xb4e5  ldc.i4.1
0xb4e6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::set_GridType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0xb4eb  ldarg.0
0xb4ec  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGridMenuBar
0xb4f1  ldarg.0
0xb4f2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.Timesheet::crmGrid
0xb4f7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::Execute(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid)
0xb4fc  ret
```
