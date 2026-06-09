# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ToolBarReady

- ea: `0x9f80`
- end: `0xa077`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ToolBarReady`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9f80`

## string_xrefs

- `0x9fad`: `HtmlBar_Title_InsertUpdateDataField`
- `0x9fbd`: `UpdateDataField();`
- `0x9fe3`: `Toolbar_Tooltip_InsertUpdateDataField`
- `0xa018`: `HtmlBar_Title_DeleteDataField`
- `0xa028`: `DeleteDataField();`
- `0xa033`: `/_imgs/htmlbar/cmd-deleteField.gif`
- `0xa04e`: `Toolbar_Tooltip_DeleteDataField`

## pseudocode

```c

```

## disassembly

```asm
0x9f80  ldarg.0
0x9f81  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x9f86  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x9f8b  brtrue   loc_A076
0x9f90  ldarg.0
0x9f91  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x9f96  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x9f9b  brtrue   loc_A076
0x9fa0  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x9fa5  stloc.0
0x9fa6  ldloc.0
0x9fa7  ldarg.0
0x9fa8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9fad  ldstr    aHtmlbarTitleIn// "HtmlBar_Title_InsertUpdateDataField"
0x9fb2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9fb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x9fbc  ldloc.0
0x9fbd  ldstr    aUpdatedatafiel// "UpdateDataField();"
0x9fc2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x9fc7  ldloc.0
0x9fc8  ldstr    aImgsHtmlbarCmd// "/_imgs/htmlbar/cmd-insertField.gif"
0x9fcd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9fd2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9fd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9fdc  ldloc.0
0x9fdd  ldarg.0
0x9fde  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9fe3  ldstr    aToolbarTooltip_2// "Toolbar_Tooltip_InsertUpdateDataField"
0x9fe8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9fed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x9ff2  ldloc.0
0x9ff3  ldc.i4.1
0x9ff4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::set_UnSelectable(bool)
0x9ff9  ldarg.2
0x9ffa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x9fff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xa004  ldloc.0
0xa005  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xa00a  pop
0xa00b  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0xa010  stloc.1
0xa011  ldloc.1
0xa012  ldarg.0
0xa013  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa018  ldstr    aHtmlbarTitleDe_0// "HtmlBar_Title_DeleteDataField"
0xa01d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa022  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0xa027  ldloc.1
0xa028  ldstr    aDeletedatafiel// "DeleteDataField();"
0xa02d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0xa032  ldloc.1
0xa033  ldstr    aImgsHtmlbarCmd_0// "/_imgs/htmlbar/cmd-deleteField.gif"
0xa038  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa03d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa042  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xa047  ldloc.1
0xa048  ldarg.0
0xa049  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa04e  ldstr    aToolbarTooltip_3// "Toolbar_Tooltip_DeleteDataField"
0xa053  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa058  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0xa05d  ldloc.1
0xa05e  ldc.i4.1
0xa05f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::set_UnSelectable(bool)
0xa064  ldarg.2
0xa065  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0xa06a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0xa06f  ldloc.1
0xa070  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0xa075  pop
0xa076  ret
```
