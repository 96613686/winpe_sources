# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceImageControl::CreateImageControl

- ea: `0x2b5c0`
- end: `0x2b6fe`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceImageControl::CreateImageControl`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x2b570`

## callees

- `0x17a10`
- `0x2b220`
- `0x2b240`
- `0x2b260`
- `0x2b300`
- `0x2b470`
- `0x2b500`
- `0x2b520`

## pseudocode

```c

```

## disassembly

```asm
0x2b5c0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x2b5c5  dup
0x2b5c6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b5cb  ldstr    aUrl// "url"
0x2b5d0  ldarg.0
0x2b5d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::GetWebResourceUrl()
0x2b5d6  callvirt instance string [mscorlib]System.Object::ToString()
0x2b5db  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b5e0  dup
0x2b5e1  ldarg.0
0x2b5e2  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceImageControl::get_AltText()
0x2b5e7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x2b5ec  dup
0x2b5ed  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b5f2  ldstr    aTabindex// "tabindex"
0x2b5f7  ldarg.0
0x2b5f8  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2b5fd  stloc.0
0x2b5fe  ldloca.s 0
0x2b600  ldstr    aD// "D"
0x2b605  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b60a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2b60f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b614  dup
0x2b615  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b61a  ldstr    aResizemode// "resizeMode"
0x2b61f  ldarg.0
0x2b620  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.WebResourceSizeType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_SizeType()
0x2b625  stloc.1
0x2b626  ldloca.s 1
0x2b628  constrained. [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.WebResourceSizeType
0x2b62e  callvirt instance string [mscorlib]System.Object::ToString()
0x2b633  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b638  dup
0x2b639  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b63e  ldstr    aDesiredheight// "desiredHeight"
0x2b643  ldarg.0
0x2b644  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Height()
0x2b649  stloc.0
0x2b64a  ldloca.s 0
0x2b64c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b651  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2b656  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b65b  dup
0x2b65c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b661  ldstr    aDesiredwidth// "desiredWidth"
0x2b666  ldarg.0
0x2b667  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::get_Width()
0x2b66c  stloc.0
0x2b66d  ldloca.s 0
0x2b66f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b674  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2b679  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b67e  dup
0x2b67f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b684  ldstr    aHorizontalalig// "horizontalAlignment"
0x2b689  ldarg.0
0x2b68a  call     instance valuetype [System.Web]System.Web.UI.WebControls.HorizontalAlign Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceImageControl::get_HorizontalAlignment()
0x2b68f  stloc.2
0x2b690  ldloca.s 2
0x2b692  constrained. [System.Web]System.Web.UI.WebControls.HorizontalAlign
0x2b698  callvirt instance string [mscorlib]System.Object::ToString()
0x2b69d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b6a2  dup
0x2b6a3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b6a8  ldstr    aVerticalalignm// "verticalAlignment"
0x2b6ad  ldarg.0
0x2b6ae  call     instance valuetype [System.Web]System.Web.UI.WebControls.VerticalAlign Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceImageControl::get_VerticalAlignment()
0x2b6b3  stloc.3
0x2b6b4  ldloca.s 3
0x2b6b6  constrained. [System.Web]System.Web.UI.WebControls.VerticalAlign
0x2b6bc  callvirt instance string [mscorlib]System.Object::ToString()
0x2b6c1  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b6c6  dup
0x2b6c7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b6cc  ldstr    aStyle// "style"
0x2b6d1  ldstr    aVisibilityHidd// "visibility:hidden"
0x2b6d6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b6db  dup
0x2b6dc  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2b6e1  ldstr    aTitle// "title"
0x2b6e6  ldarg.0
0x2b6e7  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceImageControl::get_AltText()
0x2b6ec  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2b6f1  dup
0x2b6f2  ldarg.0
0x2b6f3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2b6f8  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2b6fd  ret
```
