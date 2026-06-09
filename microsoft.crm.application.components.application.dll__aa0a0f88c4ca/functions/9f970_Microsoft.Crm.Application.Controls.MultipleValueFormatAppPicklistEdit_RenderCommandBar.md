# Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderCommandBar

- ea: `0x9f970`
- end: `0x9fad1`
- name: `Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderCommandBar`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0xa0080`

## callees

- `0x9f480`
- `0x9f4a0`
- `0x9f4e0`
- `0x9f500`
- `0x9f520`
- `0x9f540`
- `0x9f960`
- `0x9f970`
- `0x9fae0`
- `0x9faf0`

## string_xrefs

- `0x9f978`: `<table id="CommandBar" width="100%" class="ms-crm-Picklist-MenuBar">`
- `0x9f9ba`: `btnRemoveValue`
- `0x9f9bf`: `remove`
- `0x9f9da`: `btnMoveValueUp`
- `0x9f9df`: `moveup`
- `0x9f9f1`: `btnMoveValueDown`
- `0x9f9f6`: `movedown`

## pseudocode

```c

```

## disassembly

```asm
0x9f970  ldarg.1
0x9f971  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x9f976  stloc.0
0x9f977  ldloc.0
0x9f978  ldstr    aTableIdCommand// "<table id=\"CommandBar\" width=\"100%\""...
0x9f97d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9f982  ldloc.0
0x9f983  ldstr    aTrAlignLeft// "<tr align=\"left\">"
0x9f988  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9f98d  ldloc.0
0x9f98e  ldstr    aTdAlignLeft// "<td align=\"left\" >"
0x9f993  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9f998  ldarg.0
0x9f999  ldc.i4.4
0x9f99a  call     instance bool Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::CheckFunction(valuetype Microsoft.Crm.Application.Controls.OptionSetFunction function)
0x9f99f  brfalse.s loc_9F9CF
0x9f9a1  ldarg.0
0x9f9a2  ldarg.1
0x9f9a3  ldstr    aBtnaddvalue// "btnAddValue"
0x9f9a8  ldstr    aAdd_0// "add"
0x9f9ad  ldarg.0
0x9f9ae  call     instance string Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::get_AddLabel()
0x9f9b3  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x9f9b8  ldarg.0
0x9f9b9  ldarg.1
0x9f9ba  ldstr    aBtnremovevalue// "btnRemoveValue"
0x9f9bf  ldstr    aRemove// "remove"
0x9f9c4  ldarg.0
0x9f9c5  call     instance string Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::get_RemoveLabel()
0x9f9ca  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x9f9cf  ldarg.0
0x9f9d0  ldc.i4.1
0x9f9d1  call     instance bool Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::CheckFunction(valuetype Microsoft.Crm.Application.Controls.OptionSetFunction function)
0x9f9d6  brfalse.s loc_9FA06
0x9f9d8  ldarg.0
0x9f9d9  ldarg.1
0x9f9da  ldstr    aBtnmovevalueup// "btnMoveValueUp"
0x9f9df  ldstr    aMoveup// "moveup"
0x9f9e4  ldarg.0
0x9f9e5  call     instance string Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::get_MoveUpLabel()
0x9f9ea  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x9f9ef  ldarg.0
0x9f9f0  ldarg.1
0x9f9f1  ldstr    aBtnmovevaluedo// "btnMoveValueDown"
0x9f9f6  ldstr    aMovedown// "movedown"
0x9f9fb  ldarg.0
0x9f9fc  call     instance string Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::get_MoveDownLabel()
0x9fa01  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x9fa06  ldarg.0
0x9fa07  ldc.i4.s 0x10
0x9fa09  call     instance bool Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::CheckFunction(valuetype Microsoft.Crm.Application.Controls.OptionSetFunction function)
0x9fa0e  brfalse.s loc_9FA3E
0x9fa10  ldarg.0
0x9fa11  ldarg.1
0x9fa12  ldstr    aBtnsortasc// "btnSortAsc"
0x9fa17  ldstr    aSortasc// "sortasc"
0x9fa1c  ldarg.0
0x9fa1d  call     instance string Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::get_SortAscendingLabel()
0x9fa22  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x9fa27  ldarg.0
0x9fa28  ldarg.1
0x9fa29  ldstr    aBtnsortdesc// "btnSortDesc"
0x9fa2e  ldstr    aSortdes// "sortdes"
0x9fa33  ldarg.0
0x9fa34  call     instance string Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::get_SortDescendingLabel()
0x9fa39  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter output, string id, string command, string title)
0x9fa3e  ldarg.0
0x9fa3f  ldc.i4.2
0x9fa40  call     instance bool Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::CheckFunction(valuetype Microsoft.Crm.Application.Controls.OptionSetFunction function)
0x9fa45  brfalse.s loc_9FAA7
0x9fa47  ldloc.0
0x9fa48  ldstr    aTdWidth1px// "<td width=\"1px\">"
0x9fa4d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fa52  ldloc.0
0x9fa53  ldstr    aSpanClassMsCrm_11// "<SPAN class=\"ms-crm-optionset-Label\">"...
0x9fa58  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fa5d  ldloc.0
0x9fa5e  ldstr    aTabindex1HrefJ// "\" tabindex = -1 href=\"javascript:oncl"...
0x9fa63  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fa68  ldloc.0
0x9fa69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fa6e  ldstr    a0Btneditvalue// "{0}_btnEditValue"
0x9fa73  ldc.i4.1
0x9fa74  newarr   [mscorlib]System.Object
0x9fa79  dup
0x9fa7a  ldc.i4.0
0x9fa7b  ldarg.0
0x9fa7c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x9fa81  stelem.ref
0x9fa82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9fa87  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x9fa8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fa91  ldloc.0
0x9fa92  ldstr    aSpan_7// "\"/></SPAN>"
0x9fa97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fa9c  ldloc.0
0x9fa9d  ldstr    aTd// "</td>"
0x9faa2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9faa7  ldloc.0
0x9faa8  ldstr    aTd// "</td>"
0x9faad  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fab2  ldarg.0
0x9fab3  ldloc.0
0x9fab4  call     instance void Microsoft.Crm.Application.Controls.MultipleValueFormatAppPicklistEdit::AddFiller(class [mscorlib]System.IO.TextWriter output)
0x9fab9  ldloc.0
0x9faba  ldstr    aTrTable// "</tr></table>"
0x9fabf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9fac4  leave.s  loc_9FAD0
0x9fac6  ldloc.0
0x9fac7  brfalse.s loc_9FACF
0x9fac9  ldloc.0
0x9faca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9facf  endfinally
0x9fad0  ret
```
