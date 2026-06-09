# Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton

- ea: `0x1aef0`
- end: `0x1b039`
- name: `Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1b040`

## callees

- `0x14fb0`
- `0x15070`
- `0x15170`
- `0x1ad50`
- `0x1aef0`
- `0x23c30`

## string_xrefs

- `0x1afdb`: `btnMoveValueUp`
- `0x1afe8`: `btnMoveValueDown`
- `0x1b00f`: `<script type="text/javascript">Sys.Application.add_init(function(){{var toolTip=$get("{0}"); crmCreate(Mscrm.AutoToolTip,{{}},null,null,toolTip);}});</script>`

## pseudocode

```c

```

## disassembly

```asm
0x1aef0  ldarg.1
0x1aef1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1aef6  stloc.0
0x1aef7  ldarg.s  5
0x1aef9  ldind.u1
0x1aefa  brfalse.s loc_1AF07
0x1aefc  ldloc.0
0x1aefd  ldstr    aTrClassListedi// "<tr class=\"listEdit_vspacer\"><td></td"...
0x1af02  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1af07  ldloc.0
0x1af08  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1af0d  ldstr    aTrTdNowrapStyl// "<tr><td nowrap style=\"padding-{0}:5px"...
0x1af12  ldc.i4.1
0x1af13  newarr   [mscorlib]System.Object
0x1af18  dup
0x1af19  ldc.i4.0
0x1af1a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1af1f  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1af24  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1af29  brtrue.s loc_1AF32
0x1af2b  ldstr    aRight// "right"
0x1af30  br.s     loc_1AF37
0x1af32  ldstr    aLeft// "left"
0x1af37  stelem.ref
0x1af38  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1af3d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1af42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1af47  ldstr    aBtnspanid0// "btnSpanId{0}"
0x1af4c  ldc.i4.1
0x1af4d  newarr   [mscorlib]System.Object
0x1af52  dup
0x1af53  ldc.i4.0
0x1af54  ldarg.0
0x1af55  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x1af5a  stelem.ref
0x1af5b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1af60  stloc.1
0x1af61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1af66  ldstr    a01_3// "{0}_{1}"
0x1af6b  ldc.i4.2
0x1af6c  newarr   [mscorlib]System.Object
0x1af71  dup
0x1af72  ldc.i4.0
0x1af73  ldarg.0
0x1af74  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1af79  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1af7e  stelem.ref
0x1af7f  dup
0x1af80  ldc.i4.1
0x1af81  ldarg.2
0x1af82  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1af87  stelem.ref
0x1af88  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1af8d  ldsfld   string [mscorlib]System.String::Empty
0x1af92  ldarg.s  4
0x1af94  ldc.i4.0
0x1af95  ldstr    aListeditButton// "listEdit_button"
0x1af9a  newobj   instance void Microsoft.Crm.Application.Components.UI.Button::.ctor(string id, string resourceId, string onClick, bool disabled, string cssClass)
0x1af9f  stloc.2
0x1afa0  ldloc.2
0x1afa1  ldc.i4   0xCD
0x1afa6  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_Width(int32 value)
0x1afab  ldloc.2
0x1afac  ldarg.3
0x1afad  callvirt instance void Microsoft.Crm.Application.Components.UI.Button::set_Text(string value)
0x1afb2  ldloc.2
0x1afb3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1afb8  ldstr    aSpanId0ClassAu// "<span id=\"{0}\" class=\"autoellipsis\""...
0x1afbd  ldc.i4.2
0x1afbe  newarr   [mscorlib]System.Object
0x1afc3  dup
0x1afc4  ldc.i4.0
0x1afc5  ldloc.1
0x1afc6  stelem.ref
0x1afc7  dup
0x1afc8  ldc.i4.1
0x1afc9  ldarg.3
0x1afca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1afcf  stelem.ref
0x1afd0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1afd5  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x1afda  ldarg.2
0x1afdb  ldstr    aBtnmovevalueup// "btnMoveValueUp"
0x1afe0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1afe5  brtrue.s loc_1AFF4
0x1afe7  ldarg.2
0x1afe8  ldstr    aBtnmovevaluedo// "btnMoveValueDown"
0x1afed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1aff2  brfalse.s loc_1B003
0x1aff4  ldarg.0
0x1aff5  call     instance bool Microsoft.Crm.Application.Components.UI.ListEdit::get_MoveDisabled()
0x1affa  brfalse.s loc_1B003
0x1affc  ldloc.2
0x1affd  ldc.i4.1
0x1affe  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1b003  ldloc.2
0x1b004  dup
0x1b005  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x1b00a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b00f  ldstr    aScriptTypeText_9// "<script type=\"text/javascript\">Sys.Ap"...
0x1b014  ldc.i4.1
0x1b015  newarr   [mscorlib]System.Object
0x1b01a  dup
0x1b01b  ldc.i4.0
0x1b01c  ldloc.1
0x1b01d  stelem.ref
0x1b01e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b023  call     string [mscorlib]System.String::Concat(string, string)
0x1b028  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x1b02d  ldloc.2
0x1b02e  ldarg.1
0x1b02f  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b034  ldarg.s  5
0x1b036  ldc.i4.1
0x1b037  stind.i1
0x1b038  ret
```
