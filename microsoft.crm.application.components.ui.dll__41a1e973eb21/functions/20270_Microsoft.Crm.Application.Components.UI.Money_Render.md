# Microsoft.Crm.Application.Components.UI.Money::Render

- ea: `0x20270`
- end: `0x20420`
- name: `Microsoft.Crm.Application.Components.UI.Money::Render`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x20270`
- `0x20a80`
- `0x20c60`
- `0x23c20`
- `0x24280`

## string_xrefs

- `0x202eb`: `ms-crm-Money-CurrencySymbol ms-crm-ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x20270  ldarg.0
0x20271  ldstr    aMsCrmMoney// "ms-crm-Money"
0x20276  call     instance void Microsoft.Crm.Application.Components.UI.Number::set_NumberInputClass(string value)
0x2027b  ldarg.1
0x2027c  ldstr    aTable// "<table"
0x20281  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20286  ldstr    aId// "id"
0x2028b  ldarg.0
0x2028c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x20291  ldstr    aTable_2// "_table"
0x20296  call     string [mscorlib]System.String::Concat(string, string)
0x2029b  ldarg.1
0x2029c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x202a1  ldarg.1
0x202a2  ldstr    aDirLtrClassMsC// " dir=\"ltr\" class=\"ms-crm-Money\" wid"...
0x202a7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x202ac  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x202b1  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x202b6  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x202bb  brfalse.s loc_202CA
0x202bd  ldarg.1
0x202be  ldstr    aSpanDirRtl// "<span dir=\"rtl\" "
0x202c3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x202c8  br.s     loc_202D5
0x202ca  ldarg.1
0x202cb  ldstr    aSpan_3// "<span "
0x202d0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x202d5  ldarg.0
0x202d6  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x202db  brtrue.s loc_202E5
0x202dd  ldarg.0
0x202de  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x202e3  brfalse.s loc_20309
0x202e5  ldarg.1
0x202e6  ldstr    aClass_1// "class"
0x202eb  ldstr    aMsCrmMoneyCurr// "ms-crm-Money-CurrencySymbol ms-crm-Read"...
0x202f0  ldc.i4.0
0x202f1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x202f6  ldarg.1
0x202f7  ldstr    aDisabled// "disabled"
0x202fc  ldstr    aDisabled// "disabled"
0x20301  ldc.i4.0
0x20302  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20307  br.s     loc_2031A
0x20309  ldarg.1
0x2030a  ldstr    aClass_1// "class"
0x2030f  ldstr    aMsCrmMoneyCurr_0// "ms-crm-Money-CurrencySymbol"
0x20314  ldc.i4.0
0x20315  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2031a  ldstr    aId// "id"
0x2031f  ldarg.0
0x20320  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x20325  ldstr    aSym// "_sym"
0x2032a  call     string [mscorlib]System.String::Concat(string, string)
0x2032f  ldarg.1
0x20330  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20335  ldstr    aTitle_2// "title"
0x2033a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2033f  ldstr    aCurrencyTitle// "Currency.Title"
0x20344  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x20349  ldarg.1
0x2034a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2034f  ldarg.1
0x20350  ldstr    aTabindex// "tabindex"
0x20355  ldstr    a1_0// "-1"
0x2035a  ldc.i4.0
0x2035b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x20360  ldarg.0
0x20361  ldfld    string Microsoft.Crm.Application.Components.UI.Money::_currencySymbol
0x20366  ldstr    a1_0// "-1"
0x2036b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20370  brfalse.s loc_203DB
0x20372  ldstr    aStyle_0// "style"
0x20377  ldstr    aDisplayNone_0// "display:none;"
0x2037c  ldarg.1
0x2037d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20382  ldarg.1
0x20383  ldstr    asc_2B7B6// ">"
0x20388  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2038d  ldarg.1
0x2038e  ldarg.0
0x2038f  ldfld    string Microsoft.Crm.Application.Components.UI.Money::_currencySymbol
0x20394  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x20399  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2039e  ldarg.1
0x2039f  ldstr    aSpan// "</span>"
0x203a4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x203a9  ldarg.1
0x203aa  ldstr    aImgSrcImgsErro_1// "<img src=\"/_imgs/error/notif_icn_crit1"...
0x203af  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x203b4  ldstr    aAlt// "alt"
0x203b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x203be  ldstr    aInvalidCurrenc// "Invalid_Currency_GUID"
0x203c3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x203c8  ldarg.1
0x203c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x203ce  ldarg.1
0x203cf  ldstr    asc_4886A// " />"
0x203d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x203d9  br.s     loc_20402
0x203db  ldarg.1
0x203dc  ldstr    asc_2B7B6// ">"
0x203e1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x203e6  ldarg.1
0x203e7  ldarg.0
0x203e8  ldfld    string Microsoft.Crm.Application.Components.UI.Money::_currencySymbol
0x203ed  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x203f2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x203f7  ldarg.1
0x203f8  ldstr    aSpan// "</span>"
0x203fd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20402  ldarg.1
0x20403  ldstr    aTdTd_0// "</td><td>"
0x20408  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2040d  ldarg.0
0x2040e  ldarg.1
0x2040f  call     instance void Microsoft.Crm.Application.Components.UI.Number::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x20414  ldarg.1
0x20415  ldstr    aTdTrTable// "</td></tr></table>"
0x2041a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2041f  ret
```
