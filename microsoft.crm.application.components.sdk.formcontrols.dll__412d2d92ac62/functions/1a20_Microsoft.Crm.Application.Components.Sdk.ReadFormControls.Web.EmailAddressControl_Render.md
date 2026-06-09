# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailAddressControl::Render

- ea: `0x1a20`
- end: `0x1b0d`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailAddressControl::Render`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xb120`

## callees

- `0x1230`
- `0x1330`
- `0x1450`
- `0x1a20`

## string_xrefs

- `0x1adb`: `Mscrm.ReadFormUtilities.handleEmailAddressClick(this);return false;`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.0
0x1a21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1a26  brtrue.s loc_1A30
0x1a28  ldarg.0
0x1a29  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1a2e  br.s     loc_1A3B
0x1a30  ldarg.0
0x1a31  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1a36  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1a3b  stloc.0
0x1a3c  ldarg.1
0x1a3d  ldstr    aA// "a"
0x1a42  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1a47  ldarg.1
0x1a48  ldstr    aHref// "href"
0x1a4d  ldstr    asc_3002A// "#"
0x1a52  ldc.i4.0
0x1a53  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a58  ldarg.1
0x1a59  ldstr    aClass// "class"
0x1a5e  ldstr    aMsCrmGridurl// "ms-crm-gridurl"
0x1a63  ldc.i4.0
0x1a64  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a69  ldarg.1
0x1a6a  ldstr    aTarget// "target"
0x1a6f  ldstr    aNew// "_new"
0x1a74  ldc.i4.0
0x1a75  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a7a  ldarg.0
0x1a7b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x1a80  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x1a85  brfalse.s loc_1AC4
0x1a87  ldarg.1
0x1a88  ldstr    aId// "id"
0x1a8d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a92  ldstr    a0L// "{0}_l"
0x1a97  ldc.i4.1
0x1a98  newarr   [mscorlib]System.Object
0x1a9d  dup
0x1a9e  ldc.i4.0
0x1a9f  ldarg.0
0x1aa0  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1aa5  stelem.ref
0x1aa6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1aab  ldc.i4.0
0x1aac  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ab1  ldarg.1
0x1ab2  ldstr    aTabindex// "tabindex"
0x1ab7  ldstr    a1// "-1"
0x1abc  ldc.i4.0
0x1abd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ac2  br.s     loc_1AE6
0x1ac4  ldarg.1
0x1ac5  ldstr    aTabindex// "tabindex"
0x1aca  ldstr    a0// "0"
0x1acf  ldc.i4.0
0x1ad0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ad5  ldarg.1
0x1ad6  ldstr    aOnclick// "onclick"
0x1adb  ldstr    aMscrmReadformu// "Mscrm.ReadFormUtilities.handleEmailAddr"...
0x1ae0  ldc.i4.0
0x1ae1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ae6  ldarg.1
0x1ae7  ldc.i4.s 0x3E
0x1ae9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1aee  ldarg.1
0x1aef  ldarg.0
0x1af0  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x1af5  ldc.i4.0
0x1af6  ldloc.0
0x1af7  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetTemplateBindingHtml(bool, string)
0x1afc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b01  ldarg.1
0x1b02  ldstr    aA// "a"
0x1b07  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x1b0c  ret
```
