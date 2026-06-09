# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.TickerControl::Render

- ea: `0x82d0`
- end: `0x8402`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.TickerControl::Render`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x12080`

## callees

- `0x1230`
- `0x1330`
- `0x1450`
- `0x82d0`

## string_xrefs

- `0x8388`: `http://go.microsoft.com/fwlink?linkid=8506&clcid=`

## pseudocode

```c

```

## disassembly

```asm
0x82d0  ldarg.0
0x82d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x82d6  brtrue.s loc_82E0
0x82d8  ldarg.0
0x82d9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x82de  br.s     loc_82EB
0x82e0  ldarg.0
0x82e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x82e6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x82eb  stloc.0
0x82ec  ldarg.0
0x82ed  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x82f2  ldc.i4.0
0x82f3  ldloc.0
0x82f4  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetTemplateBindingHtml(bool, string)
0x82f9  stloc.1
0x82fa  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_Instance()
0x82ff  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_ShowStockSymbolAsLink()
0x8304  brfalse  loc_83E3
0x8309  ldarg.1
0x830a  ldstr    aA// "a"
0x830f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x8314  ldarg.1
0x8315  ldstr    aClass// "class"
0x831a  ldstr    aMsCrmGridurl// "ms-crm-gridurl"
0x831f  ldc.i4.0
0x8320  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8325  ldarg.1
0x8326  ldstr    aTarget// "target"
0x832b  ldstr    aNew// "_new"
0x8330  ldc.i4.0
0x8331  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8336  ldarg.0
0x8337  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x833c  brfalse.s loc_8388
0x833e  ldarg.0
0x833f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x8344  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x8349  brfalse.s loc_8388
0x834b  ldarg.1
0x834c  ldstr    aId// "id"
0x8351  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8356  ldstr    a0L// "{0}_l"
0x835b  ldc.i4.1
0x835c  newarr   [mscorlib]System.Object
0x8361  dup
0x8362  ldc.i4.0
0x8363  ldarg.0
0x8364  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x8369  stelem.ref
0x836a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x836f  ldc.i4.0
0x8370  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8375  ldarg.1
0x8376  ldstr    aTabindex// "tabindex"
0x837b  ldstr    a1// "-1"
0x8380  ldc.i4.0
0x8381  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8386  br.s     loc_83DB
0x8388  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink?linkid=8"...
0x838d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8392  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x8397  box      [mscorlib]System.Int32
0x839c  ldstr    aSymbol0Q0// "&Symbol={0}&q={0}"
0x83a1  call     string [mscorlib]System.String::Concat(object, object, object)
0x83a6  stloc.2
0x83a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83ac  ldloc.2
0x83ad  ldc.i4.1
0x83ae  newarr   [mscorlib]System.Object
0x83b3  dup
0x83b4  ldc.i4.0
0x83b5  ldloc.1
0x83b6  stelem.ref
0x83b7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x83bc  stloc.3
0x83bd  ldarg.1
0x83be  ldstr    aHref// "href"
0x83c3  ldloc.3
0x83c4  ldc.i4.0
0x83c5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x83ca  ldarg.1
0x83cb  ldstr    aTabindex// "tabindex"
0x83d0  ldstr    a0// "0"
0x83d5  ldc.i4.0
0x83d6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x83db  ldarg.1
0x83dc  ldc.i4.s 0x3E
0x83de  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x83e3  ldarg.1
0x83e4  ldloc.1
0x83e5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x83ea  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_Instance()
0x83ef  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_ShowStockSymbolAsLink()
0x83f4  brfalse.s loc_8401
0x83f6  ldarg.1
0x83f7  ldstr    aA// "a"
0x83fc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x8401  ret
```
