# Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.KBTemplatePropertiesPage::ConfigureForm

- ea: `0xedb0`
- end: `0xee17`
- name: `Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.KBTemplatePropertiesPage::ConfigureForm`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xedd3`: `Web.Tools.KBTemplateEditor.Dialogs.kbtemplateproperties.aspx_3`
- `0xede9`: `Web.Tools.KBTemplateEditor.Dialogs.kbtemplateproperties.aspx_50`

## pseudocode

```c

```

## disassembly

```asm
0xedb0  ldarg.0
0xedb1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xedb6  ldarg.0
0xedb7  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LanguagePicker Microsoft.Crm.Service.Application.Pages.Tools.KBTemplateEditor.Dialogs.KBTemplatePropertiesPage::languagecode
0xedbc  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::PopulateOptions()
0xedc1  ldarg.0
0xedc2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xedc7  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xedcc  dup
0xedcd  ldarg.0
0xedce  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xedd3  ldstr    aWebToolsKbtemp// "Web.Tools.KBTemplateEditor.Dialogs.kbte"...
0xedd8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeddd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xede2  dup
0xede3  ldarg.0
0xede4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xede9  ldstr    aWebToolsKbtemp_0// "Web.Tools.KBTemplateEditor.Dialogs.kbte"...
0xedee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xedf3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xedf8  dup
0xedf9  ldc.i4.0
0xedfa  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xedff  dup
0xee00  ldc.i4.1
0xee01  ldstr    aButtonLabelOk// "Button_Label_OK"
0xee06  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xee0b  ldc.i4.2
0xee0c  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xee11  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xee16  ret
```
