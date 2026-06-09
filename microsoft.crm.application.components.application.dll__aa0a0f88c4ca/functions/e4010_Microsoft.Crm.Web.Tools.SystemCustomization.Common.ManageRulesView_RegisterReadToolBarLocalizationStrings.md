# Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::RegisterReadToolBarLocalizationStrings

- ea: `0xe4010`
- end: `0xe4071`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::RegisterReadToolBarLocalizationStrings`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0xe3a60`

## callees

- `0xe42e0`

## string_xrefs

- `0xe4020`: `Web._controls.listedit.buttons.MoveUp`
- `0xe4040`: `Web._controls.listedit.buttons.MoveDown`
- `0xe4060`: `Web._controls.listedit.buttons.Delete`
- `0xe4016`: `LOCID_MOVE_UP_BUTTON`
- `0xe4036`: `LOCID_MOVE_DOWN_BUTTON`
- `0xe4056`: `LOCID_DELETE_BUTTON`

## pseudocode

```c

```

## disassembly

```asm
0xe4010  ldarg.0
0xe4011  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe4016  ldstr    aLocidMoveUpBut// "LOCID_MOVE_UP_BUTTON"
0xe401b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe4020  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0xe4025  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe402a  ldc.i4.0
0xe402b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4030  ldarg.0
0xe4031  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe4036  ldstr    aLocidMoveDownB// "LOCID_MOVE_DOWN_BUTTON"
0xe403b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe4040  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0xe4045  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe404a  ldc.i4.0
0xe404b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4050  ldarg.0
0xe4051  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe4056  ldstr    aLocidDeleteBut// "LOCID_DELETE_BUTTON"
0xe405b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe4060  ldstr    aWebControlsLis_3// "Web._controls.listedit.buttons.Delete"
0xe4065  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe406a  ldc.i4.0
0xe406b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe4070  ret
```
