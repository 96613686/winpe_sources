# Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml

- ea: `0x1a410`
- end: `0x1a540`
- name: `Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml`
- size: `304`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xf7b0`
- `0x101a0`
- `0x10990`
- `0x11d80`
- `0x1a6b0`
- `0x25ab0`
- `0x27980`
- `0x27be0`
- `0x294e0`

## callees

- `0x1a350`
- `0x1a390`
- `0x1a3f0`
- `0x1a410`
- `0x1a6c0`
- `0x24120`

## pseudocode

```c

```

## disassembly

```asm
0x1a410  ldarg.0
0x1a411  ldfld    bool Microsoft.Crm.Application.Components.UI.ImageStripImage::_isPartOfImageStrip
0x1a416  brfalse  loc_1A4F5
0x1a41b  ldarg.0
0x1a41c  ldfld    class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStripImage::_imgInfo
0x1a421  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x1a426  stloc.0
0x1a427  ldarg.0
0x1a428  call     instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x1a42d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a432  brtrue.s loc_1A446
0x1a434  ldloc.0
0x1a435  ldstr    asc_4C79A// " "
0x1a43a  ldarg.0
0x1a43b  call     instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x1a440  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a445  stloc.0
0x1a446  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a44b  brfalse.s loc_1A4BF
0x1a44d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a452  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1a457  brfalse.s loc_1A4BF
0x1a459  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a45e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1a463  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsInternetExplorer(class [System.Web]System.Web.HttpRequest)
0x1a468  brfalse.s loc_1A4BF
0x1a46a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsHighContrastEnabled()
0x1a46f  brfalse.s loc_1A4BF
0x1a471  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a476  ldstr    aImgSrc0Id1Clas// "<IMG src=\"{0}\" id=\"{1}\" class=\"{2}"...
0x1a47b  ldc.i4.4
0x1a47c  newarr   [mscorlib]System.Object
0x1a481  dup
0x1a482  ldc.i4.0
0x1a483  ldarg.0
0x1a484  ldfld    class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStripImage::_imgInfo
0x1a489  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x1a48e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x1a493  stelem.ref
0x1a494  dup
0x1a495  ldc.i4.1
0x1a496  ldarg.0
0x1a497  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1a49c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a4a1  stelem.ref
0x1a4a2  dup
0x1a4a3  ldc.i4.2
0x1a4a4  ldarg.0
0x1a4a5  call     instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x1a4aa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a4af  stelem.ref
0x1a4b0  dup
0x1a4b1  ldc.i4.3
0x1a4b2  ldarg.0
0x1a4b3  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1a4b8  stelem.ref
0x1a4b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a4be  ret
0x1a4bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a4c4  ldstr    aImgId0SrcImgsI// "<IMG id=\"{0}\" src=\"/_imgs/imagestrip"...
0x1a4c9  ldc.i4.3
0x1a4ca  newarr   [mscorlib]System.Object
0x1a4cf  dup
0x1a4d0  ldc.i4.0
0x1a4d1  ldarg.0
0x1a4d2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1a4d7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a4dc  stelem.ref
0x1a4dd  dup
0x1a4de  ldc.i4.1
0x1a4df  ldloc.0
0x1a4e0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a4e5  stelem.ref
0x1a4e6  dup
0x1a4e7  ldc.i4.2
0x1a4e8  ldarg.0
0x1a4e9  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1a4ee  stelem.ref
0x1a4ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a4f4  ret
0x1a4f5  ldarg.0
0x1a4f6  call     instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x1a4fb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a500  brtrue.s loc_1A513
0x1a502  ldarg.0
0x1a503  ldstr    aClass_1// "class"
0x1a508  ldarg.0
0x1a509  call     instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x1a50e  call     instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::AddExpandoInternal(string name, string value)
0x1a513  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a518  ldstr    aImgId01// "<IMG id=\"{0}\" {1} />"
0x1a51d  ldc.i4.2
0x1a51e  newarr   [mscorlib]System.Object
0x1a523  dup
0x1a524  ldc.i4.0
0x1a525  ldarg.0
0x1a526  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1a52b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1a530  stelem.ref
0x1a531  dup
0x1a532  ldc.i4.1
0x1a533  ldarg.0
0x1a534  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1a539  stelem.ref
0x1a53a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a53f  ret
```
