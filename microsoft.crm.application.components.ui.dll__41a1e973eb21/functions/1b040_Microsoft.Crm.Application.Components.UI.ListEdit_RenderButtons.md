# Microsoft.Crm.Application.Components.UI.ListEdit::RenderButtons

- ea: `0x1b040`
- end: `0x1b20f`
- name: `Microsoft.Crm.Application.Components.UI.ListEdit::RenderButtons`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1b230`

## callees

- `0x1abf0`
- `0x1ac10`
- `0x1ac30`
- `0x1ac50`
- `0x1ac70`
- `0x1ac90`
- `0x1acb0`
- `0x1aee0`
- `0x1aef0`
- `0x1b040`

## string_xrefs

- `0x1b0a7`: `btnMoveValueUp`
- `0x1b0d4`: `btnMoveValueDown`
- `0x1b072`: `var component=$find('{0}'); var selectedValue = component.get_selectedValue(); if(!IsNull(selectedValue) && selectedValue >= 0) component.{{0}}();`
- `0x1b0c0`: `moveValueUp`
- `0x1b0ed`: `moveValueDown`
- `0x1b190`: `btnRemoveValue`
- `0x1b1a0`: `if({0}.get_selectedValue() != null){0}.removeValue(true,{0}.get_selectedValue());`

## pseudocode

```c

```

## disassembly

```asm
0x1b040  ldarg.1
0x1b041  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1b046  stloc.0
0x1b047  ldc.i4.0
0x1b048  stloc.1
0x1b049  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b04e  ldstr    aFind0// "$find('{0}')"
0x1b053  ldc.i4.1
0x1b054  newarr   [mscorlib]System.Object
0x1b059  dup
0x1b05a  ldc.i4.0
0x1b05b  ldarg.0
0x1b05c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x1b061  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x1b066  stelem.ref
0x1b067  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b06c  stloc.2
0x1b06d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b072  ldstr    aVarComponentFi// "var component=$find('{0}'); var selecte"...
0x1b077  ldc.i4.1
0x1b078  newarr   [mscorlib]System.Object
0x1b07d  dup
0x1b07e  ldc.i4.0
0x1b07f  ldarg.0
0x1b080  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x1b085  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x1b08a  stelem.ref
0x1b08b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b090  stloc.3
0x1b091  ldloc.0
0x1b092  ldstr    aTableWidth100C_0// "<table width=\"100%\" cellspacing=\"0\""...
0x1b097  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b09c  ldarg.0
0x1b09d  ldc.i4.1
0x1b09e  call     instance bool Microsoft.Crm.Application.Components.UI.ListEdit::CheckFunction(valuetype Function function)
0x1b0a3  brfalse.s loc_1B0FF
0x1b0a5  ldarg.0
0x1b0a6  ldarg.1
0x1b0a7  ldstr    aBtnmovevalueup// "btnMoveValueUp"
0x1b0ac  ldarg.0
0x1b0ad  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_MoveUpLabel()
0x1b0b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b0b7  ldloc.3
0x1b0b8  ldc.i4.1
0x1b0b9  newarr   [mscorlib]System.Object
0x1b0be  dup
0x1b0bf  ldc.i4.0
0x1b0c0  ldstr    aMovevalueup// "moveValueUp"
0x1b0c5  stelem.ref
0x1b0c6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b0cb  ldloca.s 1
0x1b0cd  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b0d2  ldarg.0
0x1b0d3  ldarg.1
0x1b0d4  ldstr    aBtnmovevaluedo// "btnMoveValueDown"
0x1b0d9  ldarg.0
0x1b0da  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_MoveDownLabel()
0x1b0df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b0e4  ldloc.3
0x1b0e5  ldc.i4.1
0x1b0e6  newarr   [mscorlib]System.Object
0x1b0eb  dup
0x1b0ec  ldc.i4.0
0x1b0ed  ldstr    aMovevaluedown// "moveValueDown"
0x1b0f2  stelem.ref
0x1b0f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b0f8  ldloca.s 1
0x1b0fa  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b0ff  ldarg.0
0x1b100  ldc.i4.2
0x1b101  call     instance bool Microsoft.Crm.Application.Components.UI.ListEdit::CheckFunction(valuetype Function function)
0x1b106  brfalse.s loc_1B135
0x1b108  ldarg.0
0x1b109  ldarg.1
0x1b10a  ldstr    aBtneditvalue// "btnEditValue"
0x1b10f  ldarg.0
0x1b110  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_EditLabel()
0x1b115  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b11a  ldloc.3
0x1b11b  ldc.i4.1
0x1b11c  newarr   [mscorlib]System.Object
0x1b121  dup
0x1b122  ldc.i4.0
0x1b123  ldstr    aEditvalue// "editValue"
0x1b128  stelem.ref
0x1b129  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b12e  ldloca.s 1
0x1b130  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b135  ldarg.0
0x1b136  ldc.i4.4
0x1b137  call     instance bool Microsoft.Crm.Application.Components.UI.ListEdit::CheckFunction(valuetype Function function)
0x1b13c  brfalse.s loc_1B1BB
0x1b13e  ldarg.0
0x1b13f  ldarg.1
0x1b140  ldstr    aBtnaddvalue// "btnAddValue"
0x1b145  ldarg.0
0x1b146  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_AddLabel()
0x1b14b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b150  ldloc.2
0x1b151  ldstr    aAddvalue0// ".addValue();{0}"
0x1b156  call     string [mscorlib]System.String::Concat(string, string)
0x1b15b  ldc.i4.1
0x1b15c  newarr   [mscorlib]System.Object
0x1b161  dup
0x1b162  ldc.i4.0
0x1b163  ldarg.0
0x1b164  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1b169  ldstr    aLedtstatusvalu// "ledtStatusValues"
0x1b16e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b173  brtrue.s loc_1B17C
0x1b175  ldsfld   string [mscorlib]System.String::Empty
0x1b17a  br.s     loc_1B181
0x1b17c  ldstr    aOnstatechange// "onStateChange();"
0x1b181  stelem.ref
0x1b182  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b187  ldloca.s 1
0x1b189  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b18e  ldarg.0
0x1b18f  ldarg.1
0x1b190  ldstr    aBtnremovevalue// "btnRemoveValue"
0x1b195  ldarg.0
0x1b196  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_RemoveLabel()
0x1b19b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b1a0  ldstr    aIf0GetSelected// "if({0}.get_selectedValue() != null){0}."...
0x1b1a5  ldc.i4.1
0x1b1a6  newarr   [mscorlib]System.Object
0x1b1ab  dup
0x1b1ac  ldc.i4.0
0x1b1ad  ldloc.2
0x1b1ae  stelem.ref
0x1b1af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b1b4  ldloca.s 1
0x1b1b6  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b1bb  ldarg.0
0x1b1bc  ldc.i4.s 0x10
0x1b1be  call     instance bool Microsoft.Crm.Application.Components.UI.ListEdit::CheckFunction(valuetype Function function)
0x1b1c3  brfalse.s loc_1B203
0x1b1c5  ldarg.0
0x1b1c6  ldarg.1
0x1b1c7  ldstr    aBtnsortasc// "btnSortAsc"
0x1b1cc  ldarg.0
0x1b1cd  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_SortAscLabel()
0x1b1d2  ldloc.2
0x1b1d3  ldstr    aSortvaluesTrue// ".sortValues(true);"
0x1b1d8  call     string [mscorlib]System.String::Concat(string, string)
0x1b1dd  ldloca.s 1
0x1b1df  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b1e4  ldarg.0
0x1b1e5  ldarg.1
0x1b1e6  ldstr    aBtnsortdesc// "btnSortDesc"
0x1b1eb  ldarg.0
0x1b1ec  call     instance string Microsoft.Crm.Application.Components.UI.ListEdit::get_SortDescLabel()
0x1b1f1  ldloc.2
0x1b1f2  ldstr    aSortvaluesFals// ".sortValues(false);"
0x1b1f7  call     string [mscorlib]System.String::Concat(string, string)
0x1b1fc  ldloca.s 1
0x1b1fe  call     instance void Microsoft.Crm.Application.Components.UI.ListEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string title, string onclick, bool& renderSpacer)
0x1b203  ldloc.0
0x1b204  ldstr    aTable_0// "</table>"
0x1b209  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b20e  ret
```
