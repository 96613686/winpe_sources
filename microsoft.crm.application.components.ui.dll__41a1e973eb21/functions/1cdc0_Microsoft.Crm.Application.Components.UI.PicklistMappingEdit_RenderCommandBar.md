# Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::RenderCommandBar

- ea: `0x1cdc0`
- end: `0x1cdee`
- name: `Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::RenderCommandBar`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ce90`

## callees

- `0x1cdf0`

## string_xrefs

- `0x1cdc7`: `<table id="CommandBar" width="100%" class="ms-crm-Picklist-MenuBar">`

## pseudocode

```c

```

## disassembly

```asm
0x1cdc0  ldarg.1
0x1cdc1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1cdc6  dup
0x1cdc7  ldstr    aTableIdCommand// "<table id=\"CommandBar\" width=\"100%\""...
0x1cdcc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1cdd1  dup
0x1cdd2  ldstr    aTr_1// "<tr>"
0x1cdd7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1cddc  ldarg.0
0x1cddd  ldarg.1
0x1cdde  call     instance void Microsoft.Crm.Application.Components.UI.PicklistMappingEdit::AddFiller(class [mscorlib]System.IO.TextWriter output)
0x1cde3  ldstr    aTrTable// "</tr></table>"
0x1cde8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1cded  ret
```
