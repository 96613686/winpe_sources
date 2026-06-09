# Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::ConfigureForm

- ea: `0x2410`
- end: `0x24b8`
- name: `Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::ConfigureForm`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2390`
- `0x23c0`
- `0x2410`
- `0x24c0`

## pseudocode

```c

```

## disassembly

```asm
0x2410  ldarg.0
0x2411  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2416  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x241b  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x2420  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x2425  ldarg.0
0x2426  ldc.i4   0x2616
0x242b  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::set_EntityTypeCode(int32 value)
0x2430  ldarg.0
0x2431  ldarg.0
0x2432  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2437  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x243c  ldstr    aIoldid// "iOldId"
0x2441  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2446  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::set_OldDefaultSlaId(string value)
0x244b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2450  brtrue.s loc_24B1
0x2452  ldarg.0
0x2453  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x2458  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x245d  dup
0x245e  ldarg.0
0x245f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2464  ldstr    aSlaDefaultConf// "SLA_Default_Confirmation_DialogTitle"
0x2469  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x246e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2473  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2478  ldarg.0
0x2479  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x247e  ldstr    aSlaEntityDefau// "SLA_Entity_Default_Confirmation_Message"
0x2483  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2488  ldc.i4.1
0x2489  newarr   [mscorlib]System.Object
0x248e  dup
0x248f  ldc.i4.0
0x2490  ldarg.0
0x2491  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2496  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x249b  ldstr    aIentityname// "iEntityName"
0x24a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x24a5  stelem.ref
0x24a6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ab  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x24b0  ret
0x24b1  ldarg.0
0x24b2  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::OnPostBack()
0x24b7  ret
```
