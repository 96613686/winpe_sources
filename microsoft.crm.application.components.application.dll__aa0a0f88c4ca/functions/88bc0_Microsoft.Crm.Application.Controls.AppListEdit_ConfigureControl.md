# Microsoft.Crm.Application.Controls.AppListEdit::ConfigureControl

- ea: `0x88bc0`
- end: `0x88c60`
- name: `Microsoft.Crm.Application.Controls.AppListEdit::ConfigureControl`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x8d1e0`

## string_xrefs

- `0x88bd9`: `Web._controls.listedit.buttons.MoveUp`
- `0x88bea`: `Web._controls.listedit.buttons.MoveDown`
- `0x88c1d`: `Web._controls.listedit.buttons.Delete`

## pseudocode

```c

```

## disassembly

```asm
0x88bc0  ldarg.0
0x88bc1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureControl()
0x88bc6  ldarg.0
0x88bc7  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x88bcc  isinst   Microsoft.Crm.Application.Controls.AppPage
0x88bd1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x88bd6  stloc.0
0x88bd7  ldarg.0
0x88bd8  ldloc.0
0x88bd9  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0x88bde  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88be3  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_MoveUpLabel(string)
0x88be8  ldarg.0
0x88be9  ldloc.0
0x88bea  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0x88bef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88bf4  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_MoveDownLabel(string)
0x88bf9  ldarg.0
0x88bfa  ldloc.0
0x88bfb  ldstr    aWebControlsLis_1// "Web._controls.listedit.buttons.Edit"
0x88c00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88c05  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_EditLabel(string)
0x88c0a  ldarg.0
0x88c0b  ldloc.0
0x88c0c  ldstr    aWebControlsLis_2// "Web._controls.listedit.buttons.Add"
0x88c11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88c16  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_AddLabel(string)
0x88c1b  ldarg.0
0x88c1c  ldloc.0
0x88c1d  ldstr    aWebControlsLis_3// "Web._controls.listedit.buttons.Delete"
0x88c22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88c27  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_RemoveLabel(string)
0x88c2c  ldarg.0
0x88c2d  ldloc.0
0x88c2e  ldstr    aWebControlsLis_4// "Web._controls.listedit.buttons.SortAsc"
0x88c33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88c38  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_SortAscLabel(string)
0x88c3d  ldarg.0
0x88c3e  ldloc.0
0x88c3f  ldstr    aWebControlsLis_5// "Web._controls.listedit.buttons.SortDesc"
0x88c44  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88c49  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_SortDescLabel(string)
0x88c4e  ldarg.0
0x88c4f  ldloc.0
0x88c50  ldstr    aWebControlsLis_6// "Web._controls.listedit.labels.DefaultVa"...
0x88c55  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88c5a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListEdit::set_DefaultValueLabel(string)
0x88c5f  ret
```
