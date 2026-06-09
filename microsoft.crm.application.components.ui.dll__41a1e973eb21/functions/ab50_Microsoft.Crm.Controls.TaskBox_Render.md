# Microsoft.Crm.Controls.TaskBox::Render

- ea: `0xab50`
- end: `0xad0a`
- name: `Microsoft.Crm.Controls.TaskBox::Render`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xa9e0`
- `0xaa00`
- `0xaa20`
- `0xaa40`
- `0xab50`

## string_xrefs

- `0xabd8`: `<div class="TaskBox_Render_td">`

## pseudocode

```c

```

## disassembly

```asm
0xab50  ldarg.1
0xab51  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xab56  stloc.0
0xab57  ldloc.0
0xab58  ldstr    aDivStyleWidth// "<div style=\"width:"
0xab5d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xab62  ldloc.0
0xab63  ldarg.0
0xab64  call     instance string Microsoft.Crm.Controls.TaskBox::get_Width()
0xab69  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xab6e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xab73  ldloc.0
0xab74  ldstr    aHeight// "; height:"
0xab79  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xab7e  ldloc.0
0xab7f  ldarg.0
0xab80  call     instance string Microsoft.Crm.Controls.TaskBox::get_Height()
0xab85  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xab8a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xab8f  ldloc.0
0xab90  ldstr    asc_43B56// ";"
0xab95  ldarg.0
0xab96  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xab9b  callvirt instance string [System.Web]System.Web.UI.CssStyleCollection::get_Value()
0xaba0  call     string [mscorlib]System.String::Concat(string, string)
0xaba5  dup
0xaba6  brtrue.s loc_ABAE
0xaba8  pop
0xaba9  ldstr    asc_3280A// ""
0xabae  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xabb3  ldloc.0
0xabb4  ldstr    aPositionRelati// ";position:relative;\">"
0xabb9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xabbe  ldloc.0
0xabbf  ldstr    aDivClassWizhea// "<div class=\"wizHead\">"
0xabc4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xabc9  ldarg.0
0xabca  call     instance string Microsoft.Crm.Controls.TaskBox::get_Icon()
0xabcf  callvirt instance int32 [mscorlib]System.String::get_Length()
0xabd4  ldc.i4.0
0xabd5  ble.s    loc_AC09
0xabd7  ldloc.0
0xabd8  ldstr    aDivClassTaskbo// "<div class=\"TaskBox_Render_td\">"
0xabdd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xabe2  ldloc.0
0xabe3  ldstr    aImgAlt_1// "<img alt=\"\" "
0xabe8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xabed  ldstr    aSrc_0// "src"
0xabf2  ldarg.0
0xabf3  call     instance string Microsoft.Crm.Controls.TaskBox::get_Icon()
0xabf8  ldarg.1
0xabf9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xabfe  ldloc.0
0xabff  ldstr    aDiv_2// "/></div>"
0xac04  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xac09  ldloc.0
0xac0a  ldstr    aDiv_0// "<div"
0xac0f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xac14  ldarg.0
0xac15  call     instance string Microsoft.Crm.Controls.TaskBox::get_Icon()
0xac1a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xac1f  ldc.i4.0
0xac20  ble.s    loc_AC67
0xac22  ldloc.0
0xac23  ldstr    aStyleBorder00p// " style=\"border-{0}:0px;padding-{1}:3px"...
0xac28  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xac2d  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xac32  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xac37  brtrue.s loc_AC40
0xac39  ldstr    aLeft// "left"
0xac3e  br.s     loc_AC45
0xac40  ldstr    aRight// "right"
0xac45  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xac4a  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xac4f  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xac54  brtrue.s loc_AC5D
0xac56  ldstr    aLeft// "left"
0xac5b  br.s     loc_AC62
0xac5d  ldstr    aRight// "right"
0xac62  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0xac67  ldloc.0
0xac68  ldstr    aNobrClassTitle// "><nobr class=\"title\" title=\""
0xac6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xac72  ldloc.0
0xac73  ldarg.0
0xac74  call     instance string Microsoft.Crm.Controls.TaskBox::get_Title()
0xac79  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xac7e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xac83  ldloc.0
0xac84  ldstr    asc_42682// "\">"
0xac89  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xac8e  ldloc.0
0xac8f  ldarg.0
0xac90  call     instance string Microsoft.Crm.Controls.TaskBox::get_Title()
0xac95  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xac9a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xac9f  ldloc.0
0xaca0  ldstr    aNobrDivDiv// "</nobr></div></div>"
0xaca5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xacaa  ldloc.0
0xacab  ldstr    aDivClassWizbox// "<div class=\"wizBoxCont\">"
0xacb0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xacb5  ldloc.0
0xacb6  ldstr    aDivId0ClassWiz// "<div id=\"{0}\" class=\"wizBox\">"
0xacbb  ldarg.0
0xacbc  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xacc1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0xacc6  ldloc.0
0xacc7  ldarg.0
0xacc8  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Controls.TaskBox::_topHtml
0xaccd  callvirt instance string [mscorlib]System.Object::ToString()
0xacd2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xacd7  ldloc.0
0xacd8  ldstr    aDivClassWizite// "<div class=\"wizItemRow wizItemRowBotto"...
0xacdd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xace2  ldloc.0
0xace3  ldarg.0
0xace4  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Controls.TaskBox::_bottomHtml
0xace9  callvirt instance string [mscorlib]System.Object::ToString()
0xacee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xacf3  ldloc.0
0xacf4  ldstr    aDiv// "</div>"
0xacf9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xacfe  ldloc.0
0xacff  ldstr    aDivDivDiv// "</div></div></div>"
0xad04  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xad09  ret
```
