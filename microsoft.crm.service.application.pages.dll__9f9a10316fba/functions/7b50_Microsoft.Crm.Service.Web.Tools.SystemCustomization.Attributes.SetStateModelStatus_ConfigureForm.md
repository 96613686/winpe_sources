# Microsoft.Crm.Service.Web.Tools.SystemCustomization.Attributes.SetStateModelStatus::ConfigureForm

- ea: `0x7b50`
- end: `0x7bec`
- name: `Microsoft.Crm.Service.Web.Tools.SystemCustomization.Attributes.SetStateModelStatus::ConfigureForm`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7b9d`: `LOCID_NO_TRANSITIONPATH_FROM_ACTIVE_RESOLVE_CASE`
- `0x7ba2`: `Dlg_SetStateModelStatusConfirmation_No_TransitionPath_From_Active_Resolve_Case`
- `0x7bb7`: `Dlg_SetStateModelStatusConfirmation_No_TransitionPath_From_Active_Resolve_Case`
- `0x7bb2`: `LOCID_NO_TRANSITIONPATH_FROM_ACTIVE_CANCEL_CASE`
- `0x7bc7`: `LOCID_NO_TRANSITIONPATH_FROM_ACTIVE_INACTIVE_CUSTOMENTITY`

## pseudocode

```c

```

## disassembly

```asm
0x7b50  ldarg.0
0x7b51  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x7b56  ldarg.0
0x7b57  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x7b5c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x7b61  dup
0x7b62  ldc.i4   0x1003
0x7b67  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x7b6c  dup
0x7b6d  ldarg.0
0x7b6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b73  ldstr    aSetStateModelS// "Set_State_Model_Status_Dlg_Title"
0x7b78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b7d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x7b82  ldarg.0
0x7b83  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7b88  ldstr    aSetStateModelS_0// "Set_State_Model_Status_Dlg_Description"
0x7b8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7b92  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x7b97  ldarg.0
0x7b98  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x7b9d  ldstr    aLocidNoTransit// "LOCID_NO_TRANSITIONPATH_FROM_ACTIVE_RES"...
0x7ba2  ldstr    aDlgSetstatemod// "Dlg_SetStateModelStatusConfirmation_No_"...
0x7ba7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7bac  ldarg.0
0x7bad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x7bb2  ldstr    aLocidNoTransit_0// "LOCID_NO_TRANSITIONPATH_FROM_ACTIVE_CAN"...
0x7bb7  ldstr    aDlgSetstatemod// "Dlg_SetStateModelStatusConfirmation_No_"...
0x7bbc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7bc1  ldarg.0
0x7bc2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x7bc7  ldstr    aLocidNoTransit_1// "LOCID_NO_TRANSITIONPATH_FROM_ACTIVE_INA"...
0x7bcc  ldstr    aDlgSetstatemod_0// "Dlg_SetStateModelStatusConfirmation_Dlg"...
0x7bd1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7bd6  ldarg.0
0x7bd7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x7bdc  ldstr    aLocidNoTransit_2// "LOCID_NO_TRANSITION_DEFINED"
0x7be1  ldstr    aDlgSetstatemod_1// "Dlg_SetStateModelStatusConfirmation_Des"...
0x7be6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7beb  ret
```
