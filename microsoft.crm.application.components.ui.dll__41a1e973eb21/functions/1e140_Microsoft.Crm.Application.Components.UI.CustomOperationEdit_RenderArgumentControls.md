# Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderArgumentControls

- ea: `0x1e140`
- end: `0x1e4c3`
- name: `Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderArgumentControls`
- size: `899`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1e6f0`

## callees

- `0x1d650`
- `0x1d670`
- `0x1d690`
- `0x1d6b0`
- `0x1d6d0`
- `0x1d6f0`
- `0x1db70`
- `0x1e040`
- `0x1e140`
- `0x1e4d0`
- `0x1e580`
- `0x1e6e0`
- `0x21160`
- `0x214a0`
- `0x22940`
- `0x229c0`
- `0x22da0`
- `0x23c20`
- `0x23c30`
- `0x24210`
- `0x26830`
- `0x26850`

## pseudocode

```c

```

## disassembly

```asm
0x1e140  ldarg.1
0x1e141  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e146  stloc.0
0x1e147  ldloc.0
0x1e148  ldstr    aTableClassStdt// "<table class=\"stdTable\" >"
0x1e14d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e152  ldloc.0
0x1e153  ldstr    aColWidth100// "<col width=\"100%\" >"
0x1e158  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e15d  ldloc.0
0x1e15e  ldstr    aTrTd// "<tr><td>"
0x1e163  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e168  ldloc.0
0x1e169  ldstr    aTableStyleTabl_0// "<table style=\"table-layout:fixed;\" wi"...
0x1e16e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e173  ldloc.0
0x1e174  ldstr    aColWidth85pxCo// "<col width=\"85px\" /><col />"
0x1e179  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e17e  ldloc.0
0x1e17f  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1e184  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e189  ldarg.0
0x1e18a  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1e18f  ldstr    aDonotsubmit// "DoNotSubmit"
0x1e194  ldstr    a1// "1"
0x1e199  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1e19e  ldarg.0
0x1e19f  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1e1a4  ldc.i4   0xFF
0x1e1a9  callvirt instance void Microsoft.Crm.Application.Components.UI.TextBox::set_MaxLength(int32 value)
0x1e1ae  ldarg.0
0x1e1af  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1e1b4  ldarg.0
0x1e1b5  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1e1ba  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1e1bf  ldarg.0
0x1e1c0  ldarg.1
0x1e1c1  ldc.i4.1
0x1e1c2  ldarg.0
0x1e1c3  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ItemNameLabel()
0x1e1c8  ldarg.0
0x1e1c9  ldfld    class Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtName
0x1e1ce  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1e1d3  ldloc.0
0x1e1d4  ldstr    aTr// "</tr>"
0x1e1d9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e1de  ldloc.0
0x1e1df  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1e1e4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e1e9  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::get_CustomOperationArgumentTypeStrings()
0x1e1ee  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortedNameList::.ctor()
0x1e1f3  stloc.1
0x1e1f4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, string>::GetEnumerator()
0x1e1f9  stloc.3
0x1e1fa  br.s     loc_1E228
0x1e1fc  ldloca.s 3
0x1e1fe  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [mscorlib]System.Type, string>::get_Current()
0x1e203  stloc.s  4
0x1e205  ldloc.1
0x1e206  ldloca.s 4
0x1e208  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, string>::get_Key()
0x1e20d  callvirt instance string [mscorlib]System.Object::ToString()
0x1e212  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e217  ldloca.s 4
0x1e219  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, string>::get_Value()
0x1e21e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e223  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortedNameList::Add(object, string)
0x1e228  ldloca.s 3
0x1e22a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [mscorlib]System.Type, string>::MoveNext()
0x1e22f  brtrue.s loc_1E1FC
0x1e231  leave.s  loc_1E241
0x1e233  ldloca.s 3
0x1e235  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [mscorlib]System.Type, string>
0x1e23b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e240  endfinally
0x1e241  ldloc.1
0x1e242  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortNameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.SortedNameList::get_SortedList()
0x1e247  stloc.2
0x1e248  ldc.i4.0
0x1e249  stloc.s  5
0x1e24b  br.s     loc_1E285
0x1e24d  ldarg.0
0x1e24e  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1e253  ldloc.2
0x1e254  ldloc.s  5
0x1e256  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Item(!!T0)
0x1e25b  stloc.s  6
0x1e25d  ldloca.s 6
0x1e25f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>::get_Value()
0x1e264  ldloc.2
0x1e265  ldloc.s  5
0x1e267  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Item(!!T0)
0x1e26c  stloc.s  6
0x1e26e  ldloca.s 6
0x1e270  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>::get_Key()
0x1e275  castclass [mscorlib]System.String
0x1e27a  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::AddItem(string text, string value)
0x1e27f  ldloc.s  5
0x1e281  ldc.i4.1
0x1e282  add
0x1e283  stloc.s  5
0x1e285  ldloc.s  5
0x1e287  ldloc.2
0x1e288  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, string>>::get_Count()
0x1e28d  blt.s    loc_1E24D
0x1e28f  ldarg.0
0x1e290  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1e295  ldarg.0
0x1e296  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1e29b  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1e2a0  ldarg.0
0x1e2a1  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1e2a6  ldstr    aDonotsubmit// "DoNotSubmit"
0x1e2ab  ldstr    a1// "1"
0x1e2b0  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::AddExpando(string name, string value)
0x1e2b5  ldarg.0
0x1e2b6  ldarg.1
0x1e2b7  ldc.i4.1
0x1e2b8  ldarg.0
0x1e2b9  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ItemTypeLabel()
0x1e2be  ldarg.0
0x1e2bf  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstType
0x1e2c4  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1e2c9  ldloc.0
0x1e2ca  ldstr    aTr// "</tr>"
0x1e2cf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e2d4  ldloc.0
0x1e2d5  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1e2da  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e2df  ldarg.0
0x1e2e0  ldarg.0
0x1e2e1  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1e2e6  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::PopulateEntityList(class Microsoft.Crm.Application.Components.UI.Select lstEntity)
0x1e2eb  ldarg.0
0x1e2ec  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1e2f1  ldarg.0
0x1e2f2  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1e2f7  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1e2fc  ldarg.0
0x1e2fd  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1e302  ldstr    aDonotsubmit// "DoNotSubmit"
0x1e307  ldstr    a1// "1"
0x1e30c  callvirt instance void Microsoft.Crm.Application.Components.UI.Select::AddExpando(string name, string value)
0x1e311  ldarg.0
0x1e312  ldarg.1
0x1e313  ldc.i4.0
0x1e314  ldarg.0
0x1e315  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ItemEntityLabel()
0x1e31a  ldarg.0
0x1e31b  ldfld    class Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_lstEntity
0x1e320  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1e325  ldloc.0
0x1e326  ldstr    aTr// "</tr>"
0x1e32b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e330  ldloc.0
0x1e331  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1e336  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e33b  ldarg.0
0x1e33c  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_chkRequired
0x1e341  ldarg.0
0x1e342  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1e347  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1e34c  ldarg.0
0x1e34d  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_chkRequired
0x1e352  ldstr    aDonotsubmit// "DoNotSubmit"
0x1e357  ldstr    a1// "1"
0x1e35c  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1e361  ldarg.0
0x1e362  ldarg.1
0x1e363  ldc.i4.0
0x1e364  ldarg.0
0x1e365  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ItemRequiredLabel()
0x1e36a  ldarg.0
0x1e36b  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_chkRequired
0x1e370  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1e375  ldloc.0
0x1e376  ldstr    aTr// "</tr>"
0x1e37b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e380  ldloc.0
0x1e381  ldstr    aTrClassParam// "<tr class=\"param\">"
0x1e386  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e38b  ldarg.0
0x1e38c  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1e391  ldarg.0
0x1e392  ldstr    aWebControlsCus// "Web._controls.customoperationedit.item."...
0x1e397  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1e39c  ldstr    a1// "1"
0x1e3a1  callvirt instance void Microsoft.Crm.Application.Components.UI.Radio::AddItem(string itemLabel, string itemValue)
0x1e3a6  ldarg.0
0x1e3a7  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1e3ac  ldarg.0
0x1e3ad  ldstr    aWebControlsCus_0// "Web._controls.customoperationedit.item."...
0x1e3b2  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::GetResourceString(string key)
0x1e3b7  ldstr    a0// "0"
0x1e3bc  callvirt instance void Microsoft.Crm.Application.Components.UI.Radio::AddItem(string itemLabel, string itemValue)
0x1e3c1  ldarg.0
0x1e3c2  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1e3c7  ldstr    a1// "1"
0x1e3cc  callvirt instance void Microsoft.Crm.Application.Components.UI.Radio::set_Value(string value)
0x1e3d1  ldarg.0
0x1e3d2  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1e3d7  ldarg.0
0x1e3d8  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1e3dd  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1e3e2  ldarg.0
0x1e3e3  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1e3e8  ldstr    aDonotsubmit// "DoNotSubmit"
0x1e3ed  ldstr    a1// "1"
0x1e3f2  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1e3f7  ldarg.0
0x1e3f8  ldarg.1
0x1e3f9  ldc.i4.0
0x1e3fa  ldarg.0
0x1e3fb  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ItemDirectionLabel()
0x1e400  ldarg.0
0x1e401  ldfld    class Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_direction
0x1e406  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1e40b  ldloc.0
0x1e40c  ldstr    aTr// "</tr>"
0x1e411  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e416  ldloc.0
0x1e417  ldstr    aTrValignTopCla// "<tr valign=\"top\" class=\"param\">"
0x1e41c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e421  ldarg.0
0x1e422  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1e427  ldstr    a60px// "60px"
0x1e42c  callvirt instance void Microsoft.Crm.Application.Components.UI.TextArea::set_Height(string value)
0x1e431  ldarg.0
0x1e432  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1e437  ldc.i4   0xFF
0x1e43c  callvirt instance void Microsoft.Crm.Application.Components.UI.TextArea::set_MaxLength(int32 value)
0x1e441  ldarg.0
0x1e442  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1e447  ldarg.0
0x1e448  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1e44d  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1e452  ldarg.0
0x1e453  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1e458  ldstr    aDonotsubmit// "DoNotSubmit"
0x1e45d  ldstr    a1// "1"
0x1e462  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1e467  ldarg.0
0x1e468  ldarg.1
0x1e469  ldc.i4.0
0x1e46a  ldarg.0
0x1e46b  call     instance string Microsoft.Crm.Application.Components.UI.CustomOperationEdit::get_ItemDescriptionLabel()
0x1e470  ldarg.0
0x1e471  ldfld    class Microsoft.Crm.Application.Components.UI.TextArea Microsoft.Crm.Application.Components.UI.CustomOperationEdit::_txtDesc
0x1e476  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderItemEditorValue(class [System.Web]System.Web.UI.HtmlTextWriter output, bool required, string label, class Microsoft.Crm.Application.Components.UI.CrmUIControl control)
0x1e47b  ldloc.0
0x1e47c  ldstr    aTr// "</tr>"
0x1e481  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e486  ldarg.0
0x1e487  ldc.i4.8
0x1e488  call     instance bool Microsoft.Crm.Application.Components.UI.CustomOperationEdit::CheckFunction(valuetype Microsoft.Crm.Application.Components.UI.CustomOperationFunction function)
0x1e48d  brfalse.s loc_1E4AC
0x1e48f  ldloc.0
0x1e490  ldstr    aTrTdNbspTdTdNb// "<tr><td>&nbsp;</td><td>&nbsp;</td></tr>"
0x1e495  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e49a  ldloc.0
0x1e49b  ldstr    aTrTdNbspTdTdNb// "<tr><td>&nbsp;</td><td>&nbsp;</td></tr>"
0x1e4a0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e4a5  ldarg.0
0x1e4a6  ldarg.1
0x1e4a7  call     instance void Microsoft.Crm.Application.Components.UI.CustomOperationEdit::RenderDefaultValue(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1e4ac  ldloc.0
0x1e4ad  ldstr    aTable_0// "</table>"
0x1e4b2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e4b7  ldloc.0
0x1e4b8  ldstr    aTdTrTrHeight99// "</td></tr><tr height=\"99%\"><td></td><"...
0x1e4bd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e4c2  ret
```
