# Microsoft.Crm.Dialogs.CopyDynamicListToStaticDialogPage::ConfigureForm

- ea: `0x6160`
- end: `0x61ff`
- name: `Microsoft.Crm.Dialogs.CopyDynamicListToStaticDialogPage::ConfigureForm`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6110`
- `0x6130`
- `0x6150`

## string_xrefs

- `0x61a9`: `Dialog_Header_CopyList`
- `0x61bf`: `MA.List.Dialogs.CopyToStatic`
- `0x61f4`: `MA.List.Dialogs.CopyToStatic_Save`

## pseudocode

```c

```

## disassembly

```asm
0x6160  ldarg.0
0x6161  ldarg.0
0x6162  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6167  ldstr    aDialogAddtocam// "Dialog_AddToCampaign_ActionStringAddToL"...
0x616c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6171  call     instance void Microsoft.Crm.Dialogs.CopyDynamicListToStaticDialogPage::set_ActionString(string value)
0x6176  ldarg.0
0x6177  ldstr    aConfirmmodeTru// "confirmMode(true)"
0x617c  call     instance void Microsoft.Crm.Dialogs.CopyDynamicListToStaticDialogPage::set_DialogActionOk(string value)
0x6181  ldarg.0
0x6182  ldstr    aConfirmmodeFal// "confirmMode(false)"
0x6187  call     instance void Microsoft.Crm.Dialogs.CopyDynamicListToStaticDialogPage::set_DialogActionCancel(string value)
0x618c  ldarg.0
0x618d  ldc.i4   0x198
0x6192  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_Width(int32)
0x6197  ldarg.0
0x6198  ldc.i4   0xFA
0x619d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_Height(int32)
0x61a2  ldarg.0
0x61a3  ldarg.0
0x61a4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x61a9  ldstr    aDialogHeaderCo// "Dialog_Header_CopyList"
0x61ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x61b3  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x61b8  ldarg.0
0x61b9  ldarg.0
0x61ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x61bf  ldstr    aMaListDialogsC// "MA.List.Dialogs.CopyToStatic"
0x61c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x61c9  stfld    string Microsoft.Crm.Dialogs.CopyDynamicListToStaticDialogPage::BodyDescription
0x61ce  ldarg.0
0x61cf  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x61d4  ldc.i4.1
0x61d5  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x61da  stloc.0
0x61db  ldarg.0
0x61dc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x61e1  ldc.i4.2
0x61e2  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x61e7  pop
0x61e8  ldarg.0
0x61e9  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x61ee  ldloc.0
0x61ef  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::get_Item(int32)
0x61f4  ldstr    aMaListDialogsC_0// "MA.List.Dialogs.CopyToStatic_Save"
0x61f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x61fe  ret
```
