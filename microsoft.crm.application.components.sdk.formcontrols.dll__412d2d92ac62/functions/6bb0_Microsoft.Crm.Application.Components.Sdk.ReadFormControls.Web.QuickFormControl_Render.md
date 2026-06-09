# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::Render

- ea: `0x6bb0`
- end: `0x6d76`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::Render`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x6910`
- `0x6980`
- `0x6a20`
- `0x6b40`
- `0x6bb0`
- `0x6d80`
- `0x6e10`
- `0x72c0`

## string_xrefs

- `0x6bc6`: `The QuickFormControl wasnt added to the ASP.NET control hierarchy, which resulted in CreateChildControls() not getting invoked. Make sure that the QF control is added to the container controls' .Controls collection. This jquery template cannot be initialised : {0}`
- `0x6c58`: `QuickFormControl.RenderChildren resulted in a null string. Make sure that QuickFormControl.CreateChildControls() is getting invoked correctly.`
- `0x6ce1`: `template_name`

## pseudocode

```c

```

## disassembly

```asm
0x6bb0  ldarg.0
0x6bb1  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_quickFormDescriptor
0x6bb6  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor>::get_Value()
0x6bbb  brfalse  loc_6D75
0x6bc0  ldarg.0
0x6bc1  ldfld    bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_childControlsCreated
0x6bc6  ldstr    aTheQuickformco// "The QuickFormControl wasnt added to the"...
0x6bcb  ldc.i4.1
0x6bcc  newarr   [mscorlib]System.Object
0x6bd1  dup
0x6bd2  ldc.i4.0
0x6bd3  ldarg.0
0x6bd4  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_jqueryTemplateName
0x6bd9  stelem.ref
0x6bda  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x6bdf  ldarg.0
0x6be0  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_UniqueId()
0x6be5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6bea  ldc.i4.0
0x6beb  ceq
0x6bed  ldstr    aTheControlUniq// "The control unique Id input parameter f"...
0x6bf2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6bf7  ldarg.0
0x6bf8  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::UpdateTabCount()
0x6bfd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6c02  stloc.0
0x6c03  ldloc.0
0x6c04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c09  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x6c0e  stloc.2
0x6c0f  ldloc.2
0x6c10  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x6c15  stloc.3
0x6c16  ldarg.0
0x6c17  ldloc.3
0x6c18  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::RenderAttributesOnRootDiv(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x6c1d  ldloc.3
0x6c1e  ldc.i4.s 0x19
0x6c20  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x6c25  ldarg.0
0x6c26  ldloc.3
0x6c27  callvirt instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0x6c2c  ldloc.3
0x6c2d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x6c32  leave.s  loc_6C48
0x6c34  ldloc.3
0x6c35  brfalse.s loc_6C3D
0x6c37  ldloc.3
0x6c38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c3d  endfinally
0x6c3e  ldloc.2
0x6c3f  brfalse.s loc_6C47
0x6c41  ldloc.2
0x6c42  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c47  endfinally
0x6c48  ldloc.0
0x6c49  callvirt instance string [mscorlib]System.Object::ToString()
0x6c4e  stloc.1
0x6c4f  ldloc.1
0x6c50  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6c55  ldc.i4.0
0x6c56  ceq
0x6c58  ldstr    aQuickformcontr// "QuickFormControl.RenderChildren resulte"...
0x6c5d  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x6c62  ldarg.0
0x6c63  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x6c68  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_JQueryTemplates()
0x6c6d  ldarg.0
0x6c6e  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_jqueryTemplateName
0x6c73  ldloc.1
0x6c74  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x6c79  ldarg.0
0x6c7a  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_IsTurboForm()
0x6c7f  brtrue.s loc_6C99
0x6c81  ldarg.1
0x6c82  ldstr    aForData0Tmpl1// "{{{{for #data.{0} tmpl=\"#{1}\" /}}}}"
0x6c87  ldarg.0
0x6c88  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_CustomDataObjectKey()
0x6c8d  ldarg.0
0x6c8e  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_jqueryTemplateName
0x6c93  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x6c98  ret
0x6c99  ldarg.0
0x6c9a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x6c9f  ldstr    asc_359D6// "_"
0x6ca4  ldarg.0
0x6ca5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormId()
0x6caa  stloc.s  8
0x6cac  ldloca.s 8
0x6cae  constrained. [mscorlib]System.Guid
0x6cb4  callvirt instance string [mscorlib]System.Object::ToString()
0x6cb9  ldstr    a0_0// "_{0}"
0x6cbe  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x6cc3  stloc.s  4
0x6cc5  ldloc.s  4
0x6cc7  ldc.i4.s 0x2D
0x6cc9  ldc.i4.s 0x5F
0x6ccb  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x6cd0  stloc.s  4
0x6cd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cd7  ldloc.s  4
0x6cd9  ldc.i4.1
0x6cda  newarr   [mscorlib]System.Object
0x6cdf  dup
0x6ce0  ldc.i4.0
0x6ce1  ldstr    aTemplateName// "template_name"
0x6ce6  stelem.ref
0x6ce7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6cec  stloc.s  5
0x6cee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cf3  ldloc.s  4
0x6cf5  ldc.i4.1
0x6cf6  newarr   [mscorlib]System.Object
0x6cfb  dup
0x6cfc  ldc.i4.0
0x6cfd  ldstr    aUniqueId// "unique_id"
0x6d02  stelem.ref
0x6d03  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6d08  stloc.s  6
0x6d0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6d0f  ldloc.s  4
0x6d11  ldc.i4.1
0x6d12  newarr   [mscorlib]System.Object
0x6d17  dup
0x6d18  ldc.i4.0
0x6d19  ldstr    aFormDataId// "form_data_id"
0x6d1e  stelem.ref
0x6d1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6d24  stloc.s  7
0x6d26  ldarg.0
0x6d27  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x6d2c  ldloc.s  5
0x6d2e  ldarg.0
0x6d2f  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_jqueryTemplateName
0x6d34  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d39  ldarg.0
0x6d3a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x6d3f  ldloc.s  6
0x6d41  ldarg.0
0x6d42  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_uniqueId
0x6d47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d4c  ldarg.0
0x6d4d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x6d52  ldloc.s  7
0x6d54  ldarg.0
0x6d55  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::get_FormDataEntityId()
0x6d5a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x6d5f  ldarg.1
0x6d60  ldstr    aDivId0Div// "<div id=\"{0}\"></div>"
0x6d65  ldarg.0
0x6d66  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.QuickFormControl::_jqueryTemplateName
0x6d6b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6d70  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x6d75  ret
```
