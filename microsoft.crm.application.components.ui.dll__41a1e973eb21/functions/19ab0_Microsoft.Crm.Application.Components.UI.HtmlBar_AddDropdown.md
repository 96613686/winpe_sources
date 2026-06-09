# Microsoft.Crm.Application.Components.UI.HtmlBar::AddDropdown

- ea: `0x19ab0`
- end: `0x19b0f`
- name: `Microsoft.Crm.Application.Components.UI.HtmlBar::AddDropdown`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x19cb0`

## string_xrefs

- `0x19ab1`: `<td nowrap class="htmlBtn" dropdown="true" command="`

## pseudocode

```c

```

## disassembly

```asm
0x19ab0  ldarg.1
0x19ab1  ldstr    aTdNowrapClassH// "<td nowrap class=\"htmlBtn\" dropdown="...
0x19ab6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19abb  ldarg.2
0x19abc  ldarg.1
0x19abd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x19ac2  ldarg.1
0x19ac3  ldstr    aStyleWidth30px// "\" style=\"width:30px;\"><a class=\"htm"...
0x19ac8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19acd  ldarg.3
0x19ace  ldarg.1
0x19acf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x19ad4  ldarg.1
0x19ad5  ldstr    aImgClassHtmlim_0// "\"><img class='htmlImgStyle' alt=\""
0x19ada  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19adf  ldarg.3
0x19ae0  ldarg.1
0x19ae1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x19ae6  ldarg.1
0x19ae7  ldstr    aSrcImgsHtmlbar// "\" src=\"/_imgs/htmlbar/cmd-"
0x19aec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19af1  ldarg.2
0x19af2  ldarg.1
0x19af3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x19af8  ldarg.1
0x19af9  ldstr    aGif_0// ".gif\"/>"
0x19afe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19b03  ldarg.1
0x19b04  ldstr    aATd// "</a></td>"
0x19b09  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19b0e  ret
```
