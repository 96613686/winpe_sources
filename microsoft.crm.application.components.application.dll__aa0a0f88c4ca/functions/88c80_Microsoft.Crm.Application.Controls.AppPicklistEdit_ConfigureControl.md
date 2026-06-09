# Microsoft.Crm.Application.Controls.AppPicklistEdit::ConfigureControl

- ea: `0x88c80`
- end: `0x88d97`
- name: `Microsoft.Crm.Application.Controls.AppPicklistEdit::ConfigureControl`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x8d1e0`

## string_xrefs

- `0x88c99`: `Web._controls.listedit.buttons.MoveUp`
- `0x88caa`: `Web._controls.listedit.buttons.MoveDown`
- `0x88cdd`: `Web._controls.listedit.buttons.Delete`

## pseudocode

```c

```

## disassembly

```asm
0x88c80  ldarg.0
0x88c81  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureControl()
0x88c86  ldarg.0
0x88c87  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x88c8c  isinst   Microsoft.Crm.Application.Controls.AppPage
0x88c91  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x88c96  stloc.0
0x88c97  ldarg.0
0x88c98  ldloc.0
0x88c99  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0x88c9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88ca3  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_MoveUpLabel(string)
0x88ca8  ldarg.0
0x88ca9  ldloc.0
0x88caa  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0x88caf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88cb4  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_MoveDownLabel(string)
0x88cb9  ldarg.0
0x88cba  ldloc.0
0x88cbb  ldstr    aWebControlsLis_1// "Web._controls.listedit.buttons.Edit"
0x88cc0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88cc5  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_EditLabel(string)
0x88cca  ldarg.0
0x88ccb  ldloc.0
0x88ccc  ldstr    aWebControlsLis_2// "Web._controls.listedit.buttons.Add"
0x88cd1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88cd6  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_AddLabel(string)
0x88cdb  ldarg.0
0x88cdc  ldloc.0
0x88cdd  ldstr    aWebControlsLis_3// "Web._controls.listedit.buttons.Delete"
0x88ce2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88ce7  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_RemoveLabel(string)
0x88cec  ldarg.0
0x88ced  ldloc.0
0x88cee  ldstr    aWebControlsLis_4// "Web._controls.listedit.buttons.SortAsc"
0x88cf3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88cf8  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_SortAscLabel(string)
0x88cfd  ldarg.0
0x88cfe  ldloc.0
0x88cff  ldstr    aWebControlsLis_5// "Web._controls.listedit.buttons.SortDesc"
0x88d04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d09  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_SortDescLabel(string)
0x88d0e  ldarg.0
0x88d0f  ldloc.0
0x88d10  ldstr    aWebControlsLis_6// "Web._controls.listedit.labels.DefaultVa"...
0x88d15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d1a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_DefaultValueLabel(string)
0x88d1f  ldarg.0
0x88d20  ldloc.0
0x88d21  ldstr    aSystemcustomiz_2// "SystemCustomization.Boolean.Values.True"
0x88d26  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d2b  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_BooleanTrueLabel(string)
0x88d30  ldarg.0
0x88d31  ldloc.0
0x88d32  ldstr    aSystemcustomiz_3// "SystemCustomization.Boolean.Values.Fals"...
0x88d37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d3c  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_BooleanFalseLabel(string)
0x88d41  ldarg.0
0x88d42  ldloc.0
0x88d43  ldstr    aWebControlsPic// "Web._controls.picklistedit.item.value"
0x88d48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d4d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_ItemValueLabel(string)
0x88d52  ldarg.0
0x88d53  ldloc.0
0x88d54  ldstr    aWebControlsPic_0// "Web._controls.picklistedit.item.label"
0x88d59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d5e  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_ItemLabelLabel(string)
0x88d63  ldarg.0
0x88d64  ldloc.0
0x88d65  ldstr    aWebControlsPic_1// "Web._controls.picklistedit.item.descrip"...
0x88d6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d6f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_ItemDescriptionLabel(string)
0x88d74  ldarg.0
0x88d75  ldloc.0
0x88d76  ldstr    aSystemcustomiz_4// "SystemCustomization.ManageEntityPage.En"...
0x88d7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d80  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_ItemColorLabel(string)
0x88d85  ldarg.0
0x88d86  ldloc.0
0x88d87  ldstr    aSystemcustomiz_5// "SystemCustomization.ManageAttributePage"...
0x88d8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88d91  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_ItemExternalNameLabel(string)
0x88d96  ret
```
