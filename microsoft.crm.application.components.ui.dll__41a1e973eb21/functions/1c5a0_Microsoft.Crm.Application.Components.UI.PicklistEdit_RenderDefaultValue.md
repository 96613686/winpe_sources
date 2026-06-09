# Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderDefaultValue

- ea: `0x1c5a0`
- end: `0x1c64f`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderDefaultValue`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1c380`

## callees

- `0x1bb60`
- `0x1c5a0`
- `0x1c780`
- `0x22480`
- `0x23f00`
- `0x26600`
- `0x26750`

## pseudocode

```c

```

## disassembly

```asm
0x1c5a0  ldarg.1
0x1c5a1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1c5a6  stloc.0
0x1c5a7  ldloc.0
0x1c5a8  ldstr    aTr_1// "<tr>"
0x1c5ad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c5b2  ldloc.0
0x1c5b3  ldstr    aTdClassMsCrmPi_0// "<td class=\"ms-crm-Picklist_DefaultLabe"...
0x1c5b8  ldarg.0
0x1c5b9  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_DefaultValueLabel()
0x1c5be  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1c5c3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1c5c8  ldloc.0
0x1c5c9  ldstr    aTdClassListedi_2// "<td class=\"listEdit_dropdown\" >"
0x1c5ce  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c5d3  ldarg.0
0x1c5d4  newobj   instance void Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x1c5d9  dup
0x1c5da  stloc.2
0x1c5db  stfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.PicklistEdit::_selDefaultValue
0x1c5e0  ldloc.2
0x1c5e1  stloc.1
0x1c5e2  ldarg.0
0x1c5e3  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.PicklistEdit::_selDefaultValue
0x1c5e8  ldarg.0
0x1c5e9  ldstr    aSeldefaultvalu_1// "selDefaultValue"
0x1c5ee  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::GetOptionItemId(string fieldName)
0x1c5f3  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1c5f8  ldarg.0
0x1c5f9  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.PicklistEdit::_selDefaultValue
0x1c5fe  ldc.i4.0
0x1c5ff  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool value)
0x1c604  ldarg.0
0x1c605  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.PicklistEdit::_selDefaultValue
0x1c60a  ldarg.1
0x1c60b  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c610  ldloc.0
0x1c611  ldarg.0
0x1c612  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.PicklistEdit::_selDefaultValue
0x1c617  callvirt instance string Microsoft.Crm.Application.Components.UI.Select::get_ClientSideFormInputBehaviorClassName()
0x1c61c  ldarg.0
0x1c61d  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.PicklistEdit::_selDefaultValue
0x1c622  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1c627  call     void Microsoft.Crm.Application.Components.UI.SharedMethods::RenderClientControlRegistrationScript(class [mscorlib]System.IO.TextWriter output, string clientSideFormInputBehaviorClassName, string id)
0x1c62c  leave.s  loc_1C638
0x1c62e  ldloc.1
0x1c62f  brfalse.s loc_1C637
0x1c631  ldloc.1
0x1c632  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c637  endfinally
0x1c638  ldloc.0
0x1c639  ldstr    aTd// "</td>"
0x1c63e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c643  ldloc.0
0x1c644  ldstr    aTr// "</tr>"
0x1c649  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c64e  ret
```
