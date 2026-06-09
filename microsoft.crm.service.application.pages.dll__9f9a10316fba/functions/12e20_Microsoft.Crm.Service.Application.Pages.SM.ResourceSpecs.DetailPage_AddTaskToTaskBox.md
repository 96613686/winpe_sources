# Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::AddTaskToTaskBox

- ea: `0x12e20`
- end: `0x12e80`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::AddTaskToTaskBox`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x127b0`

## callees

- `0x12df0`

## string_xrefs

- `0x12e4a`: `Task_Bar_Resource_Spec_Tooltip_Format`

## pseudocode

```c

```

## disassembly

```asm
0x12e20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e25  ldstr    aB0B// "<b>{0}</b>"
0x12e2a  ldc.i4.1
0x12e2b  newarr   [mscorlib]System.Object
0x12e30  dup
0x12e31  ldc.i4.0
0x12e32  ldarg.1
0x12e33  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x12e38  stelem.ref
0x12e39  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12e3e  stloc.0
0x12e3f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x12e44  ldarg.0
0x12e45  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12e4a  ldstr    aTaskBarResourc_9// "Task_Bar_Resource_Spec_Tooltip_Format"
0x12e4f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12e54  ldc.i4.2
0x12e55  newarr   [mscorlib]System.Object
0x12e5a  dup
0x12e5b  ldc.i4.0
0x12e5c  ldarg.1
0x12e5d  stelem.ref
0x12e5e  dup
0x12e5f  ldc.i4.1
0x12e60  ldarg.2
0x12e61  stelem.ref
0x12e62  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12e67  stloc.1
0x12e68  ldarg.0
0x12e69  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::crmTaskBox
0x12e6e  ldloc.0
0x12e6f  ldarg.3
0x12e70  ldarg.s  4
0x12e72  ldloc.1
0x12e73  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTaskHtml(string, string, string, string)
0x12e78  ldarg.0
0x12e79  ldarg.2
0x12e7a  call     instance void Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::AddHelpTextToTaskBox(string helpText)
0x12e7f  ret
```
