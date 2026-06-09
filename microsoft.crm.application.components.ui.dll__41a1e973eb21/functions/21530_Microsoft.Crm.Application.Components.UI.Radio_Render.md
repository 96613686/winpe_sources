# Microsoft.Crm.Application.Components.UI.Radio::Render

- ea: `0x21530`
- end: `0x2160d`
- name: `Microsoft.Crm.Application.Components.UI.Radio::Render`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x21530`
- `0x21610`
- `0x23c20`
- `0x24120`

## string_xrefs

- `0x21582`: `Recommended_Fields_Background_Color`

## pseudocode

```c

```

## disassembly

```asm
0x21530  ldarg.1
0x21531  ldstr    aDivClassMsCrmR// "<div class=\"ms-crm-RadioButton\" id=\""
0x21536  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2153b  ldarg.0
0x2153c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x21541  ldarg.1
0x21542  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0x21547  ldarg.1
0x21548  ldc.i4.s 0x22
0x2154a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x2154f  ldarg.0
0x21550  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x21555  ldstr    aBackgroundColo// "background-color:"
0x2155a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2155f  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x21564  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21569  call     string [mscorlib]System.String::Concat(string, string)
0x2156e  ldstr    asc_3280A// ""
0x21573  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x21578  ldstr    aBackgroundColo// "background-color:"
0x2157d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21582  ldstr    aRecommendedFie// "Recommended_Fields_Background_Color"
0x21587  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2158c  call     string [mscorlib]System.String::Concat(string, string)
0x21591  ldstr    asc_3280A// ""
0x21596  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x2159b  stloc.0
0x2159c  ldarg.0
0x2159d  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x215a2  ldstr    aBackgroundColo// "background-color:"
0x215a7  ldc.i4.4
0x215a8  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x215ad  ldc.i4.m1
0x215ae  beq.s    loc_215D8
0x215b0  ldarg.0
0x215b1  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x215b6  ldstr    aBackgroundColo// "background-color:"
0x215bb  ldc.i4.4
0x215bc  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x215c1  stloc.1
0x215c2  ldarg.0
0x215c3  ldarg.0
0x215c4  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x215c9  ldloc.1
0x215ca  ldc.i4.s 0x11
0x215cc  add
0x215cd  ldc.i4.7
0x215ce  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x215d3  stfld    string Microsoft.Crm.Application.Components.UI.Radio::_childFieldColor
0x215d8  ldarg.1
0x215d9  ldloc.0
0x215da  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x215df  ldarg.0
0x215e0  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x215e5  brfalse.s loc_215F2
0x215e7  ldarg.1
0x215e8  ldstr    aDisabled_0// " disabled"
0x215ed  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x215f2  ldarg.1
0x215f3  ldc.i4.s 0x3E
0x215f5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x215fa  ldarg.0
0x215fb  ldarg.1
0x215fc  call     instance void Microsoft.Crm.Application.Components.UI.Radio::RenderOptions(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x21601  ldarg.1
0x21602  ldstr    aDiv// "</div>"
0x21607  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2160c  ret
```
