# Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::ConfigureForm

- ea: `0x26f0`
- end: `0x2755`
- name: `Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::ConfigureForm`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x26d0`
- `0x26f0`
- `0x2760`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  ldarg.0
0x26f1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x26f6  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x26fb  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x2700  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x2705  ldarg.0
0x2706  ldc.i4   0x2616
0x270b  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::set_EntityTypeCode(int32 value)
0x2710  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2715  brtrue.s loc_274E
0x2717  ldarg.0
0x2718  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x271d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x2722  dup
0x2723  ldarg.0
0x2724  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2729  ldstr    aSlaDefaultConf_0// "SLA_Default_Confirm_DialogTitle"
0x272e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2733  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2738  ldarg.0
0x2739  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x273e  ldstr    aSlaDefaultConf_1// "SLA_Default_Confirm_Message"
0x2743  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2748  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x274d  ret
0x274e  ldarg.0
0x274f  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::OnPostBack()
0x2754  ret
```
