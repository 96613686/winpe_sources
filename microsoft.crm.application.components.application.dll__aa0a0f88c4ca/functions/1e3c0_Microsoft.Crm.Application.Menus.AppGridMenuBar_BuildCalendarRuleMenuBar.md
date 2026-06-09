# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildCalendarRuleMenuBar

- ea: `0x1e3c0`
- end: `0x1e7d9`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildCalendarRuleMenuBar`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x1a490`
- `0x1a510`
- `0x1a590`
- `0x1ae30`
- `0x1c010`
- `0x1e3c0`
- `0x24210`
- `0x242a0`

## string_xrefs

- `0x1e444`: `DeleteServiceRestrictions(`
- `0x1e4eb`: `openStdDlg(Mscrm.CrmUri.create(`
- `0x1e55f`: `Calendar_Rule_Service_Restriction`
- `0x1e56a`: `/SM/workplans/Dialogs/serviceavailability.aspx`
- `0x1e5da`: `OpenServiceAvailabilityDialog(`
- `0x1e600`: `openServiceAvailabilityButton`

## pseudocode

```c

```

## disassembly

```asm
0x1e3c0  ldsfld   string [mscorlib]System.String::Empty
0x1e3c5  stloc.0
0x1e3c6  ldarg.0
0x1e3c7  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridViewId
0x1e3cc  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1e3d1  stloc.1
0x1e3d2  ldarg.0
0x1e3d3  call     instance int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityType()
0x1e3d8  stloc.2
0x1e3d9  ldloc.2
0x1e3da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e3df  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateCalendar(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e3e4  brtrue.s loc_1E3F6
0x1e3e6  ldloc.2
0x1e3e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e3ec  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateOwnCalendar(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e3f1  brfalse  loc_1E65F
0x1e3f6  ldloc.1
0x1e3f7  ldstr    aF751f47d6a6e42// "{F751F47D-6A6E-42D1-9F11-33AA7B42C13A}"
0x1e3fc  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1e401  brfalse  loc_1E65F
0x1e406  ldloc.1
0x1e407  ldstr    a44be8643A33242// "{44BE8643-A332-42E5-B3A3-4184ADB60671}"
0x1e40c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1e411  brfalse  loc_1E65F
0x1e416  ldarg.0
0x1e417  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1e41c  ldc.i4   0x10000
0x1e421  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e426  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e42b  brfalse.s loc_1E463
0x1e42d  ldarg.0
0x1e42e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton()
0x1e433  stloc.s  4
0x1e435  ldloc.1
0x1e436  ldstr    aA7c07bc4B80f4b// "{A7C07BC4-B80F-4BCA-926B-A11FFF6EA0F2}"
0x1e43b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e440  brfalse.s loc_1E463
0x1e442  ldloc.s  4
0x1e444  ldstr    aDeleteservicer// "DeleteServiceRestrictions("
0x1e449  ldarg.0
0x1e44a  ldfld    string Microsoft.Crm.Application.Menus.AppGridMenuBar::_gridClientId
0x1e44f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1e454  ldstr    asc_11632C// ");"
0x1e459  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e45e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl::set_Action(string)
0x1e463  ldloc.1
0x1e464  ldstr    a1fb3033e6b8142// "{1FB3033E-6B81-4297-AFD6-DF5262372ADC}"
0x1e469  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e46e  brtrue.s loc_1E485
0x1e470  ldloc.1
0x1e471  ldstr    aA7c07bc4B80f4b// "{A7C07BC4-B80F-4BCA-926B-A11FFF6EA0F2}"
0x1e476  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e47b  brtrue   loc_1E559
0x1e480  br       loc_1E653
0x1e485  ldarg.0
0x1e486  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e48b  ldstr    aCalendarRuleBr// "Calendar_Rule_Break"
0x1e490  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e495  stloc.0
0x1e496  ldstr    aSmWorkplansDia// "/SM/workplans/Dialogs/break.aspx"
0x1e49b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e4a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e4a5  stloc.s  5
0x1e4a7  ldloc.s  5
0x1e4a9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1e4ae  ldstr    aCalendarid// "calendarid"
0x1e4b3  ldarg.0
0x1e4b4  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetParentEntityId()
0x1e4b9  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1e4be  ldarg.0
0x1e4bf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e4c4  ldc.i4.1
0x1e4c5  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1e4ca  ldarg.0
0x1e4cb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e4d0  ldarg.0
0x1e4d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e4d6  ldstr    aMenuitemLabelN// "MenuItem_Label_New"
0x1e4db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e4e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1e4e5  ldarg.0
0x1e4e6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e4eb  ldstr    aOpenstddlgMscr// "openStdDlg(Mscrm.CrmUri.create("
0x1e4f0  ldloc.s  5
0x1e4f2  callvirt instance string [mscorlib]System.Object::ToString()
0x1e4f7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1e4fc  ldstr    aWindow550340// "), window, 550, 340);"
0x1e501  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e506  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1e50b  ldarg.0
0x1e50c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e511  ldstr    aImgsIco165002G// "/_imgs/ico_16_5002.gif"
0x1e516  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e51b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e520  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1e525  ldarg.0
0x1e526  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e52b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e530  ldarg.0
0x1e531  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e536  ldstr    aMenuitemToolti_0// "MenuItem_ToolTip_NewObject"
0x1e53b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e540  ldc.i4.1
0x1e541  newarr   [mscorlib]System.Object
0x1e546  dup
0x1e547  ldc.i4.0
0x1e548  ldloc.0
0x1e549  stelem.ref
0x1e54a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e54f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1e554  br       loc_1E653
0x1e559  ldarg.0
0x1e55a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e55f  ldstr    aCalendarRuleSe// "Calendar_Rule_Service_Restriction"
0x1e564  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e569  stloc.0
0x1e56a  ldstr    aSmWorkplansDia_0// "/SM/workplans/Dialogs/serviceavailabili"...
0x1e56f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e574  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e579  stloc.s  6
0x1e57b  ldloc.s  6
0x1e57d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1e582  ldstr    aId_1// "id"
0x1e587  ldsfld   string [mscorlib]System.String::Empty
0x1e58c  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1e591  ldloc.s  6
0x1e593  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1e598  ldstr    aCalendarid// "calendarid"
0x1e59d  ldarg.0
0x1e59e  ldstr    aId_0// "Id"
0x1e5a3  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::GetObjectIdFromQueryString(string name)
0x1e5a8  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1e5ad  ldarg.0
0x1e5ae  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e5b3  ldc.i4.1
0x1e5b4  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1e5b9  ldarg.0
0x1e5ba  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e5bf  ldarg.0
0x1e5c0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e5c5  ldstr    aMenuitemLabelN// "MenuItem_Label_New"
0x1e5ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e5cf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1e5d4  ldarg.0
0x1e5d5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e5da  ldstr    aOpenserviceava// "OpenServiceAvailabilityDialog("
0x1e5df  ldloc.s  6
0x1e5e1  callvirt instance string [mscorlib]System.Object::ToString()
0x1e5e6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x1e5eb  ldstr    asc_11632C// ");"
0x1e5f0  call     string [mscorlib]System.String::Concat(string, string, string)
0x1e5f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1e5fa  ldarg.0
0x1e5fb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e600  ldstr    aOpenserviceava_0// "openServiceAvailabilityButton"
0x1e605  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1e60a  ldarg.0
0x1e60b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e610  ldstr    aImgsIco165003G// "/_imgs/ico_16_5003.gif"
0x1e615  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e61a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e61f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1e624  ldarg.0
0x1e625  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e62a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e62f  ldarg.0
0x1e630  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e635  ldstr    aMenuitemToolti_0// "MenuItem_ToolTip_NewObject"
0x1e63a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e63f  ldc.i4.1
0x1e640  newarr   [mscorlib]System.Object
0x1e645  dup
0x1e646  ldc.i4.0
0x1e647  ldloc.0
0x1e648  stelem.ref
0x1e649  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e64e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1e653  ldc.i4.0
0x1e654  stloc.3
0x1e655  ldarg.0
0x1e656  ldloc.3
0x1e657  ldc.i4.0
0x1e658  ldc.i4.1
0x1e659  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x1e65e  ret
0x1e65f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e664  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateBusinessClosures(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e669  brfalse.s loc_1E678
0x1e66b  ldloc.1
0x1e66c  ldstr    aF751f47d6a6e42// "{F751F47D-6A6E-42D1-9F11-33AA7B42C13A}"
0x1e671  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e676  brtrue.s loc_1E697
0x1e678  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e67d  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CurrentUserPrivilegedToCreateHolidayClosures(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e682  brfalse  loc_1E7D8
0x1e687  ldloc.1
0x1e688  ldstr    a44be8643A33242// "{44BE8643-A332-42E5-B3A3-4184ADB60671}"
0x1e68d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e692  brfalse  loc_1E7D8
0x1e697  ldarg.0
0x1e698  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1e69d  ldc.i4   0x10000
0x1e6a2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e6a7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e6ac  brfalse.s loc_1E6B5
0x1e6ae  ldarg.0
0x1e6af  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton()
0x1e6b4  pop
0x1e6b5  ldloc.1
0x1e6b6  ldstr    aF751f47d6a6e42// "{F751F47D-6A6E-42D1-9F11-33AA7B42C13A}"
0x1e6bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e6c0  brtrue.s loc_1E6D2
0x1e6c2  ldloc.1
0x1e6c3  ldstr    a44be8643A33242// "{44BE8643-A332-42E5-B3A3-4184ADB60671}"
0x1e6c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e6cd  brfalse  loc_1E7CB
0x1e6d2  ldarg.0
0x1e6d3  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x1e6d8  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1e6dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1e6e2  ldstr    aCtype// "cType"
0x1e6e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1e6ec  stloc.s  8
0x1e6ee  ldloc.s  8
0x1e6f0  ldstr    aBc// "bc"
0x1e6f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e6fa  brtrue.s loc_1E70C
0x1e6fc  ldloc.s  8
0x1e6fe  ldstr    aHs// "hs"
0x1e703  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e708  brtrue.s loc_1E74E
0x1e70a  br.s     loc_1E77A
0x1e70c  ldarg.0
0x1e70d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e712  ldstr    aCalendarRuleHo// "Calendar_Rule_Holiday"
0x1e717  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e71c  stloc.0
0x1e71d  ldarg.0
0x1e71e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e723  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e728  ldarg.0
0x1e729  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e72e  ldstr    aMenuitemToolti_0// "MenuItem_ToolTip_NewObject"
0x1e733  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e738  ldc.i4.1
0x1e739  newarr   [mscorlib]System.Object
0x1e73e  dup
0x1e73f  ldc.i4.0
0x1e740  ldloc.0
0x1e741  stelem.ref
0x1e742  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e747  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1e74c  br.s     loc_1E77A
0x1e74e  ldarg.0
0x1e74f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e754  ldstr    aSmHolidaySched// "SM_Holiday_Schedule_Title"
0x1e759  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e75e  stloc.0
0x1e75f  ldarg.0
0x1e760  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e765  ldarg.0
0x1e766  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e76b  ldstr    aWebSmWorkplans// "Web.SM.WorkPlans.Dialogs.holiday.aspx_1"...
0x1e770  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e775  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1e77a  ldarg.0
0x1e77b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e780  ldc.i4.1
0x1e781  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1e786  ldarg.0
0x1e787  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e78c  ldarg.0
0x1e78d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1e792  ldstr    aMenuitemLabelN// "MenuItem_Label_New"
0x1e797  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e79c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1e7a1  ldarg.0
0x1e7a2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e7a7  ldstr    aNewholiday// "newHoliday();"
0x1e7ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1e7b1  ldarg.0
0x1e7b2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_newButton
0x1e7b7  ldstr    aImgsIco165005G// "/_imgs/ico_16_5005.gif"
0x1e7bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e7c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e7c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1e7cb  ldc.i4.0
0x1e7cc  stloc.s  7
0x1e7ce  ldarg.0
0x1e7cf  ldloc.s  7
0x1e7d1  ldc.i4.0
0x1e7d2  ldc.i4.1
0x1e7d3  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x1e7d8  ret
```
