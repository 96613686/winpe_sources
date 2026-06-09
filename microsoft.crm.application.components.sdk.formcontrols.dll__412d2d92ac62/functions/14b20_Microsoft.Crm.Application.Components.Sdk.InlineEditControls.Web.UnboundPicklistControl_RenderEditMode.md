# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundPicklistControl::RenderEditMode

- ea: `0x14b20`
- end: `0x14d00`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundPicklistControl::RenderEditMode`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x11540`
- `0x115d0`
- `0x14b20`

## string_xrefs

- `0x14bd4`: `ms-crm-SelectBox ms-crm-Inline-OptionSet-AutoOpen ms-crm-Inline-HideByZeroHeight-Ie7`

## pseudocode

```c

```

## disassembly

```asm
0x14b20  ldarg.1
0x14b21  ldstr    aDiv// "div"
0x14b26  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x14b2b  ldarg.1
0x14b2c  ldstr    aClass// "class"
0x14b31  ldstr    aMsCrmInlineEdi_7// "ms-crm-Inline-Edit ms-crm-Inline-Option"...
0x14b36  ldc.i4.0
0x14b37  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14b3c  ldarg.1
0x14b3d  ldstr    aStyle// "style"
0x14b42  ldstr    aDisplayNonePos// "display: none; position: relative;"
0x14b47  ldc.i4.0
0x14b48  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14b4d  ldarg.1
0x14b4e  ldc.i4.s 0x3E
0x14b50  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x14b55  ldarg.1
0x14b56  ldstr    aSelect// "select"
0x14b5b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x14b60  ldstr    aId// "id"
0x14b65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14b6a  ldstr    a0I// "{0}_i"
0x14b6f  ldc.i4.1
0x14b70  newarr   [mscorlib]System.Object
0x14b75  dup
0x14b76  ldc.i4.0
0x14b77  ldarg.0
0x14b78  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x14b7d  stelem.ref
0x14b7e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14b83  ldarg.1
0x14b84  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14b89  ldarg.1
0x14b8a  ldstr    aAttrname// "attrname"
0x14b8f  ldarg.0
0x14b90  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x14b95  ldc.i4.0
0x14b96  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14b9b  ldarg.1
0x14b9c  ldstr    aDefaultselecte// "defaultselected"
0x14ba1  ldstr    aNull// "null"
0x14ba6  ldc.i4.0
0x14ba7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14bac  ldarg.1
0x14bad  ldstr    aAttrpriv// "attrpriv"
0x14bb2  ldstr    a7// "7"
0x14bb7  ldc.i4.0
0x14bb8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14bbd  ldarg.1
0x14bbe  ldstr    aTitle// "title"
0x14bc3  ldstr    asc_30804// ""
0x14bc8  ldc.i4.0
0x14bc9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14bce  ldarg.1
0x14bcf  ldstr    aClass// "class"
0x14bd4  ldstr    aMsCrmSelectbox_1// "ms-crm-SelectBox ms-crm-Inline-OptionSe"...
0x14bd9  ldc.i4.0
0x14bda  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14bdf  ldstr    aAriaLabelledby// "aria-labelledby"
0x14be4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14be9  ldstr    a0C0W// "{0}_c {0}_w"
0x14bee  ldc.i4.1
0x14bef  newarr   [mscorlib]System.Object
0x14bf4  dup
0x14bf5  ldc.i4.0
0x14bf6  ldarg.0
0x14bf7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x14bfc  stelem.ref
0x14bfd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14c02  ldarg.1
0x14c03  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x14c08  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x14c0d  stloc.0
0x14c0e  ldarg.0
0x14c0f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::get_OptionSetId()
0x14c14  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14c19  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14c1e  brfalse  loc_14CE1
0x14c23  ldloc.0
0x14c24  ldarg.0
0x14c25  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::get_OptionSetId()
0x14c2a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSet(valuetype [mscorlib]System.Guid)
0x14c2f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionsInDisplayOrder()
0x14c34  stloc.1
0x14c35  ldarg.1
0x14c36  ldstr    aSize// "size"
0x14c3b  ldloc.1
0x14c3c  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x14c41  stloc.2
0x14c42  ldloca.s 2
0x14c44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14c49  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x14c4e  ldc.i4.0
0x14c4f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x14c54  ldarg.1
0x14c55  ldc.i4.s 0x3E
0x14c57  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x14c5c  ldloc.1
0x14c5d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x14c62  stloc.3
0x14c63  br.s     loc_14CCD
0x14c65  ldloc.3
0x14c66  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x14c6b  stloc.s  4
0x14c6d  ldloc.s  4
0x14c6f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x14c74  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x14c79  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x14c7e  ldc.i4.0
0x14c7f  bgt.s    loc_14C96
0x14c81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14c86  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationLanguageId()
0x14c8b  stloc.s  6
0x14c8d  ldloca.s 6
0x14c8f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x14c94  br.s     loc_14CA0
0x14c96  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x14c9b  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x14ca0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14ca5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14caa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x14caf  stloc.s  5
0x14cb1  ldarg.1
0x14cb2  ldloc.s  5
0x14cb4  ldloc.s  4
0x14cb6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x14cbb  stloc.2
0x14cbc  ldloca.s 2
0x14cbe  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x14cc3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x14cc8  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderOptionValue(class [System.Web]System.Web.UI.HtmlTextWriter writer, string displayText, string displayValue)
0x14ccd  ldloc.3
0x14cce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14cd3  brtrue.s loc_14C65
0x14cd5  leave.s  loc_14CE9
0x14cd7  ldloc.3
0x14cd8  brfalse.s loc_14CE0
0x14cda  ldloc.3
0x14cdb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ce0  endfinally
0x14ce1  ldarg.1
0x14ce2  ldc.i4.s 0x3E
0x14ce4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x14ce9  ldarg.1
0x14cea  ldstr    aSelect// "select"
0x14cef  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x14cf4  ldarg.1
0x14cf5  ldstr    aDiv// "div"
0x14cfa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x14cff  ret
```
