# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderCommandBar

- ea: `0x1dc70`
- end: `0x1ddaf`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderCommandBar`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1e6f0`

## callees

- `0x1d510`
- `0x1d530`
- `0x1d570`
- `0x1d590`
- `0x1d5b0`
- `0x1d5d0`
- `0x1db70`
- `0x1dc70`
- `0x1ddb0`
- `0x1ddc0`

## string_xrefs

- `0x1dccf`: `btnMoveValueUp`
- `0x1dce6`: `btnMoveValueDown`
- `0x1dcaf`: `btnRemoveValue`
- `0x1dc78`: `<table id="CommandBar" width="100%" class="ms-crm-Picklist-MenuBar">`
- `0x1dcb4`: `remove`
- `0x1dcd4`: `moveup`
- `0x1dceb`: `movedown`

## pseudocode

```c

```

## disassembly

```asm
0x1dc70  ldarg.1
0x1dc71  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1dc76  stloc.0
0x1dc77  ldloc.0
0x1dc78  ldstr    aTableIdCommand// "<table id=\"CommandBar\" width=\"100%\""...
0x1dc7d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dc82  ldloc.0
0x1dc83  ldstr    aTr_1// "<tr>"
0x1dc88  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dc8d  ldarg.0
0x1dc8e  ldc.i4.4
0x1dc8f  call     instance bool Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CheckFunction(valuetype Microsoft.Crm.Application.Components.UI.CustomOperationFunction function)
0x1dc94  brfalse.s loc_1DCC4
0x1dc96  ldarg.0
0x1dc97  ldarg.1
0x1dc98  ldstr    aBtnaddvalue// "btnAddValue"
0x1dc9d  ldstr    aAdd// "add"
0x1dca2  ldarg.0
0x1dca3  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_AddLabel()
0x1dca8  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1dcad  ldarg.0
0x1dcae  ldarg.1
0x1dcaf  ldstr    aBtnremovevalue// "btnRemoveValue"
0x1dcb4  ldstr    aRemove// "remove"
0x1dcb9  ldarg.0
0x1dcba  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_RemoveLabel()
0x1dcbf  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1dcc4  ldarg.0
0x1dcc5  ldc.i4.1
0x1dcc6  call     instance bool Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CheckFunction(valuetype Microsoft.Crm.Application.Components.UI.CustomOperationFunction function)
0x1dccb  brfalse.s loc_1DCFB
0x1dccd  ldarg.0
0x1dcce  ldarg.1
0x1dccf  ldstr    aBtnmovevalueup// "btnMoveValueUp"
0x1dcd4  ldstr    aMoveup// "moveup"
0x1dcd9  ldarg.0
0x1dcda  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_MoveUpLabel()
0x1dcdf  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1dce4  ldarg.0
0x1dce5  ldarg.1
0x1dce6  ldstr    aBtnmovevaluedo// "btnMoveValueDown"
0x1dceb  ldstr    aMovedown// "movedown"
0x1dcf0  ldarg.0
0x1dcf1  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_MoveDownLabel()
0x1dcf6  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1dcfb  ldarg.0
0x1dcfc  ldc.i4.s 0x10
0x1dcfe  call     instance bool Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CheckFunction(valuetype Microsoft.Crm.Application.Components.UI.CustomOperationFunction function)
0x1dd03  brfalse.s loc_1DD33
0x1dd05  ldarg.0
0x1dd06  ldarg.1
0x1dd07  ldstr    aBtnsortasc// "btnSortAsc"
0x1dd0c  ldstr    aSortasc_0// "sortasc"
0x1dd11  ldarg.0
0x1dd12  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_SortAscLabel()
0x1dd17  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1dd1c  ldarg.0
0x1dd1d  ldarg.1
0x1dd1e  ldstr    aBtnsortdesc// "btnSortDesc"
0x1dd23  ldstr    aSortdes// "sortdes"
0x1dd28  ldarg.0
0x1dd29  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_SortDescLabel()
0x1dd2e  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x1dd33  ldarg.0
0x1dd34  ldc.i4.2
0x1dd35  call     instance bool Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CheckFunction(valuetype Microsoft.Crm.Application.Components.UI.CustomOperationFunction function)
0x1dd3a  brfalse.s loc_1DD9C
0x1dd3c  ldloc.0
0x1dd3d  ldstr    aTdWidth1px// "<td width=\"1px\">"
0x1dd42  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dd47  ldloc.0
0x1dd48  ldstr    aSpanClassMsCrm// "<SPAN class=\"ms-crm-optionset-Label\">"...
0x1dd4d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dd52  ldloc.0
0x1dd53  ldstr    aTabindex1HrefJ_0// "\" tabindex=\"-1\" href=\"javascript:on"...
0x1dd58  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dd5d  ldloc.0
0x1dd5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1dd63  ldstr    a0Btneditvalue// "{0}_btnEditValue"
0x1dd68  ldc.i4.1
0x1dd69  newarr   [mscorlib]System.Object
0x1dd6e  dup
0x1dd6f  ldc.i4.0
0x1dd70  ldarg.0
0x1dd71  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1dd76  stelem.ref
0x1dd77  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dd7c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1dd81  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dd86  ldloc.0
0x1dd87  ldstr    aSpan_5// "\"/></SPAN>"
0x1dd8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dd91  ldloc.0
0x1dd92  ldstr    aTd// "</td>"
0x1dd97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dd9c  ldarg.0
0x1dd9d  ldarg.1
0x1dd9e  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::AddFiller(class [mscorlib]System.IO.TextWriter output)
0x1dda3  ldloc.0
0x1dda4  ldstr    aTrTable// "</tr></table>"
0x1dda9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ddae  ret
```
