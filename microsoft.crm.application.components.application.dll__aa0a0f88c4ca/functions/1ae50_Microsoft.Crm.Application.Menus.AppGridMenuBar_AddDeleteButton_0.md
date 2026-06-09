# Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton_0

- ea: `0x1ae50`
- end: `0x1aec7`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::AddDeleteButton_0`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1ae10`
- `0x1ae30`
- `0x23f20`

## callees

- `0x1ae50`
- `0x1b410`
- `0x24210`

## string_xrefs

- `0x1aeb1`: `MenuItem_Label_Delete`
- `0x1ae57`: `delete`
- `0x1ae6c`: `/_imgs/ico_16_delete.gif`

## pseudocode

```c

```

## disassembly

```asm
0x1ae50  ldarg.0
0x1ae51  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1ae56  ldarg.0
0x1ae57  ldstr    aDelete// "delete"
0x1ae5c  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x1ae61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1ae66  ldarg.0
0x1ae67  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1ae6c  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x1ae71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ae76  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ae7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1ae80  ldarg.0
0x1ae81  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1ae86  ldarg.1
0x1ae87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x1ae8c  ldarg.0
0x1ae8d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1ae92  ldc.i4.1
0x1ae93  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x1ae98  ldarg.0
0x1ae99  ldfld    int32 Microsoft.Crm.Application.Menus.AppGridMenuBar::_objectTypeId
0x1ae9e  ldc.i4   0x270D
0x1aea3  bne.un.s loc_1AEC0
0x1aea5  ldarg.0
0x1aea6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1aeab  ldarg.0
0x1aeac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1aeb1  ldstr    aMenuitemLabelD_1// "MenuItem_Label_Delete"
0x1aeb6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1aebb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1aec0  ldarg.0
0x1aec1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppGridMenuBar::_deleteButton
0x1aec6  ret
```
