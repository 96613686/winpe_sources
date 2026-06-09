# Microsoft.Crm.Application.Components.UI.TextBox::RenderTextBoxContainer

- ea: `0x231f0`
- end: `0x2328f`
- name: `Microsoft.Crm.Application.Components.UI.TextBox::RenderTextBoxContainer`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x22fc0`

## callees

- `0x22e70`
- `0x22ed0`
- `0x231f0`
- `0x23c20`
- `0x24280`

## string_xrefs

- `0x23232`: ` ms-crm-Input-Container-ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x231f0  ldstr    aMsCrmInputCont// "ms-crm-Input-Container"
0x231f5  stloc.0
0x231f6  ldloc.0
0x231f7  ldarg.0
0x231f8  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_CssClass()
0x231fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23202  brtrue.s loc_23216
0x23204  ldstr    asc_4C79A// " "
0x23209  ldarg.0
0x2320a  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_CssClass()
0x2320f  call     string [mscorlib]System.String::Concat(string, string)
0x23214  br.s     loc_2321B
0x23216  ldstr    asc_3280A// ""
0x2321b  call     string [mscorlib]System.String::Concat(string, string)
0x23220  stloc.0
0x23221  ldarg.0
0x23222  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x23227  brtrue.s loc_23231
0x23229  ldarg.0
0x2322a  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x2322f  brfalse.s loc_2323D
0x23231  ldloc.0
0x23232  ldstr    aMsCrmInputCont_0// " ms-crm-Input-Container-ReadOnly"
0x23237  call     string [mscorlib]System.String::Concat(string, string)
0x2323c  stloc.0
0x2323d  ldarg.1
0x2323e  ldstr    aDiv_5// "<div "
0x23243  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x23248  ldstr    aClass_1// "class"
0x2324d  ldloc.0
0x2324e  ldarg.1
0x2324f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x23254  ldstr    aId// "id"
0x23259  ldarg.0
0x2325a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2325f  ldstr    aContainer// "_container"
0x23264  call     string [mscorlib]System.String::Concat(string, string)
0x23269  ldarg.1
0x2326a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2326f  ldarg.0
0x23270  call     instance bool Microsoft.Crm.Application.Components.UI.TextBox::get_IsHidden()
0x23275  brfalse.s loc_23283
0x23277  ldarg.1
0x23278  ldstr    aStyleDisplayNo_2// "style=\"display:none;\""
0x2327d  ldarg.1
0x2327e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x23283  ldarg.1
0x23284  ldstr    asc_2B7B6// ">"
0x23289  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2328e  ret
```
