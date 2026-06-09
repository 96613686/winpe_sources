# Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderOptionLists

- ea: `0x1c380`
- end: `0x1c596`
- name: `Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderOptionLists`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1c7c0`

## callees

- `0x1bbc0`
- `0x1bbe0`
- `0x1bc00`
- `0x1bc20`
- `0x1bc40`
- `0x1bf90`
- `0x1c380`
- `0x1c5a0`
- `0x1c650`
- `0x22940`
- `0x229c0`
- `0x22da0`
- `0x22de0`
- `0x23c20`
- `0x23c30`

## pseudocode

```c

```

## disassembly

```asm
0x1c380  ldarg.1
0x1c381  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1c386  stloc.0
0x1c387  ldloc.0
0x1c388  ldstr    aTableClassStdt// "<table class=\"stdTable\" >"
0x1c38d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c392  ldloc.0
0x1c393  ldstr    aColWidth100// "<col width=\"100%\" >"
0x1c398  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c39d  ldloc.0
0x1c39e  ldstr    aTrTd// "<tr><td>"
0x1c3a3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c3a8  ldloc.0
0x1c3a9  ldstr    aTableWidth100C_2// "<table  width=\"100%\" cellspacing=\"0"...
0x1c3ae  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c3b3  ldloc.0
0x1c3b4  ldstr    aColStyleWidth1_0// "<col style=\"width:115px\" /><col />"
0x1c3b9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c3be  ldloc.0
0x1c3bf  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1c3c4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c3c9  ldarg.0
0x1c3ca  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtLb
0x1c3cf  ldc.i4   0xFF
0x1c3d4  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_MaxLength(int32 value)
0x1c3d9  ldarg.0
0x1c3da  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtLb
0x1c3df  ldarg.0
0x1c3e0  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1c3e5  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1c3ea  ldarg.0
0x1c3eb  ldarg.1
0x1c3ec  ldc.i4.1
0x1c3ed  ldarg.0
0x1c3ee  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_ItemLabelLabel()
0x1c3f3  ldarg.0
0x1c3f4  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtLb
0x1c3f9  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1c3fe  ldloc.0
0x1c3ff  ldstr    aTr// "</tr>"
0x1c404  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c409  ldloc.0
0x1c40a  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1c40f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c414  ldarg.0
0x1c415  ldarg.1
0x1c416  ldc.i4.1
0x1c417  ldarg.0
0x1c418  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_ItemValueLabel()
0x1c41d  ldarg.0
0x1c41e  ldfld    class Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Components.UI.PicklistEdit::_numBox
0x1c423  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1c428  ldloc.0
0x1c429  ldstr    aTr// "</tr>"
0x1c42e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c433  ldarg.0
0x1c434  ldfld    bool Microsoft.Crm.Application.Components.UI.PicklistEdit::_hideExternalName
0x1c439  brtrue.s loc_1C486
0x1c43b  ldloc.0
0x1c43c  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1c441  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c446  ldarg.0
0x1c447  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtExtName
0x1c44c  ldc.i4   0xFF
0x1c451  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_MaxLength(int32 value)
0x1c456  ldarg.0
0x1c457  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtExtName
0x1c45c  ldarg.0
0x1c45d  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1c462  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1c467  ldarg.0
0x1c468  ldarg.1
0x1c469  ldc.i4.0
0x1c46a  ldarg.0
0x1c46b  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_ItemExternalNameLabel()
0x1c470  ldarg.0
0x1c471  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtExtName
0x1c476  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1c47b  ldloc.0
0x1c47c  ldstr    aTr// "</tr>"
0x1c481  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c486  ldloc.0
0x1c487  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1c48c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c491  ldarg.0
0x1c492  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1c497  ldstr    a60px// "60px"
0x1c49c  callvirt instance void Microsoft.Crm.Application.Components.UI.TextArea::set_Height(string value)
0x1c4a1  ldarg.0
0x1c4a2  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1c4a7  ldc.i4   0xFF
0x1c4ac  callvirt instance void Microsoft.Crm.Application.Components.UI.TextArea::set_MaxLength(int32 value)
0x1c4b1  ldarg.0
0x1c4b2  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1c4b7  ldarg.0
0x1c4b8  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1c4bd  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1c4c2  ldarg.0
0x1c4c3  ldarg.1
0x1c4c4  ldc.i4.0
0x1c4c5  ldarg.0
0x1c4c6  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_ItemDescriptionLabel()
0x1c4cb  ldarg.0
0x1c4cc  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtDesc
0x1c4d1  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1c4d6  ldloc.0
0x1c4d7  ldstr    aTr// "</tr>"
0x1c4dc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c4e1  ldloc.0
0x1c4e2  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1c4e7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c4ec  ldarg.0
0x1c4ed  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1c4f2  ldc.i4.7
0x1c4f3  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_MaxLength(int32 value)
0x1c4f8  ldarg.0
0x1c4f9  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1c4fe  ldarg.0
0x1c4ff  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1c504  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1c509  ldarg.0
0x1c50a  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1c50f  ldstr    aJavascriptVali// "javascript:validateAndPreview()"
0x1c514  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_OnChange(string value)
0x1c519  ldarg.0
0x1c51a  ldarg.1
0x1c51b  ldc.i4.0
0x1c51c  ldarg.0
0x1c51d  call     instance string Microsoft.Crm.Application.Components.UI.PicklistEdit::get_ItemColorLabel()
0x1c522  ldarg.0
0x1c523  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.PicklistEdit::_txtColor
0x1c528  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1c52d  ldloc.0
0x1c52e  ldstr    aTdStyleWidth30// "<td style=\"width: 30px;\">"
0x1c533  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c538  ldloc.0
0x1c539  ldstr    aDivIdDivprevie// "<div id=\"divPreviewColor\" class =\"ms"...
0x1c53e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c543  ldloc.0
0x1c544  ldstr    aDivTd// "</div></td>"
0x1c549  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c54e  ldloc.0
0x1c54f  ldstr    aTr// "</tr>"
0x1c554  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c559  ldarg.0
0x1c55a  ldc.i4.8
0x1c55b  call     instance bool Microsoft.Crm.Application.Components.UI.PicklistEdit::CheckFunction(valuetype Function function)
0x1c560  brfalse.s loc_1C57F
0x1c562  ldloc.0
0x1c563  ldstr    aTrTdNbspTdTdNb// "<tr><td>&nbsp;</td><td>&nbsp;</td></tr>"
0x1c568  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c56d  ldloc.0
0x1c56e  ldstr    aTrTdNbspTdTdNb// "<tr><td>&nbsp;</td><td>&nbsp;</td></tr>"
0x1c573  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c578  ldarg.0
0x1c579  ldarg.1
0x1c57a  call     instance void Microsoft.Crm.Application.Components.UI.PicklistEdit::RenderDefaultValue(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1c57f  ldloc.0
0x1c580  ldstr    aTable_0// "</table>"
0x1c585  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c58a  ldloc.0
0x1c58b  ldstr    aTdTrTrHeight99// "</td></tr><tr height=\"99%\"><td></td><"...
0x1c590  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c595  ret
```
