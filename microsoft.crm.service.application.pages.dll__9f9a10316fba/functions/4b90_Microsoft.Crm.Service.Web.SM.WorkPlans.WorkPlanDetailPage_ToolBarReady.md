# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::ToolBarReady

- ea: `0x4b90`
- end: `0x4ee2`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::ToolBarReady`
- size: `850`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x4300`
- `0x4b90`

## string_xrefs

- `0x4cdd`: `_deleteActionEnabled`
- `0x4ced`: `onActionMenuClick('delete', {0});`
- `0x4d18`: `MenuItem_Label_DeleteObject`
- `0x4dda`: `MenuItem_Label_Copy_Shortcut`

## pseudocode

```c

```

## disassembly

```asm
0x4b90  ldarg.0
0x4b91  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4b96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4b9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ba0  stloc.0
0x4ba1  ldloc.0
0x4ba2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanCreate()
0x4ba7  brtrue.s loc_4BB1
0x4ba9  ldloc.0
0x4baa  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanWrite()
0x4baf  brfalse.s loc_4C29
0x4bb1  ldarg.0
0x4bb2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4bb7  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x4bbc  brtrue.s loc_4C29
0x4bbe  ldloc.0
0x4bbf  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanRead()
0x4bc4  brfalse.s loc_4BF1
0x4bc6  ldarg.2
0x4bc7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x4bcc  ldsfld   string [mscorlib]System.String::Empty
0x4bd1  ldstr    aFindCrmformSav// "$find('crmForm').Save();"
0x4bd6  ldstr    aImgsIco16SaveG// "/_imgs/ico/16_save.gif"
0x4bdb  ldarg.0
0x4bdc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4be1  ldstr    aMenuitemLabelS// "MenuItem_Label_Save"
0x4be6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4beb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x4bf0  pop
0x4bf1  ldarg.2
0x4bf2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x4bf7  ldarg.0
0x4bf8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4bfd  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveClose"
0x4c02  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c07  ldstr    aFindCrmformSav_0// "$find('crmForm').SaveAndClose();"
0x4c0c  ldstr    aImgsIco16Savec// "/_imgs/ico/16_saveClose.gif"
0x4c11  ldarg.0
0x4c12  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4c17  ldstr    aMenuitemLabelS_0// "MenuItem_Label_SaveClose"
0x4c1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x4c26  pop
0x4c27  br.s     loc_4C5F
0x4c29  ldarg.2
0x4c2a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x4c2f  ldarg.0
0x4c30  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4c35  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x4c3a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c3f  ldstr    aClosewindow// "closeWindow();"
0x4c44  ldstr    aImgsIco16Close// "/_imgs/ico/16_close.gif"
0x4c49  ldarg.0
0x4c4a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4c4f  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x4c54  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x4c5e  pop
0x4c5f  ldarg.0
0x4c60  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4c65  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x4c6a  ldc.i4.2
0x4c6b  bne.un   loc_4EE1
0x4c70  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x4c75  stloc.1
0x4c76  ldloc.1
0x4c77  ldstr    aAction// "action"
0x4c7c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x4c81  ldloc.1
0x4c82  ldstr    aImgsMnuActions// "/_imgs/mnu_actions.gif"
0x4c87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c8c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x4c96  ldloc.1
0x4c97  ldarg.0
0x4c98  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4c9d  ldstr    aMenuLabelActio// "Menu_Label_Actions"
0x4ca2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4ca7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x4cac  ldloc.1
0x4cad  ldloc.1
0x4cae  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x4cb3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x4cb8  ldloc.1
0x4cb9  ldc.i4.1
0x4cba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x4cbf  ldloc.1
0x4cc0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x4cc5  stloc.2
0x4cc6  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteCalendar()
0x4ccb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4cd0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cd5  brfalse.s loc_4D49
0x4cd7  ldarg.0
0x4cd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4cdd  ldstr    aDeleteactionen// "_deleteActionEnabled"
0x4ce2  ldc.i4.1
0x4ce3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x4ce8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ced  ldstr    aOnactionmenucl// "onActionMenuClick('delete', {0});"
0x4cf2  ldc.i4.1
0x4cf3  newarr   [mscorlib]System.Object
0x4cf8  dup
0x4cf9  ldc.i4.0
0x4cfa  ldc.i4   0xFA3
0x4cff  box      [mscorlib]System.Int32
0x4d04  stelem.ref
0x4d05  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d0a  stloc.s  4
0x4d0c  ldloc.2
0x4d0d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d12  ldarg.0
0x4d13  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4d18  ldstr    aMenuitemLabelD// "MenuItem_Label_DeleteObject"
0x4d1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d22  ldc.i4.1
0x4d23  newarr   [mscorlib]System.Object
0x4d28  dup
0x4d29  ldc.i4.0
0x4d2a  ldarg.0
0x4d2b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4d30  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x4d35  ldc.i4.1
0x4d36  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x4d3b  stelem.ref
0x4d3c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d41  ldloc.s  4
0x4d43  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x4d48  pop
0x4d49  ldloc.2
0x4d4a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x4d4f  ldarg.0
0x4d50  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d55  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d5a  ldstr    aCalendarid// "calendarId"
0x4d5f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d64  brfalse.s loc_4DBF
0x4d66  ldarg.0
0x4d67  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d6c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d71  ldstr    aCalendarid// "calendarId"
0x4d76  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d7b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4d80  ldc.i4.0
0x4d81  ble.s    loc_4DBF
0x4d83  ldarg.0
0x4d84  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4d89  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4d8e  ldstr    aId// "id"
0x4d93  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4d98  brfalse.s loc_4DBC
0x4d9a  ldarg.0
0x4d9b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4da0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4da5  ldstr    aId// "id"
0x4daa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4daf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4db4  ldc.i4.0
0x4db5  cgt
0x4db7  ldc.i4.0
0x4db8  ceq
0x4dba  br.s     loc_4DC0
0x4dbc  ldc.i4.1
0x4dbd  br.s     loc_4DC0
0x4dbf  ldc.i4.0
0x4dc0  stloc.3
0x4dc1  ldarg.0
0x4dc2  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x4dc7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x4dcc  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsInternetExplorer(class [System.Web]System.Web.HttpRequest)
0x4dd1  brfalse.s loc_4E51
0x4dd3  ldloc.2
0x4dd4  ldarg.0
0x4dd5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4dda  ldstr    aMenuitemLabelC_0// "MenuItem_Label_Copy_Shortcut"
0x4ddf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4de4  ldloc.3
0x4de5  brtrue.s loc_4E11
0x4de7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4dec  ldstr    aSendformshortc// "sendFormShortcut(false, '{0}')"
0x4df1  ldc.i4.1
0x4df2  newarr   [mscorlib]System.Object
0x4df7  dup
0x4df8  ldc.i4.0
0x4df9  ldarg.0
0x4dfa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4dff  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTitle()
0x4e04  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4e09  stelem.ref
0x4e0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e0f  br.s     loc_4E4B
0x4e11  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e16  ldstr    aMscrmFormactio// "Mscrm.FormAction.sendFormShortcut(false"...
0x4e1b  ldc.i4.3
0x4e1c  newarr   [mscorlib]System.Object
0x4e21  dup
0x4e22  ldc.i4.0
0x4e23  ldarg.0
0x4e24  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarName
0x4e29  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4e2e  stelem.ref
0x4e2f  dup
0x4e30  ldc.i4.1
0x4e31  ldarg.0
0x4e32  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_CalendarId()
0x4e37  stelem.ref
0x4e38  dup
0x4e39  ldc.i4.2
0x4e3a  ldarg.0
0x4e3b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x4e40  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x4e45  stelem.ref
0x4e46  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e4b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x4e50  pop
0x4e51  ldloc.2
0x4e52  ldarg.0
0x4e53  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4e58  ldstr    aMenuitemLabelS_1// "MenuItem_Label_Send_Shortcut"
0x4e5d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4e62  ldloc.3
0x4e63  brtrue.s loc_4E8F
0x4e65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e6a  ldstr    aSendformshortc_0// "sendFormShortcut(true, '{0}')"
0x4e6f  ldc.i4.1
0x4e70  newarr   [mscorlib]System.Object
0x4e75  dup
0x4e76  ldc.i4.0
0x4e77  ldarg.0
0x4e78  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4e7d  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTitle()
0x4e82  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4e87  stelem.ref
0x4e88  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e8d  br.s     loc_4EC9
0x4e8f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e94  ldstr    aMscrmFormactio_0// "Mscrm.FormAction.sendFormShortcut(true,"...
0x4e99  ldc.i4.3
0x4e9a  newarr   [mscorlib]System.Object
0x4e9f  dup
0x4ea0  ldc.i4.0
0x4ea1  ldarg.0
0x4ea2  ldfld    string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarName
0x4ea7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x4eac  stelem.ref
0x4ead  dup
0x4eae  ldc.i4.1
0x4eaf  ldarg.0
0x4eb0  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_CalendarId()
0x4eb5  stelem.ref
0x4eb6  dup
0x4eb7  ldc.i4.2
0x4eb8  ldarg.0
0x4eb9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x4ebe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x4ec3  stelem.ref
0x4ec4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ec9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x4ece  pop
0x4ecf  ldarg.2
0x4ed0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x4ed5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x4eda  ldloc.1
0x4edb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x4ee0  pop
0x4ee1  ret
```
