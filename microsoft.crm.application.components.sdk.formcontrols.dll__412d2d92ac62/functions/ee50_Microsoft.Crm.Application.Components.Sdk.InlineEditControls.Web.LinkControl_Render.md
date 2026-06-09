# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::Render

- ea: `0xee50`
- end: `0xf01f`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::Render`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1290`
- `0x2b50`
- `0x2b70`
- `0xed10`
- `0xee00`
- `0xee20`
- `0xee50`
- `0xf020`

## string_xrefs

- `0xee6f`: `ms-crm-LinkControl-content`
- `0xeed7`: `data-linkcontrolstart`
- `0xef0a`: `linkControlLabel`
- `0xef26`: `isEligibleForMarkComplete`
- `0xef76`: `linkcontroldefinitionid`

## pseudocode

```c

```

## disassembly

```asm
0xee50  ldarg.1
0xee51  ldc.i4.s 0x11
0xee53  ldarg.0
0xee54  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xee59  ldstr    aFlyoutloadinga// "_flyoutLoadingArea"
0xee5e  call     string [mscorlib]System.String::Concat(string, string)
0xee63  ldc.i4.0
0xee64  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0xee69  ldarg.1
0xee6a  ldstr    aClass// "class"
0xee6f  ldstr    aMsCrmLinkcontr// "ms-crm-LinkControl-content"
0xee74  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string)
0xee79  ldarg.1
0xee7a  ldc.i4.s 0x19
0xee7c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xee81  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xee86  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xee8b  stloc.1
0xee8c  ldloc.1
0xee8d  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0xee92  stloc.2
0xee93  ldarg.0
0xee94  ldloc.2
0xee95  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::AddContent(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xee9a  ldarg.1
0xee9b  ldloc.1
0xee9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.IO.StringWriter::GetStringBuilder()
0xeea1  callvirt instance string [mscorlib]System.Object::ToString()
0xeea6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xeeab  leave.s  loc_EEC1
0xeead  ldloc.2
0xeeae  brfalse.s loc_EEB6
0xeeb0  ldloc.2
0xeeb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeeb6  endfinally
0xeeb7  ldloc.1
0xeeb8  brfalse.s loc_EEC0
0xeeba  ldloc.1
0xeebb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeec0  endfinally
0xeec1  ldarg.1
0xeec2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xeec7  ldarg.1
0xeec8  ldc.i4.s 0x11
0xeeca  ldarg.0
0xeecb  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xeed0  ldc.i4.0
0xeed1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0xeed6  ldarg.1
0xeed7  ldstr    aDataLinkcontro// "data-linkcontrolstart"
0xeedc  ldstr    a1_0// "1"
0xeee1  ldc.i4.0
0xeee2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0xeee7  ldarg.1
0xeee8  ldc.i4.s 0x20
0xeeea  ldarg.0
0xeeeb  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0xeef0  stloc.3
0xeef1  ldloca.s 3
0xeef3  ldstr    aD// "D"
0xeef8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeefd  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0xef02  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xef07  ldarg.1
0xef08  ldc.i4.s 0xA
0xef0a  ldstr    aLinkcontrollab// "linkControlLabel"
0xef0f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xef14  ldarg.1
0xef15  ldstr    aIsdataunboundc// "isDataUnboundControl"
0xef1a  ldstr    aTrue// "true"
0xef1f  ldc.i4.0
0xef20  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0xef25  ldarg.1
0xef26  ldstr    aIseligibleform// "isEligibleForMarkComplete"
0xef2b  ldarg.0
0xef2c  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::get_IsEligibleForMarkComplete()
0xef31  stloc.s  4
0xef33  ldloca.s 4
0xef35  call     instance string [mscorlib]System.Boolean::ToString()
0xef3a  ldc.i4.0
0xef3b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0xef40  ldarg.1
0xef41  ldstr    aViewporttype// "viewportType"
0xef46  ldarg.0
0xef47  callvirt instance valuetype Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControlFlyOutType Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::get_FlyOutType()
0xef4c  stloc.3
0xef4d  ldloca.s 3
0xef4f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef54  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xef59  ldc.i4.0
0xef5a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0xef5f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xef64  stloc.s  5
0xef66  ldloca.s 5
0xef68  ldarg.0
0xef69  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LinkControl::get_LinkControlDefinitionId()
0xef6e  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xef73  brtrue.s loc_EF9A
0xef75  ldarg.1
0xef76  ldstr    aLinkcontroldef// "linkcontroldefinitionid"
0xef7b  ldarg.0
0xef7c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LinkControl::get_LinkControlDefinitionId()
0xef81  stloc.s  5
0xef83  ldloca.s 5
0xef85  ldstr    aD// "D"
0xef8a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef8f  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0xef94  ldc.i4.0
0xef95  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(string, string, bool)
0xef9a  ldarg.0
0xef9b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::get_flyOutDescriptor()
0xefa0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.LabelDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ProcessDefinition.LabelEnabledDescriptor::get_UserLabel()
0xefa5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.LabelDescriptor::get_Description()
0xefaa  stloc.0
0xefab  ldarg.0
0xefac  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.LinkControl::get_ShowLinkControlLabel()
0xefb1  brfalse.s loc_EFDA
0xefb3  ldarg.1
0xefb4  ldc.i4.s 0x19
0xefb6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xefbb  ldarg.0
0xefbc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.LinkControl::get_flyOutDescriptor()
0xefc1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SectionDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor::get_SectionDescriptor()
0xefc6  brfalse.s loc_EFD4
0xefc8  ldarg.1
0xefc9  ldloc.0
0xefca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xefcf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xefd4  ldarg.1
0xefd5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xefda  ldarg.1
0xefdb  ldc.i4.s 0x10
0xefdd  ldstr    asc_3002A// "#"
0xefe2  ldc.i4.0
0xefe3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0xefe8  ldarg.1
0xefe9  ldc.i4.s 0x22
0xefeb  ldloc.0
0xefec  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xeff1  ldc.i4.0
0xeff2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0xeff7  ldarg.1
0xeff8  ldc.i4.s 0x17
0xeffa  ldstr    aMscrmUtilities// "Mscrm.Utilities.click(previousSibling)"
0xefff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xf004  ldarg.1
0xf005  ldc.i4.s 0x20
0xf007  ldstr    a1// "-1"
0xf00c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0xf011  ldarg.1
0xf012  ldc.i4.1
0xf013  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0xf018  ldarg.1
0xf019  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0xf01e  ret
```
