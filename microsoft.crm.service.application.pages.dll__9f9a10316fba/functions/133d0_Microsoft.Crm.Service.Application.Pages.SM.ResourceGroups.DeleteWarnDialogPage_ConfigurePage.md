# Microsoft.Crm.Service.Application.Pages.SM.ResourceGroups.DeleteWarnDialogPage::ConfigurePage

- ea: `0x133d0`
- end: `0x1342d`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceGroups.DeleteWarnDialogPage::ConfigurePage`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x133e8`: `Dialog_Delete_Warn_Title`
- `0x133fe`: `Dialog_Delete_Warn_Description`

## pseudocode

```c

```

## disassembly

```asm
0x133d0  ldarg.0
0x133d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x133d6  ldarg.0
0x133d7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x133dc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x133e1  dup
0x133e2  ldarg.0
0x133e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x133e8  ldstr    aDialogDeleteWa// "Dialog_Delete_Warn_Title"
0x133ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x133f2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x133f7  dup
0x133f8  ldarg.0
0x133f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x133fe  ldstr    aDialogDeleteWa_0// "Dialog_Delete_Warn_Description"
0x13403  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13408  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1340d  dup
0x1340e  ldc.i4.0
0x1340f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x13414  dup
0x13415  ldc.i4.4
0x13416  ldstr    aButtonLabelYes// "Button_Label_Yes"
0x1341b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x13420  ldc.i4.s 0x10
0x13422  ldstr    aButtonLabelNo// "Button_Label_No"
0x13427  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1342c  ret
```
