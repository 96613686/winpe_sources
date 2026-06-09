# Microsoft.Crm.Service.SM.ResourceSpecifications.CreateGroupPage::ConfigureForm

- ea: `0x1280`
- end: `0x12c4`
- name: `Microsoft.Crm.Service.SM.ResourceSpecifications.CreateGroupPage::ConfigureForm`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x129f`: `Create_Resource_Group_Dialog_Title`
- `0x12b4`: `Create_Resource_Group_Dialog_Description`

## pseudocode

```c

```

## disassembly

```asm
0x1280  ldarg.0
0x1281  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1286  ldarg.0
0x1287  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x128c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1291  dup
0x1292  ldc.i4.1
0x1293  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowHeader(bool)
0x1298  dup
0x1299  ldarg.0
0x129a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x129f  ldstr    aCreateResource_0// "Create_Resource_Group_Dialog_Title"
0x12a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12a9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x12ae  ldarg.0
0x12af  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12b4  ldstr    aCreateResource_1// "Create_Resource_Group_Dialog_Descriptio"...
0x12b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12be  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x12c3  ret
```
