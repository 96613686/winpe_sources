# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderDefaultValue

- ea: `0x1e4d0`
- end: `0x1e57f`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderDefaultValue`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1e140`

## callees

- `0x1d5f0`
- `0x1e4d0`
- `0x1e6b0`
- `0x22480`
- `0x23f00`
- `0x26600`
- `0x26750`

## pseudocode

```c

```

## disassembly

```asm
0x1e4d0  ldarg.1
0x1e4d1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e4d6  stloc.0
0x1e4d7  ldloc.0
0x1e4d8  ldstr    aTr_1// "<tr>"
0x1e4dd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e4e2  ldloc.0
0x1e4e3  ldstr    aTdClassMsCrmPi_0// "<td class=\"ms-crm-Picklist_DefaultLabe"...
0x1e4e8  ldarg.0
0x1e4e9  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_DefaultValueLabel()
0x1e4ee  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1e4f3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1e4f8  ldloc.0
0x1e4f9  ldstr    aTdClassListedi_2// "<td class=\"listEdit_dropdown\" >"
0x1e4fe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e503  ldarg.0
0x1e504  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x1e509  dup
0x1e50a  stloc.2
0x1e50b  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_selDefaultValue
0x1e510  ldloc.2
0x1e511  stloc.1
0x1e512  ldarg.0
0x1e513  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_selDefaultValue
0x1e518  ldarg.0
0x1e519  ldstr    aSeldefaultvalu_1// "selDefaultValue"
0x1e51e  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetOptionItemId(string fieldName)
0x1e523  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1e528  ldarg.0
0x1e529  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_selDefaultValue
0x1e52e  ldc.i4.0
0x1e52f  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool value)
0x1e534  ldarg.0
0x1e535  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_selDefaultValue
0x1e53a  ldarg.1
0x1e53b  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1e540  ldloc.0
0x1e541  ldarg.0
0x1e542  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_selDefaultValue
0x1e547  callvirt instance string Microsoft.Crm.Application.Components.UI.Select::get_ClientSideFormInputBehaviorClassName()
0x1e54c  ldarg.0
0x1e54d  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_selDefaultValue
0x1e552  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1e557  call     void Microsoft.Crm.Application.Components.UI.SharedMethods::RenderClientControlRegistrationScript(class [mscorlib]System.IO.TextWriter output, string clientSideFormInputBehaviorClassName, string id)
0x1e55c  leave.s  loc_1E568
0x1e55e  ldloc.1
0x1e55f  brfalse.s loc_1E567
0x1e561  ldloc.1
0x1e562  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e567  endfinally
0x1e568  ldloc.0
0x1e569  ldstr    aTd// "</td>"
0x1e56e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e573  ldloc.0
0x1e574  ldstr    aTr// "</tr>"
0x1e579  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e57e  ret
```
