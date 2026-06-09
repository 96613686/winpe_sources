# Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderSimpleHtmlBarControls

- ea: `0x884c0`
- end: `0x885cd`
- name: `Microsoft.Crm.Application.Controls.AppHtmlBarControl::RenderSimpleHtmlBarControls`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x88240`

## string_xrefs

- `0x884d4`: `UnsubscribeLink();`
- `0x884df`: `HtmlBar_Title_UnsubscribeLink`
- `0x884e9`: `cmd-unsubscribeLink`
- `0x88522`: `createHyperlink()`
- `0x8853e`: `HtmlBar_Title_CreateHyperlink`
- `0x8856a`: `HtmlBar_Title_CreateHyperlink`
- `0x88585`: `cmd-insertHyperlink`
- `0x885a6`: `HtmlBar_Display_CreateHyperlink`

## pseudocode

```c

```

## disassembly

```asm
0x884c0  ldarg.0
0x884c1  ldarg.1
0x884c2  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x884c7  ldarg.1
0x884c8  ldstr    aTdStylePadding// "<td style=\"padding:0px;\"><table width"...
0x884cd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x884d2  ldarg.0
0x884d3  ldarg.1
0x884d4  ldstr    aUnsubscribelin// "UnsubscribeLink();"
0x884d9  ldarg.0
0x884da  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x884df  ldstr    aHtmlbarTitleUn// "HtmlBar_Title_UnsubscribeLink"
0x884e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x884e9  ldstr    aCmdUnsubscribe// "cmd-unsubscribeLink"
0x884ee  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddTextButton(class [mscorlib]System.IO.TextWriter, string, string, string)
0x884f3  ldarg.1
0x884f4  ldstr    aTdWidth100Igno// "<td width=\"100%\" ignoreforresize=\"tr"...
0x884f9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x884fe  ldarg.0
0x884ff  ldarg.1
0x88500  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::AddSpacer(class [mscorlib]System.IO.TextWriter)
0x88505  ldarg.0
0x88506  ldc.i4.1
0x88507  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::set_AllowSpacer(bool)
0x8850c  ldarg.1
0x8850d  ldstr    aTdStylePadding// "<td style=\"padding:0px;\"><table width"...
0x88512  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x88517  ldarg.1
0x88518  ldstr    aTdNowrapClassH// "<td nowrap class=\"htmlBtn HtmlBar_AddT"...
0x8851d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x88522  ldstr    aCreatehyperlin// "createHyperlink()"
0x88527  ldarg.1
0x88528  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x8852d  ldarg.1
0x8852e  ldstr    aASelectenableT// "\"><a selectEnable='true' onclick=\"ret"...
0x88533  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x88538  ldarg.0
0x88539  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x8853e  ldstr    aHtmlbarTitleCr// "HtmlBar_Title_CreateHyperlink"
0x88543  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88548  ldarg.1
0x88549  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x8854e  ldarg.1
0x8854f  ldstr    asc_F6B30// "\""
0x88554  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x88559  ldarg.1
0x8855a  ldstr    aImgAlt_0// "><img alt=\""
0x8855f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x88564  ldarg.0
0x88565  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x8856a  ldstr    aHtmlbarTitleCr// "HtmlBar_Title_CreateHyperlink"
0x8856f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x88574  ldarg.1
0x88575  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x8857a  ldarg.1
0x8857b  ldstr    aSrcImgsHtmlbar// "\" src=\"/_imgs/htmlbar/"
0x88580  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x88585  ldstr    aCmdInserthyper// "cmd-insertHyperlink"
0x8858a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlPathEncode(string)
0x8858f  ldarg.1
0x88590  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x88595  ldarg.1
0x88596  ldstr    aGifAlignAbsmid// ".gif\" align='absmiddle'><span class='h"...
0x8859b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x885a0  ldarg.0
0x885a1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AppHtmlBarControl::_rm
0x885a6  ldstr    aHtmlbarDisplay// "HtmlBar_Display_CreateHyperlink"
0x885ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x885b0  ldarg.1
0x885b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x885b6  ldarg.1
0x885b7  ldstr    aSpanATd// "</span></a></td>"
0x885bc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x885c1  ldarg.1
0x885c2  ldstr    aTdWidth100Igno// "<td width=\"100%\" ignoreforresize=\"tr"...
0x885c7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x885cc  ret
```
