# Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderCommandBar

- ea: `0x1bfa0`
- end: `0x1c0df`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderCommandBar`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1c7c0`

## callees

- `0x1ba80`
- `0x1baa0`
- `0x1bae0`
- `0x1bb00`
- `0x1bb20`
- `0x1bb40`
- `0x1bf90`
- `0x1bfa0`
- `0x1c0e0`
- `0x1c0f0`

## string_xrefs

- `0x1bfff`: `btnMoveValueUp`
- `0x1c016`: `btnMoveValueDown`
- `0x1bfdf`: `btnRemoveValue`
- `0x1bfa8`: `<table id="CommandBar" width="100%" class="ms-crm-Picklist-MenuBar">`
- `0x1bfe4`: `remove`
- `0x1c004`: `moveup`
- `0x1c01b`: `movedown`

## pseudocode

```c

```

## disassembly

```asm
0x1bfa0  ldarg.1
0x1bfa1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1bfa6  stloc.0
0x1bfa7  ldloc.0
0x1bfa8  ldstr    aTableIdCommand// "<table id=\"CommandBar\" width=\"100%\""...
0x1bfad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1bfb2  ldloc.0
0x1bfb3  ldstr    aTr_1// "<tr>"
0x1bfb8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1bfbd  ldarg.0
0x1bfbe  ldc.i4.4
0x1bfbf  call     instance bool Microsoft.Crm.Application.Components.UI.PicklistEdit::CheckFunction(valuetype Function function)
0x1bfc4  brfalse.s loc_1BFF4
0x1bfc6  ldarg.0
0x1bfc7  ldarg.1
0x1bfc8  ldstr    aBtnaddvalue// "btnAddValue"
0x1bfcd  ldstr    aAdd// "add"
0x1bfd2  ldarg.0
0x1bfd3  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_AddLabel()
0x1bfd8  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1bfdd  ldarg.0
0x1bfde  ldarg.1
0x1bfdf  ldstr    aBtnremovevalue// "btnRemoveValue"
0x1bfe4  ldstr    aRemove// "remove"
0x1bfe9  ldarg.0
0x1bfea  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_RemoveLabel()
0x1bfef  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1bff4  ldarg.0
0x1bff5  ldc.i4.1
0x1bff6  call     instance bool Microsoft.Crm.Application.Components.UI.PicklistEdit::CheckFunction(valuetype Function function)
0x1bffb  brfalse.s loc_1C02B
0x1bffd  ldarg.0
0x1bffe  ldarg.1
0x1bfff  ldstr    aBtnmovevalueup// "btnMoveValueUp"
0x1c004  ldstr    aMoveup// "moveup"
0x1c009  ldarg.0
0x1c00a  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_MoveUpLabel()
0x1c00f  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1c014  ldarg.0
0x1c015  ldarg.1
0x1c016  ldstr    aBtnmovevaluedo// "btnMoveValueDown"
0x1c01b  ldstr    aMovedown// "movedown"
0x1c020  ldarg.0
0x1c021  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_MoveDownLabel()
0x1c026  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1c02b  ldarg.0
0x1c02c  ldc.i4.s 0x10
0x1c02e  call     instance bool Microsoft.Crm.Application.Components.UI.PicklistEdit::CheckFunction(valuetype Function function)
0x1c033  brfalse.s loc_1C063
0x1c035  ldarg.0
0x1c036  ldarg.1
0x1c037  ldstr    aBtnsortasc// "btnSortAsc"
0x1c03c  ldstr    aSortasc_0// "sortasc"
0x1c041  ldarg.0
0x1c042  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_SortAscLabel()
0x1c047  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1c04c  ldarg.0
0x1c04d  ldarg.1
0x1c04e  ldstr    aBtnsortdesc// "btnSortDesc"
0x1c053  ldstr    aSortdes// "sortdes"
0x1c058  ldarg.0
0x1c059  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_SortDescLabel()
0x1c05e  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1c063  ldarg.0
0x1c064  ldc.i4.2
0x1c065  call     instance bool Microsoft.Crm.Application.Components.UI.PicklistEdit::CheckFunction(valuetype Function function)
0x1c06a  brfalse.s loc_1C0CC
0x1c06c  ldloc.0
0x1c06d  ldstr    aTdStyleWidth1p// "<td style=\"width:1px\">"
0x1c072  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c077  ldloc.0
0x1c078  ldstr    aSpanClassMsCrm// "<SPAN class=\"ms-crm-optionset-Label\">"...
0x1c07d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c082  ldloc.0
0x1c083  ldstr    aTabindex1HrefJ// "\" tabindex = -1 href=\"javascript:oncl"...
0x1c088  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c08d  ldloc.0
0x1c08e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c093  ldstr    a0Btneditvalue// "{0}_btnEditValue"
0x1c098  ldc.i4.1
0x1c099  newarr   [mscorlib]System.Object
0x1c09e  dup
0x1c09f  ldc.i4.0
0x1c0a0  ldarg.0
0x1c0a1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1c0a6  stelem.ref
0x1c0a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c0ac  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1c0b1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c0b6  ldloc.0
0x1c0b7  ldstr    aSpan_5// "\"/></SPAN>"
0x1c0bc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c0c1  ldloc.0
0x1c0c2  ldstr    aTd// "</td>"
0x1c0c7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c0cc  ldarg.0
0x1c0cd  ldarg.1
0x1c0ce  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::AddFiller(class [mscorlib]System.IO.TextWriter output)
0x1c0d3  ldloc.0
0x1c0d4  ldstr    aTrTable// "</tr></table>"
0x1c0d9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c0de  ret
```
