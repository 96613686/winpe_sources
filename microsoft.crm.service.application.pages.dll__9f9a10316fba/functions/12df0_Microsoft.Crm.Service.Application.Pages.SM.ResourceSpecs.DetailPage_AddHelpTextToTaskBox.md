# Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::AddHelpTextToTaskBox

- ea: `0x12df0`
- end: `0x12e1c`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::AddHelpTextToTaskBox`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x12e20`

## string_xrefs

- `0x12df5`: `<table style="margin-top:5px"><tr><td width="16px">&nbsp;<td><td class="rsTaskHelp">{0}</td></tr></table>`

## pseudocode

```c

```

## disassembly

```asm
0x12df0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12df5  ldstr    aTableStyleMarg// "<table style=\"margin-top:5px\"><tr><td"...
0x12dfa  ldc.i4.1
0x12dfb  newarr   [mscorlib]System.Object
0x12e00  dup
0x12e01  ldc.i4.0
0x12e02  ldarg.1
0x12e03  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x12e08  stelem.ref
0x12e09  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12e0e  stloc.0
0x12e0f  ldarg.0
0x12e10  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Service.Application.Pages.SM.ResourceSpecs.DetailPage::crmTaskBox
0x12e15  ldloc.0
0x12e16  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0x12e1b  ret
```
