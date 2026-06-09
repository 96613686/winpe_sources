# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildMailMergeTemplateMenuBar

- ea: `0x1fd50`
- end: `0x1fdfc`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildMailMergeTemplateMenuBar`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x19fd0`
- `0x1b410`
- `0x1c010`
- `0x1fd50`
- `0x24210`

## string_xrefs

- `0x1fd97`: `Menu_Label_PublishMailMergeTemplate`
- `0x1fda7`: `publishmailmergetemplate`
- `0x1fddc`: `Menu_Label_UnpublishMailMergeTemplate`
- `0x1fdec`: `unpublishmailmergetemplate`

## pseudocode

```c

```

## disassembly

```asm
0x1fd50  ldarg.0
0x1fd51  ldc.i4   0x9F
0x1fd56  ldc.i4.1
0x1fd57  ldc.i4.1
0x1fd58  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x1fd5d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_PublishOrgMailMergeTemplate()
0x1fd62  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fd67  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fd6c  brfalse  loc_1FDFB
0x1fd71  ldarg.0
0x1fd72  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1fd77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1fd7c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1fd81  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1fd86  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1fd8b  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1fd90  dup
0x1fd91  ldarg.0
0x1fd92  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fd97  ldstr    aMenuLabelPubli// "Menu_Label_PublishMailMergeTemplate"
0x1fd9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fda1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1fda6  ldarg.0
0x1fda7  ldstr    aPublishmailmer// "publishmailmergetemplate"
0x1fdac  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x1fdb1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1fdb6  ldarg.0
0x1fdb7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup Microsoft.Crm.Application.Menus.AppGridMenuBar::get_MoreActionsButton()
0x1fdbc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x1fdc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x1fdc6  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton::.ctor()
0x1fdcb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x1fdd0  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x1fdd5  dup
0x1fdd6  ldarg.0
0x1fdd7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x1fddc  ldstr    aMenuLabelUnpub_1// "Menu_Label_UnpublishMailMergeTemplate"
0x1fde1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fde6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x1fdeb  ldarg.0
0x1fdec  ldstr    aUnpublishmailm// "unpublishmailmergetemplate"
0x1fdf1  call     instance string Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildDoActionScript(string action)
0x1fdf6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x1fdfb  ret
```
