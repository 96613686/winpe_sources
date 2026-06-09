# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.UrlControl::Render

- ea: `0x8430`
- end: `0x8525`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.UrlControl::Render`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x128e0`

## callees

- `0x1230`
- `0x1330`
- `0x1450`
- `0x8430`

## string_xrefs

- `0x84f3`: `Mscrm.ReadFormUtilities.handleUrlClick(this);return false;`

## pseudocode

```c

```

## disassembly

```asm
0x8430  ldarg.0
0x8431  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8436  brtrue.s loc_8440
0x8438  ldarg.0
0x8439  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x843e  br.s     loc_844B
0x8440  ldarg.0
0x8441  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8446  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x844b  stloc.0
0x844c  ldarg.1
0x844d  ldstr    aA// "a"
0x8452  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x8457  ldarg.1
0x8458  ldstr    aHref// "href"
0x845d  ldstr    asc_3002A// "#"
0x8462  ldc.i4.0
0x8463  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8468  ldarg.1
0x8469  ldstr    aClass// "class"
0x846e  ldstr    aMsCrmGridurl// "ms-crm-gridurl"
0x8473  ldc.i4.0
0x8474  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8479  ldarg.1
0x847a  ldstr    aTarget// "target"
0x847f  ldstr    aNew// "_new"
0x8484  ldc.i4.0
0x8485  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x848a  ldarg.0
0x848b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x8490  brfalse.s loc_84DC
0x8492  ldarg.0
0x8493  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x8498  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x849d  brfalse.s loc_84DC
0x849f  ldarg.1
0x84a0  ldstr    aId// "id"
0x84a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84aa  ldstr    a0L// "{0}_l"
0x84af  ldc.i4.1
0x84b0  newarr   [mscorlib]System.Object
0x84b5  dup
0x84b6  ldc.i4.0
0x84b7  ldarg.0
0x84b8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x84bd  stelem.ref
0x84be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x84c3  ldc.i4.0
0x84c4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x84c9  ldarg.1
0x84ca  ldstr    aTabindex// "tabindex"
0x84cf  ldstr    a1// "-1"
0x84d4  ldc.i4.0
0x84d5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x84da  br.s     loc_84FE
0x84dc  ldarg.1
0x84dd  ldstr    aTabindex// "tabindex"
0x84e2  ldstr    a0// "0"
0x84e7  ldc.i4.0
0x84e8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x84ed  ldarg.1
0x84ee  ldstr    aOnclick// "onclick"
0x84f3  ldstr    aMscrmReadformu_2// "Mscrm.ReadFormUtilities.handleUrlClick("...
0x84f8  ldc.i4.0
0x84f9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x84fe  ldarg.1
0x84ff  ldc.i4.s 0x3E
0x8501  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x8506  ldarg.1
0x8507  ldarg.0
0x8508  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x850d  ldc.i4.0
0x850e  ldloc.0
0x850f  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetTemplateBindingHtml(bool, string)
0x8514  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8519  ldarg.1
0x851a  ldstr    aA// "a"
0x851f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x8524  ret
```
