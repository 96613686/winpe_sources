# Microsoft.Crm.Application.Forms.FormBody::RenderForRead

- ea: `0x32840`
- end: `0x32a09`
- name: `Microsoft.Crm.Application.Forms.FormBody::RenderForRead`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x32a10`

## callees

- `0x26510`
- `0x2fb20`
- `0x32840`
- `0x36070`
- `0x39070`
- `0x390b0`
- `0x82ff0`

## string_xrefs

- `0x328c1`: `<div class="ms-crm-InlineTabContainer-Read-SLAKpiQuickView" id="crmFormTabContainer" IsQuickForm="True">`
- `0x328ce`: `<div class="ms-crm-InlineTabContainer-Read" id="crmFormTabContainer" IsQuickForm="{0}">`
- `0x32930`: `<div class="ms-crm-InlineTab-Read"`

## pseudocode

```c

```

## disassembly

```asm
0x32840  ldarg.1
0x32841  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x32846  stloc.0
0x32847  ldarg.0
0x32848  ldfld    class Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Forms.FormBody::_form
0x3284d  callvirt instance bool Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_InlineEditable()
0x32852  stloc.1
0x32853  ldloc.1
0x32854  brtrue.s loc_32896
0x32856  ldarg.0
0x32857  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Forms.FormBody::_formDescriptor
0x3285c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_HasMargin()
0x32861  brfalse.s loc_32896
0x32863  ldloc.0
0x32864  ldstr    aDivClassMsCrmF// "<div class=\"ms-crm-Form-Area\""
0x32869  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3286e  ldarg.0
0x3286f  callvirt instance int32 Microsoft.Crm.Application.Controls.AppControl::get_MinWidth()
0x32874  ldc.i4   0xAA
0x32879  add
0x3287a  stloc.2
0x3287b  ldloc.0
0x3287c  ldstr    aStyleMinWidth// " style=\"min-width:"
0x32881  ldloc.2
0x32882  box      [mscorlib]System.Int32
0x32887  ldstr    aPx_0// "px\" >"
0x3288c  call     string [mscorlib]System.String::Concat(object, object, object)
0x32891  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x32896  ldarg.0
0x32897  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Forms.FormBody::_formDescriptor
0x3289c  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0x328a1  ldc.i4.6
0x328a2  bne.un.s loc_328CD
0x328a4  ldarg.0
0x328a5  ldfld    class Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Forms.FormBody::_form
0x328aa  callvirt instance int32 Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x328af  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0x328b4  ldstr    aSlakpiinstance// "slakpiinstance"
0x328b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x328be  brfalse.s loc_328CD
0x328c0  ldloc.0
0x328c1  ldstr    aDivClassMsCrmI// "<div class=\"ms-crm-InlineTabContainer-"...
0x328c6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x328cb  br.s     loc_328EB
0x328cd  ldloc.0
0x328ce  ldstr    aDivClassMsCrmI_0// "<div class=\"ms-crm-InlineTabContainer-"...
0x328d3  ldarg.0
0x328d4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Forms.FormBody::_formDescriptor
0x328d9  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0x328de  ldc.i4.6
0x328df  ceq
0x328e1  box      [mscorlib]System.Boolean
0x328e6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x328eb  ldarg.0
0x328ec  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x328f1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x328f6  stloc.3
0x328f7  br       loc_329C1
0x328fc  ldloc.3
0x328fd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32902  castclass [System.Web]System.Web.UI.Control
0x32907  stloc.s  4
0x32909  ldloc.s  4
0x3290b  isinst   Microsoft.Crm.Application.Forms.FormTab
0x32910  stloc.s  5
0x32912  ldloc.s  4
0x32914  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x32919  brfalse  loc_329C1
0x3291e  ldloc.s  5
0x32920  brtrue.s loc_3292F
0x32922  ldloc.0
0x32923  ldstr    aDiv_2// "<div>"
0x32928  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3292d  br.s     loc_329AE
0x3292f  ldloc.0
0x32930  ldstr    aDivClassMsCrmI_1// "<div class=\"ms-crm-InlineTab-Read\""
0x32935  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3293a  ldstr    aId_1// "id"
0x3293f  ldloc.s  5
0x32941  callvirt instance string Microsoft.Crm.Application.Forms.FormTab::get_ContainerId()
0x32946  ldarg.1
0x32947  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3294c  ldstr    aName// "name"
0x32951  ldloc.s  5
0x32953  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Name()
0x32958  ldarg.1
0x32959  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3295e  ldstr    aRole// "role"
0x32963  ldstr    aRegion// "region"
0x32968  ldarg.1
0x32969  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3296e  ldstr    aAriaLabelledby// "aria-labelledby"
0x32973  ldloc.s  5
0x32975  callvirt instance string Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Name()
0x3297a  ldstr    aHeaderH2// "_header_h2"
0x3297f  call     string [mscorlib]System.String::Concat(string, string)
0x32984  ldarg.1
0x32985  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x3298a  ldloc.s  5
0x3298c  callvirt instance bool Microsoft.Crm.Application.Forms.FormTab::get_RenderAsVisible()
0x32991  brtrue.s loc_329A3
0x32993  ldstr    aStyle_0// "style"
0x32998  ldstr    aDisplayNone// "display:none"
0x3299d  ldarg.1
0x3299e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x329a3  ldloc.0
0x329a4  ldstr    asc_111CB6// ">"
0x329a9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x329ae  ldloc.s  4
0x329b0  ldarg.1
0x329b1  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x329b6  ldloc.0
0x329b7  ldstr    aDiv_1// "</div>"
0x329bc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x329c1  ldloc.3
0x329c2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x329c7  brtrue   loc_328FC
0x329cc  leave.s  loc_329E2
0x329ce  ldloc.3
0x329cf  isinst   [mscorlib]System.IDisposable
0x329d4  stloc.s  6
0x329d6  ldloc.s  6
0x329d8  brfalse.s loc_329E1
0x329da  ldloc.s  6
0x329dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x329e1  endfinally
0x329e2  ldloc.0
0x329e3  ldstr    aDiv_1// "</div>"
0x329e8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x329ed  ldloc.1
0x329ee  brtrue.s loc_32A08
0x329f0  ldarg.0
0x329f1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Forms.FormBody::_formDescriptor
0x329f6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_HasMargin()
0x329fb  brfalse.s loc_32A08
0x329fd  ldloc.0
0x329fe  ldstr    aDiv_1// "</div>"
0x32a03  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x32a08  ret
```
