# Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent

- ea: `0x16e60`
- end: `0x16e7c`
- name: `Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderScrollerComponent`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x16d80`
- `0x16de0`

## string_xrefs

- `0x16e61`: `<div class="scrollerComponent `

## pseudocode

```c

```

## disassembly

```asm
0x16e60  ldarg.1
0x16e61  ldstr    aDivClassScroll_1// "<div class=\"scrollerComponent "
0x16e66  ldarg.2
0x16e67  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x16e6c  ldstr    aDiv_6// "\"></div>"
0x16e71  call     string [mscorlib]System.String::Concat(string, string, string)
0x16e76  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16e7b  ret
```
