# Microsoft.Crm.Application.Controls.AppCustomOperationEdit::ConfigureControl

- ea: `0x88e00`
- end: `0x88f28`
- name: `Microsoft.Crm.Application.Controls.AppCustomOperationEdit::ConfigureControl`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x8d1e0`

## string_xrefs

- `0x88e19`: `Web._controls.listedit.buttons.MoveUp`
- `0x88e2a`: `Web._controls.listedit.buttons.MoveDown`
- `0x88e5d`: `Web._controls.listedit.buttons.Delete`

## pseudocode

```c

```

## disassembly

```asm
0x88e00  ldarg.0
0x88e01  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureControl()
0x88e06  ldarg.0
0x88e07  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x88e0c  isinst   Microsoft.Crm.Application.Controls.AppPage
0x88e11  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x88e16  stloc.0
0x88e17  ldarg.0
0x88e18  ldloc.0
0x88e19  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0x88e1e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e23  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_MoveUpLabel(string)
0x88e28  ldarg.0
0x88e29  ldloc.0
0x88e2a  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0x88e2f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e34  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_MoveDownLabel(string)
0x88e39  ldarg.0
0x88e3a  ldloc.0
0x88e3b  ldstr    aWebControlsLis_1// "Web._controls.listedit.buttons.Edit"
0x88e40  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e45  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_EditLabel(string)
0x88e4a  ldarg.0
0x88e4b  ldloc.0
0x88e4c  ldstr    aWebControlsLis_2// "Web._controls.listedit.buttons.Add"
0x88e51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e56  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_AddLabel(string)
0x88e5b  ldarg.0
0x88e5c  ldloc.0
0x88e5d  ldstr    aWebControlsLis_3// "Web._controls.listedit.buttons.Delete"
0x88e62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e67  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_RemoveLabel(string)
0x88e6c  ldarg.0
0x88e6d  ldloc.0
0x88e6e  ldstr    aWebControlsLis_4// "Web._controls.listedit.buttons.SortAsc"
0x88e73  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e78  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_SortAscLabel(string)
0x88e7d  ldarg.0
0x88e7e  ldloc.0
0x88e7f  ldstr    aWebControlsLis_5// "Web._controls.listedit.buttons.SortDesc"
0x88e84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e89  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_SortDescLabel(string)
0x88e8e  ldarg.0
0x88e8f  ldloc.0
0x88e90  ldstr    aWebControlsLis_6// "Web._controls.listedit.labels.DefaultVa"...
0x88e95  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88e9a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_DefaultValueLabel(string)
0x88e9f  ldarg.0
0x88ea0  ldloc.0
0x88ea1  ldstr    aSystemcustomiz_2// "SystemCustomization.Boolean.Values.True"
0x88ea6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88eab  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_BooleanTrueLabel(string)
0x88eb0  ldarg.0
0x88eb1  ldloc.0
0x88eb2  ldstr    aSystemcustomiz_3// "SystemCustomization.Boolean.Values.Fals"...
0x88eb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88ebc  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_BooleanFalseLabel(string)
0x88ec1  ldarg.0
0x88ec2  ldloc.0
0x88ec3  ldstr    aWebControlsCus// "Web._controls.customoperationedit.item."...
0x88ec8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88ecd  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_ItemNameLabel(string)
0x88ed2  ldarg.0
0x88ed3  ldloc.0
0x88ed4  ldstr    aWebControlsCus_0// "Web._controls.customoperationedit.item."...
0x88ed9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88ede  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_ItemDirectionLabel(string)
0x88ee3  ldarg.0
0x88ee4  ldloc.0
0x88ee5  ldstr    aWebControlsCus_1// "Web._controls.customoperationedit.item."...
0x88eea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88eef  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_ItemDescriptionLabel(string)
0x88ef4  ldarg.0
0x88ef5  ldloc.0
0x88ef6  ldstr    aWebControlsCus_2// "Web._controls.customoperationedit.item."...
0x88efb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88f00  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_ItemRequiredLabel(string)
0x88f05  ldarg.0
0x88f06  ldloc.0
0x88f07  ldstr    aWebControlsCus_3// "Web._controls.customoperationedit.item."...
0x88f0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88f11  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_ItemTypeLabel(string)
0x88f16  ldarg.0
0x88f17  ldloc.0
0x88f18  ldstr    aWebControlsCus_4// "Web._controls.customoperationedit.item."...
0x88f1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88f22  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CustomOperationEdit::set_ItemEntityLabel(string)
0x88f27  ret
```
