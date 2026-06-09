# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundEntityPicklistControl::RenderEditMode

- ea: `0x138f0`
- end: `0x13ad9`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.UnboundEntityPicklistControl::RenderEditMode`
- size: `489`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x11540`
- `0x115d0`
- `0x138f0`

## string_xrefs

- `0x139b5`: `ms-crm-SelectBox ms-crm-Inline-OptionSet-AutoOpen ms-crm-Inline-HideByZeroHeight-Ie7`

## pseudocode

```c

```

## disassembly

```asm
0x138f0  ldarg.1
0x138f1  ldstr    aDiv// "div"
0x138f6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x138fb  ldarg.1
0x138fc  ldstr    aClass// "class"
0x13901  ldstr    aMsCrmInlineEdi_7// "ms-crm-Inline-Edit ms-crm-Inline-Option"...
0x13906  ldc.i4.0
0x13907  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1390c  ldarg.1
0x1390d  ldstr    aStyle// "style"
0x13912  ldstr    aDisplayNonePos// "display: none; position: relative;"
0x13917  ldc.i4.0
0x13918  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1391d  ldarg.1
0x1391e  ldc.i4.s 0x3E
0x13920  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x13925  ldarg.1
0x13926  ldstr    aSelect// "select"
0x1392b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x13930  ldstr    aId// "id"
0x13935  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1393a  ldstr    a0I// "{0}_i"
0x1393f  ldc.i4.1
0x13940  newarr   [mscorlib]System.Object
0x13945  dup
0x13946  ldc.i4.0
0x13947  ldarg.0
0x13948  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1394d  stelem.ref
0x1394e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13953  ldarg.1
0x13954  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13959  ldarg.1
0x1395a  ldstr    aAttrname// "attrname"
0x1395f  ldarg.0
0x13960  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x13965  ldc.i4.0
0x13966  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1396b  ldarg.1
0x1396c  ldstr    aDefaultselecte// "defaultselected"
0x13971  ldstr    aNull// "null"
0x13976  ldc.i4.0
0x13977  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1397c  ldarg.1
0x1397d  ldstr    aAttrpriv// "attrpriv"
0x13982  ldstr    a7// "7"
0x13987  ldc.i4.0
0x13988  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1398d  ldarg.1
0x1398e  ldstr    aTitle// "title"
0x13993  ldstr    asc_30804// ""
0x13998  ldc.i4.0
0x13999  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1399e  ldarg.1
0x1399f  ldstr    aTabindex// "tabindex"
0x139a4  ldstr    a1// "-1"
0x139a9  ldc.i4.0
0x139aa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x139af  ldarg.1
0x139b0  ldstr    aClass// "class"
0x139b5  ldstr    aMsCrmSelectbox_1// "ms-crm-SelectBox ms-crm-Inline-OptionSe"...
0x139ba  ldc.i4.0
0x139bb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x139c0  ldstr    aAriaLabelledby// "aria-labelledby"
0x139c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x139ca  ldstr    a0C0W// "{0}_c {0}_w"
0x139cf  ldc.i4.1
0x139d0  newarr   [mscorlib]System.Object
0x139d5  dup
0x139d6  ldc.i4.0
0x139d7  ldarg.0
0x139d8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x139dd  stelem.ref
0x139de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x139e3  ldarg.1
0x139e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x139e9  ldarg.1
0x139ea  ldc.i4.s 0x3E
0x139ec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x139f1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x139f6  stloc.0
0x139f7  ldarg.0
0x139f8  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::get_OptionSetId()
0x139fd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13a02  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13a07  brfalse  loc_13AC2
0x13a0c  ldloc.0
0x13a0d  ldarg.0
0x13a0e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::get_OptionSetId()
0x13a13  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSet(valuetype [mscorlib]System.Guid)
0x13a18  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionsInDisplayOrder()
0x13a1d  stloc.1
0x13a1e  ldarg.1
0x13a1f  ldstr    aSize// "size"
0x13a24  ldloc.1
0x13a25  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x13a2a  stloc.2
0x13a2b  ldloca.s 2
0x13a2d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13a32  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x13a37  ldc.i4.0
0x13a38  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x13a3d  ldloc.1
0x13a3e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x13a43  stloc.3
0x13a44  br.s     loc_13AAE
0x13a46  ldloc.3
0x13a47  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x13a4c  stloc.s  4
0x13a4e  ldloc.s  4
0x13a50  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x13a55  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x13a5a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x13a5f  ldc.i4.0
0x13a60  bgt.s    loc_13A77
0x13a62  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13a67  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationLanguageId()
0x13a6c  stloc.s  6
0x13a6e  ldloca.s 6
0x13a70  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x13a75  br.s     loc_13A81
0x13a77  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x13a7c  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x13a81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13a86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13a8b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x13a90  stloc.s  5
0x13a92  ldarg.1
0x13a93  ldloc.s  5
0x13a95  ldloc.s  4
0x13a97  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x13a9c  stloc.2
0x13a9d  ldloca.s 2
0x13a9f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x13aa4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x13aa9  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderOptionValue(class [System.Web]System.Web.UI.HtmlTextWriter writer, string displayText, string displayValue)
0x13aae  ldloc.3
0x13aaf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13ab4  brtrue.s loc_13A46
0x13ab6  leave.s  loc_13AC2
0x13ab8  ldloc.3
0x13ab9  brfalse.s loc_13AC1
0x13abb  ldloc.3
0x13abc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13ac1  endfinally
0x13ac2  ldarg.1
0x13ac3  ldstr    aSelect// "select"
0x13ac8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x13acd  ldarg.1
0x13ace  ldstr    aDiv// "div"
0x13ad3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x13ad8  ret
```
