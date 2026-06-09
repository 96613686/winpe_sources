# Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::ConfigureMenus

- ea: `0xf1fa0`
- end: `0xf239f`
- name: `Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::ConfigureMenus`
- size: `1023`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0xf1e00`
- `0xf1e70`
- `0xf1fa0`

## string_xrefs

- `0xf229d`: `MenuItem_Label_Delete`
- `0xf22ad`: `/_imgs/ico_16_delete.gif`
- `0xf226f`: `frames['MonthCalendar'].Delete('MonthCalendar', LOCID_MONCAL_NONE_SELECTED, `
- `0xf22c1`: `deleteCalendarMenuItem`

## pseudocode

```c

```

## disassembly

```asm
0xf1fa0  ldarg.0
0xf1fa1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf1fa6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf1fab  ldstr    aOtype// "oType"
0xf1fb0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf1fb5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf1fba  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xf1fbf  stloc.0
0xf1fc0  ldloc.0
0xf1fc1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf1fc6  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateCalendar(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf1fcb  brtrue.s loc_F1FDD
0xf1fcd  ldloc.0
0xf1fce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf1fd3  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateOwnCalendar(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf1fd8  brfalse  loc_F222F
0xf1fdd  ldarg.0
0xf1fde  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::crmMenuBar1
0xf1fe3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf1fe8  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0xf1fed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf1ff2  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0xf1ff7  stloc.2
0xf1ff8  ldloc.2
0xf1ff9  ldloc.2
0xf1ffa  ldarg.0
0xf1ffb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2000  ldstr    aMenubarLabelSe// "MenuBar_Label_Set_Up"
0xf2005  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf200a  dup
0xf200b  stloc.s  6
0xf200d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xf2012  ldloc.s  6
0xf2014  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0xf2019  ldloc.2
0xf201a  ldc.i4.1
0xf201b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0xf2020  ldloc.2
0xf2021  ldstr    aNewsetup// "newSetUp"
0xf2026  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xf202b  ldarg.0
0xf202c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2031  ldstr    aMenuitemLabelW_0// "MenuItem_Label_Weekly_Schedule"
0xf2036  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf203b  stloc.1
0xf203c  ldloc.2
0xf203d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xf2042  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf2047  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xf204c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf2051  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xf2056  stloc.3
0xf2057  ldloc.3
0xf2058  ldloc.1
0xf2059  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xf205e  ldloc.3
0xf205f  ldstr    aImgsIco165009G// "/_imgs/ico_16_5009.gif"
0xf2064  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf2069  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf206e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf2073  ldloc.3
0xf2074  ldc.i4.7
0xf2075  newarr   [mscorlib]System.String
0xf207a  dup
0xf207b  ldc.i4.0
0xf207c  ldstr    aMscrmCalendaru// "Mscrm.CalendarUtility.newWorkShift('"
0xf2081  stelem.ref
0xf2082  dup
0xf2083  ldc.i4.1
0xf2084  ldarg.0
0xf2085  call     instance string Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::get_CalendarId()
0xf208a  stelem.ref
0xf208b  dup
0xf208c  ldc.i4.2
0xf208d  ldstr    asc_142CA2// "', '"
0xf2092  stelem.ref
0xf2093  dup
0xf2094  ldc.i4.3
0xf2095  ldarg.0
0xf2096  call     instance string Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::get_OId()
0xf209b  stelem.ref
0xf209c  dup
0xf209d  ldc.i4.4
0xf209e  ldstr    asc_142CA2// "', '"
0xf20a3  stelem.ref
0xf20a4  dup
0xf20a5  ldc.i4.5
0xf20a6  ldloca.s 0
0xf20a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf20ad  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf20b2  stelem.ref
0xf20b3  dup
0xf20b4  ldc.i4.6
0xf20b5  ldstr    asc_142D92// "');"
0xf20ba  stelem.ref
0xf20bb  call     string [mscorlib]System.String::Concat(string[])
0xf20c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xf20c5  ldloc.3
0xf20c6  ldstr    aNewweeklysched// "newWeeklySchedule"
0xf20cb  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xf20d0  ldarg.0
0xf20d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf20d6  ldstr    aMenuitemLabelW_1// "MenuItem_Label_Work_Day"
0xf20db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf20e0  stloc.1
0xf20e1  ldloc.2
0xf20e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xf20e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf20ec  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xf20f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf20f6  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xf20fb  stloc.s  4
0xf20fd  ldloc.s  4
0xf20ff  ldloc.1
0xf2100  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xf2105  ldloc.s  4
0xf2107  ldstr    aImgsIco165008G// "/_imgs/ico_16_5008.gif"
0xf210c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf2111  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf2116  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf211b  ldloc.s  4
0xf211d  ldc.i4.7
0xf211e  newarr   [mscorlib]System.String
0xf2123  dup
0xf2124  ldc.i4.0
0xf2125  ldstr    aMscrmCalendaru_0// "Mscrm.CalendarUtility.newWorkDay('"
0xf212a  stelem.ref
0xf212b  dup
0xf212c  ldc.i4.1
0xf212d  ldarg.0
0xf212e  call     instance string Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::get_CalendarId()
0xf2133  stelem.ref
0xf2134  dup
0xf2135  ldc.i4.2
0xf2136  ldstr    asc_142CA2// "', '"
0xf213b  stelem.ref
0xf213c  dup
0xf213d  ldc.i4.3
0xf213e  ldarg.0
0xf213f  call     instance string Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::get_OId()
0xf2144  stelem.ref
0xf2145  dup
0xf2146  ldc.i4.4
0xf2147  ldstr    asc_142CA2// "', '"
0xf214c  stelem.ref
0xf214d  dup
0xf214e  ldc.i4.5
0xf214f  ldloca.s 0
0xf2151  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf2156  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf215b  stelem.ref
0xf215c  dup
0xf215d  ldc.i4.6
0xf215e  ldstr    asc_142D92// "');"
0xf2163  stelem.ref
0xf2164  call     string [mscorlib]System.String::Concat(string[])
0xf2169  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xf216e  ldloc.s  4
0xf2170  ldstr    aNewworkday// "newWorkDay"
0xf2175  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xf217a  ldarg.0
0xf217b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2180  ldstr    aMenuitemLabelT_1// "MenuItem_Label_Time_Off"
0xf2185  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf218a  stloc.1
0xf218b  ldloc.2
0xf218c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xf2191  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf2196  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xf219b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf21a0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xf21a5  stloc.s  5
0xf21a7  ldloc.s  5
0xf21a9  ldloc.1
0xf21aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xf21af  ldloc.s  5
0xf21b1  ldstr    aImgsIco165004G// "/_imgs/ico_16_5004.gif"
0xf21b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf21bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf21c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf21c5  ldloc.s  5
0xf21c7  ldc.i4.7
0xf21c8  newarr   [mscorlib]System.String
0xf21cd  dup
0xf21ce  ldc.i4.0
0xf21cf  ldstr    aMscrmCalendaru_1// "Mscrm.CalendarUtility.newTimeOff('"
0xf21d4  stelem.ref
0xf21d5  dup
0xf21d6  ldc.i4.1
0xf21d7  ldarg.0
0xf21d8  call     instance string Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::get_CalendarId()
0xf21dd  stelem.ref
0xf21de  dup
0xf21df  ldc.i4.2
0xf21e0  ldstr    asc_142CA2// "', '"
0xf21e5  stelem.ref
0xf21e6  dup
0xf21e7  ldc.i4.3
0xf21e8  ldarg.0
0xf21e9  call     instance string Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::get_OId()
0xf21ee  stelem.ref
0xf21ef  dup
0xf21f0  ldc.i4.4
0xf21f1  ldstr    asc_142CA2// "', '"
0xf21f6  stelem.ref
0xf21f7  dup
0xf21f8  ldc.i4.5
0xf21f9  ldloca.s 0
0xf21fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf2200  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf2205  stelem.ref
0xf2206  dup
0xf2207  ldc.i4.6
0xf2208  ldstr    asc_142D92// "');"
0xf220d  stelem.ref
0xf220e  call     string [mscorlib]System.String::Concat(string[])
0xf2213  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xf2218  ldloc.s  5
0xf221a  ldstr    aNewtimeoff// "newTimeOff"
0xf221f  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xf2224  ldarg.0
0xf2225  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::crmMenuBar1
0xf222a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xf222f  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteCalendar()
0xf2234  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf2239  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf223e  brtrue.s loc_F2254
0xf2240  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteOwnCalendar()
0xf2245  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf224a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf224f  brfalse  loc_F22D6
0xf2254  ldarg.0
0xf2255  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::crmMenuBar1
0xf225a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf225f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xf2264  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf2269  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xf226e  dup
0xf226f  ldstr    aFramesMonthcal// "frames['MonthCalendar'].Delete('MonthCa"...
0xf2274  ldc.i4   0xFA4
0xf2279  stloc.s  7
0xf227b  ldloca.s 7
0xf227d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf2282  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf2287  ldstr    asc_12EE04// ");"
0xf228c  call     string [mscorlib]System.String::Concat(string, string, string)
0xf2291  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xf2296  dup
0xf2297  ldarg.0
0xf2298  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf229d  ldstr    aMenuitemLabelD_0// "MenuItem_Label_Delete"
0xf22a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf22a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0xf22ac  dup
0xf22ad  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0xf22b2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf22b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf22bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf22c1  ldstr    aDeletecalendar// "deleteCalendarMenuItem"
0xf22c6  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xf22cb  ldarg.0
0xf22cc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::crmMenuBar1
0xf22d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0xf22d6  ldloc.0
0xf22d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf22dc  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateCalendar(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf22e1  brtrue.s loc_F22F3
0xf22e3  ldloc.0
0xf22e4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf22e9  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateOwnCalendar(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf22ee  brfalse  loc_F239E
0xf22f3  ldarg.0
0xf22f4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Pages.Business.Users.MonthlyCalendar::crmMenuBar1
0xf22f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf22fe  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0xf2303  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf2308  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0xf230d  dup
0xf230e  ldarg.0
0xf230f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2314  ldstr    aMenuLabelMorea// "Menu_Label_MoreActions"
0xf2319  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf231e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xf2323  dup
0xf2324  ldstr    aActions// "actions"
0xf2329  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xf232e  dup
0xf232f  ldc.i4.1
0xf2330  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0xf2335  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xf233a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xf233f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xf2344  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xf2349  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0xf234e  dup
0xf234f  ldarg.0
0xf2350  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf2355  ldstr    aMenuitemLabelE_0// "MenuItem_Label_Edit"
0xf235a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf235f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
  ... truncated ...
```
