# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButton

- ea: `0x172f0`
- end: `0x174c8`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControl::WriteButton`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x17230`

## callees

- `0x15280`
- `0x152d0`
- `0x152f0`
- `0x15310`
- `0x15520`
- `0x15540`
- `0x15560`
- `0x15580`
- `0x155a0`
- `0x155c0`

## pseudocode

```c

```

## disassembly

```asm
0x172f0  ldc.i4.s 0x4C
0x172f2  stloc.2
0x172f3  ldloca.s 2
0x172f5  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x172fb  callvirt instance string [mscorlib]System.Object::ToString()
0x17300  ldarg.2
0x17301  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor(string htmlTagName, class [System.Web]System.Web.UI.HtmlTextWriter htmlTextWriter)
0x17306  dup
0x17307  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x1730c  ldc.i4.s 0xA
0x1730e  stloc.3
0x1730f  ldloca.s 3
0x17311  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x17317  callvirt instance string [mscorlib]System.Object::ToString()
0x1731c  ldarg.1
0x1731d  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ClassName()
0x17322  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17327  dup
0x17328  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x1732d  ldc.i4.s 0x11
0x1732f  stloc.3
0x17330  ldloca.s 3
0x17332  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x17338  callvirt instance string [mscorlib]System.Object::ToString()
0x1733d  ldarg.1
0x1733e  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonId()
0x17343  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17348  dup
0x17349  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::Write()
0x1734e  ldc.i4.1
0x1734f  stloc.2
0x17350  ldloca.s 2
0x17352  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x17358  callvirt instance string [mscorlib]System.Object::ToString()
0x1735d  ldarg.2
0x1735e  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor(string htmlTagName, class [System.Web]System.Web.UI.HtmlTextWriter htmlTextWriter)
0x17363  dup
0x17364  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17369  ldc.i4.s 0x11
0x1736b  stloc.3
0x1736c  ldloca.s 3
0x1736e  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x17374  callvirt instance string [mscorlib]System.Object::ToString()
0x17379  ldarg.1
0x1737a  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonId()
0x1737f  ldstr    aHref_0// "_href"
0x17384  call     string [mscorlib]System.String::Concat(string, string)
0x17389  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1738e  dup
0x1738f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17394  ldc.i4.s 0x10
0x17396  stloc.3
0x17397  ldloca.s 3
0x17399  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1739f  callvirt instance string [mscorlib]System.Object::ToString()
0x173a4  ldarg.1
0x173a5  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonImageHref()
0x173aa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x173af  dup
0x173b0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x173b5  ldstr    aAriaLabel// "aria-label"
0x173ba  ldarg.1
0x173bb  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonImageAltText()
0x173c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x173c5  dup
0x173c6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::Write()
0x173cb  ldarg.1
0x173cc  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonImageBase()
0x173d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x173d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x173db  stloc.0
0x173dc  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x173e1  ldloc.0
0x173e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x173e7  stloc.1
0x173e8  ldc.i4.s 0x2E
0x173ea  stloc.2
0x173eb  ldloca.s 2
0x173ed  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x173f3  callvirt instance string [mscorlib]System.Object::ToString()
0x173f8  ldarg.2
0x173f9  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::.ctor(string htmlTagName, class [System.Web]System.Web.UI.HtmlTextWriter htmlTextWriter)
0x173fe  dup
0x173ff  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17404  ldc.i4.s 0x11
0x17406  stloc.3
0x17407  ldloca.s 3
0x17409  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1740f  callvirt instance string [mscorlib]System.Object::ToString()
0x17414  ldarg.1
0x17415  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonId()
0x1741a  ldstr    aImg_0// "_img"
0x1741f  call     string [mscorlib]System.String::Concat(string, string)
0x17424  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17429  dup
0x1742a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x1742f  ldc.i4.s 0xA
0x17431  stloc.3
0x17432  ldloca.s 3
0x17434  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1743a  callvirt instance string [mscorlib]System.Object::ToString()
0x1743f  ldloc.1
0x17440  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x17445  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1744a  dup
0x1744b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17450  ldc.i4.s 0x1E
0x17452  stloc.3
0x17453  ldloca.s 3
0x17455  constrained. [System.Web]System.Web.UI.HtmlTextWriterAttribute
0x1745b  callvirt instance string [mscorlib]System.Object::ToString()
0x17460  ldloc.1
0x17461  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x17466  callvirt instance string [mscorlib]System.Object::ToString()
0x1746b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17470  dup
0x17471  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x17476  ldstr    aAlt// "alt"
0x1747b  ldarg.1
0x1747c  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonImageAltText()
0x17481  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x17486  dup
0x17487  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x1748c  ldstr    aTitle// "title"
0x17491  ldarg.1
0x17492  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonImageTitle()
0x17497  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1749c  dup
0x1749d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::get_Attributes()
0x174a2  ldstr    aImgbase// "imgbase"
0x174a7  ldarg.1
0x174a8  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlToolbarButtonParameters::get_ButtonImageBase()
0x174ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x174b2  dup
0x174b3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::Write()
0x174b8  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::WriteEndTag()
0x174bd  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::WriteEndTag()
0x174c2  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmControlHtmlBuilder::WriteEndTag()
0x174c7  ret
```
