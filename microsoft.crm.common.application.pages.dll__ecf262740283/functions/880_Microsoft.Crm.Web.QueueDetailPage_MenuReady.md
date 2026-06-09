# Microsoft.Crm.Web.QueueDetailPage::MenuReady

- ea: `0x880`
- end: `0xa48`
- name: `Microsoft.Crm.Web.QueueDetailPage::MenuReady`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7e0`
- `0x880`

## string_xrefs

- `0x9b7`: `openObj(`
- `0x9fb`: `openObj(`

## pseudocode

```c

```

## disassembly

```asm
0x880  ldarg.0
0x881  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x886  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x88b  ldc.i4.2
0x88c  bne.un   loc_A47
0x891  ldarg.2
0x892  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuId()
0x897  ldc.i4.2
0x898  bne.un   loc_A47
0x89d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ApproveRejectEmailAddress()
0x8a2  ldc.i4.1
0x8a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8a8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8ad  brfalse  loc_A1A
0x8b2  ldarg.2
0x8b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x8b8  ldarg.0
0x8b9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8be  ldstr    aMenuitemLabelA// "MenuItem_Label_ApproveEmailAddress"
0x8c3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c8  ldstr    aOnactionmenucl// "onActionMenuClick('approve_emailaddress"...
0x8cd  ldarg.0
0x8ce  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x8d3  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x8d8  stloc.0
0x8d9  ldloca.s 0
0x8db  ldstr    aD// "D"
0x8e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e5  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x8ea  ldstr    asc_1F06E// ")"
0x8ef  call     string [mscorlib]System.String::Concat(string, string, string)
0x8f4  ldstr    aImgsIco16Appro// "/_imgs/ico/16_approveemailofqueue.png"
0x8f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string)
0x8fe  pop
0x8ff  ldarg.2
0x900  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x905  ldarg.0
0x906  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x90b  ldstr    aMenuitemLabelR// "MenuItem_Label_RejectEmailAddress"
0x910  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x915  ldstr    aOnactionmenucl_0// "onActionMenuClick('reject_emailaddress'"...
0x91a  ldarg.0
0x91b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x920  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x925  stloc.0
0x926  ldloca.s 0
0x928  ldstr    aD// "D"
0x92d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x932  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x937  ldstr    asc_1F06E// ")"
0x93c  call     string [mscorlib]System.String::Concat(string, string, string)
0x941  ldstr    aImgsIco16Rejec// "/_imgs/ico/16_rejectemailofqueue.png"
0x946  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string)
0x94b  pop
0x94c  ldarg.0
0x94d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x952  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x957  ldstr    aId// "id"
0x95c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x961  brfalse  loc_A1A
0x966  ldarg.0
0x967  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x96c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x971  ldstr    aId// "id"
0x976  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x97b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x980  brtrue   loc_A1A
0x985  ldarg.0
0x986  ldarg.0
0x987  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x98c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x991  ldstr    aId// "id"
0x996  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x99b  call     instance string Microsoft.Crm.Web.QueueDetailPage::GetConvertRuleId(string queueId)
0x9a0  stloc.1
0x9a1  ldloc.1
0x9a2  brfalse.s loc_9F0
0x9a4  ldarg.2
0x9a5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x9aa  ldstr    aEmailToCase// "Email To Case"
0x9af  ldc.i4.5
0x9b0  newarr   [mscorlib]System.Object
0x9b5  dup
0x9b6  ldc.i4.0
0x9b7  ldstr    aOpenobj// "openObj("
0x9bc  stelem.ref
0x9bd  dup
0x9be  ldc.i4.1
0x9bf  ldc.i4   0x2454
0x9c4  box      [mscorlib]System.Int32
0x9c9  stelem.ref
0x9ca  dup
0x9cb  ldc.i4.2
0x9cc  ldstr    asc_1F1CE// ",\"{"
0x9d1  stelem.ref
0x9d2  dup
0x9d3  ldc.i4.3
0x9d4  ldloc.1
0x9d5  stelem.ref
0x9d6  dup
0x9d7  ldc.i4.4
0x9d8  ldstr    asc_1F1D6// "}\")"
0x9dd  stelem.ref
0x9de  call     string [mscorlib]System.String::Concat(object[])
0x9e3  ldstr    asc_1F1DE// ""
0x9e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string)
0x9ed  pop
0x9ee  br.s     loc_A1A
0x9f0  ldarg.2
0x9f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x9f6  ldstr    aEmailToCase// "Email To Case"
0x9fb  ldstr    aOpenobj// "openObj("
0xa00  ldc.i4   0x2454
0xa05  box      [mscorlib]System.Int32
0xa0a  ldstr    asc_1F06E// ")"
0xa0f  call     string [mscorlib]System.String::Concat(object, object, object)
0xa14  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string)
0xa19  pop
0xa1a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xa1f  brfalse.s loc_A47
0xa21  ldarg.2
0xa22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xa27  ldarg.0
0xa28  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa2d  ldstr    aWebManuQueueLa// "Web.Manu.Queue.LaunchMailbox"
0xa32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa37  ldstr    aMscrmMailboxac// "Mscrm.MailboxActions.launchMailboxFromF"...
0xa3c  ldstr    aImgsRibbonLaun// "/_imgs/ribbon/LaunchMailbox_16.png"
0xa41  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string)
0xa46  pop
0xa47  ret
```
