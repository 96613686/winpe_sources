# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.PhoneNumberControl::Render

- ea: `0x8580`
- end: `0x8699`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.PhoneNumberControl::Render`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x12970`

## callees

- `0x1230`
- `0x1330`
- `0x1450`
- `0x8580`

## string_xrefs

- `0x8643`: `Mscrm.ReadFormUtilities.handlePhoneNumberClick(this);return false;`

## pseudocode

```c

```

## disassembly

```asm
0x8580  ldarg.0
0x8581  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8586  brtrue.s loc_8590
0x8588  ldarg.0
0x8589  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x858e  br.s     loc_859B
0x8590  ldarg.0
0x8591  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x8596  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x859b  stloc.0
0x859c  ldarg.1
0x859d  ldstr    aA// "a"
0x85a2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x85a7  ldarg.1
0x85a8  ldstr    aHref// "href"
0x85ad  ldstr    asc_3002A// "#"
0x85b2  ldc.i4.0
0x85b3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x85b8  ldarg.1
0x85b9  ldstr    aClass// "class"
0x85be  ldstr    aMsCrmGridurlMs// "ms-crm-gridurl ms-crm-Phone"
0x85c3  ldc.i4.0
0x85c4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x85c9  ldarg.0
0x85ca  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x85cf  brfalse.s loc_861B
0x85d1  ldarg.0
0x85d2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x85d7  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x85dc  brfalse.s loc_861B
0x85de  ldarg.1
0x85df  ldstr    aId// "id"
0x85e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85e9  ldstr    a0L// "{0}_l"
0x85ee  ldc.i4.1
0x85ef  newarr   [mscorlib]System.Object
0x85f4  dup
0x85f5  ldc.i4.0
0x85f6  ldarg.0
0x85f7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x85fc  stelem.ref
0x85fd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8602  ldc.i4.0
0x8603  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8608  ldarg.1
0x8609  ldstr    aTabindex// "tabindex"
0x860e  ldstr    a1// "-1"
0x8613  ldc.i4.0
0x8614  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8619  br.s     loc_864E
0x861b  ldarg.1
0x861c  ldstr    aTarget// "target"
0x8621  ldstr    aNew// "_new"
0x8626  ldc.i4.0
0x8627  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x862c  ldarg.1
0x862d  ldstr    aTabindex// "tabindex"
0x8632  ldstr    a0// "0"
0x8637  ldc.i4.0
0x8638  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x863d  ldarg.1
0x863e  ldstr    aOnclick// "onclick"
0x8643  ldstr    aMscrmReadformu_3// "Mscrm.ReadFormUtilities.handlePhoneNumb"...
0x8648  ldc.i4.0
0x8649  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x864e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8653  ldstr    aPhonenumbercon// "PhoneNumberControl_ToolTip"
0x8658  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x865d  stloc.1
0x865e  ldloc.1
0x865f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8664  stloc.1
0x8665  ldarg.1
0x8666  ldstr    aTitle// "title"
0x866b  ldloc.1
0x866c  ldc.i4.0
0x866d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x8672  ldarg.1
0x8673  ldc.i4.s 0x3E
0x8675  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x867a  ldarg.1
0x867b  ldarg.0
0x867c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TemplateRenderer()
0x8681  ldc.i4.0
0x8682  ldloc.0
0x8683  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IBindingTemplateRenderer::GetTemplateBindingHtml(bool, string)
0x8688  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x868d  ldarg.1
0x868e  ldstr    aA// "a"
0x8693  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x8698  ret
```
