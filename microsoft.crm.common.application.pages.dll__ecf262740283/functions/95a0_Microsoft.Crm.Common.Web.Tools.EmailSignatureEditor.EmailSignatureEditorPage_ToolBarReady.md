# Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::ToolBarReady

- ea: `0x95a0`
- end: `0x9665`
- name: `Microsoft.Crm.Common.Web.Tools.EmailSignatureEditor.EmailSignatureEditorPage::ToolBarReady`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x95a0`

## string_xrefs

- `0x95bd`: `HtmlBar_Title_DeleteEmailSignature`
- `0x95c7`: `DeleteEmailSignature();`
- `0x95cc`: `/_imgs/ico/16_L_remove.gif`
- `0x95d7`: `Toolbar_Tooltip_DeleteEmailSignature`
- `0x963a`: `HtmlBar_Title_RemoveDefault`
- `0x9644`: `RemoveDefaultSignature();`
- `0x9649`: `/_imgs/ico/16_removedefault.png`
- `0x9654`: `Toolbar_Tooltip_RemoveDefault`

## pseudocode

```c

```

## disassembly

```asm
0x95a0  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_DeleteEmailSignature()
0x95a5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x95aa  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x95af  brfalse.s loc_95E7
0x95b1  ldarg.2
0x95b2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x95b7  ldarg.0
0x95b8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95bd  ldstr    aHtmlbarTitleDe// "HtmlBar_Title_DeleteEmailSignature"
0x95c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95c7  ldstr    aDeleteemailsig// "DeleteEmailSignature();"
0x95cc  ldstr    aImgsIco16LRemo// "/_imgs/ico/16_L_remove.gif"
0x95d1  ldarg.0
0x95d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x95d7  ldstr    aToolbarTooltip// "Toolbar_Tooltip_DeleteEmailSignature"
0x95dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x95e6  pop
0x95e7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteEmailSignature()
0x95ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x95f1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x95f6  brfalse.s loc_9664
0x95f8  ldarg.2
0x95f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x95fe  ldarg.0
0x95ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9604  ldstr    aHtmlbarTitleSe// "HtmlBar_Title_SetAsDefault"
0x9609  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x960e  ldstr    aSetasdefaultsi// "SetAsDefaultSignature();"
0x9613  ldstr    aImgsIco16Setas// "/_imgs/ico/16_setasdefault.png"
0x9618  ldarg.0
0x9619  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x961e  ldstr    aToolbarTooltip_0// "Toolbar_Tooltip_SetAsDefault"
0x9623  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9628  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x962d  pop
0x962e  ldarg.2
0x962f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x9634  ldarg.0
0x9635  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x963a  ldstr    aHtmlbarTitleRe// "HtmlBar_Title_RemoveDefault"
0x963f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9644  ldstr    aRemovedefaults// "RemoveDefaultSignature();"
0x9649  ldstr    aImgsIco16Remov// "/_imgs/ico/16_removedefault.png"
0x964e  ldarg.0
0x964f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9654  ldstr    aToolbarTooltip_1// "Toolbar_Tooltip_RemoveDefault"
0x9659  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x965e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x9663  pop
0x9664  ret
```
