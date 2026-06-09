# Microsoft.Crm.Application.Components.UI.Select::Render

- ea: `0x26880`
- end: `0x26b0c`
- name: `Microsoft.Crm.Application.Components.UI.Select::Render`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x23c20`
- `0x24120`
- `0x24280`
- `0x242c0`
- `0x25e30`
- `0x25e50`
- `0x25ff0`
- `0x26000`
- `0x26050`
- `0x26060`
- `0x260a0`
- `0x26880`

## pseudocode

```c

```

## disassembly

```asm
0x26880  ldarg.0
0x26881  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x26886  brfalse  loc_26925
0x2688b  ldarg.0
0x2688c  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_selected
0x26891  brfalse  loc_26B0B
0x26896  ldarg.0
0x26897  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Application.Components.UI.Select::_optionGroups
0x2689c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x268a1  stloc.0
0x268a2  br.s     loc_26907
0x268a4  ldloc.0
0x268a5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x268aa  castclass Microsoft.Crm.Application.Components.UI.OptionGroup
0x268af  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x268b4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x268b9  stloc.1
0x268ba  br.s     loc_268EC
0x268bc  ldloc.1
0x268bd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x268c2  castclass Microsoft.Crm.Application.Components.UI.Option
0x268c7  stloc.2
0x268c8  ldloc.2
0x268c9  callvirt instance string Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x268ce  ldarg.0
0x268cf  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_selected
0x268d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x268d9  brfalse.s loc_268EC
0x268db  ldloc.2
0x268dc  callvirt instance string Microsoft.Crm.Application.Components.UI.Option::get_Text()
0x268e1  ldarg.1
0x268e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x268e7  leave    loc_26B0B
0x268ec  ldloc.1
0x268ed  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x268f2  brtrue.s loc_268BC
0x268f4  leave.s  loc_26907
0x268f6  ldloc.1
0x268f7  isinst   [mscorlib]System.IDisposable
0x268fc  stloc.3
0x268fd  ldloc.3
0x268fe  brfalse.s loc_26906
0x26900  ldloc.3
0x26901  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26906  endfinally
0x26907  ldloc.0
0x26908  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2690d  brtrue.s loc_268A4
0x2690f  leave    loc_26B0B
0x26914  ldloc.0
0x26915  isinst   [mscorlib]System.IDisposable
0x2691a  stloc.3
0x2691b  ldloc.3
0x2691c  brfalse.s loc_26924
0x2691e  ldloc.3
0x2691f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26924  endfinally
0x26925  ldarg.1
0x26926  ldstr    aSelect_2// "<select "
0x2692b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26930  ldarg.1
0x26931  ldarg.0
0x26932  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x26937  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2693c  ldarg.0
0x2693d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x26942  brfalse.s loc_2696E
0x26944  ldstr    aId// "id"
0x26949  ldarg.0
0x2694a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2694f  ldarg.1
0x26950  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x26955  ldarg.0
0x26956  ldfld    bool Microsoft.Crm.Application.Components.UI.Select::_renderNameAttribute
0x2695b  brfalse.s loc_2696E
0x2695d  ldstr    aName_0// "name"
0x26962  ldarg.0
0x26963  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x26968  ldarg.1
0x26969  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2696e  ldarg.0
0x2696f  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_selected
0x26974  brfalse.s loc_26987
0x26976  ldstr    aDefaultselecte_1// "defaultSelected"
0x2697b  ldarg.0
0x2697c  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_selected
0x26981  ldarg.1
0x26982  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x26987  ldc.i4.s 0x40
0x26989  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x2698e  stloc.s  4
0x26990  ldarg.0
0x26991  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Application.Components.UI.Select::_classNames
0x26996  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x2699b  stloc.0
0x2699c  br.s     loc_269BF
0x2699e  ldloc.0
0x2699f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x269a4  castclass [mscorlib]System.String
0x269a9  stloc.s  5
0x269ab  ldloc.s  4
0x269ad  ldloc.s  5
0x269af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x269b4  pop
0x269b5  ldloc.s  4
0x269b7  ldc.i4.s 0x20
0x269b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x269be  pop
0x269bf  ldloc.0
0x269c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x269c5  brtrue.s loc_2699E
0x269c7  leave.s  loc_269DA
0x269c9  ldloc.0
0x269ca  isinst   [mscorlib]System.IDisposable
0x269cf  stloc.3
0x269d0  ldloc.3
0x269d1  brfalse.s loc_269D9
0x269d3  ldloc.3
0x269d4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x269d9  endfinally
0x269da  ldstr    aClass_1// "class"
0x269df  ldloc.s  4
0x269e1  callvirt instance string [mscorlib]System.Object::ToString()
0x269e6  ldarg.1
0x269e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x269ec  ldarg.0
0x269ed  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x269f2  ldc.i4.0
0x269f3  ble.s    loc_26A1A
0x269f5  ldarg.1
0x269f6  ldstr    aTabindex// "tabindex"
0x269fb  ldarg.0
0x269fc  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x26a01  stloc.s  6
0x26a03  ldloca.s 6
0x26a05  ldstr    aD_1// "D"
0x26a0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26a0f  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x26a14  ldc.i4.0
0x26a15  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x26a1a  ldarg.0
0x26a1b  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_onChange
0x26a20  brfalse.s loc_26A33
0x26a22  ldstr    aOnchange_0// "onchange"
0x26a27  ldarg.0
0x26a28  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_onChange
0x26a2d  ldarg.1
0x26a2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x26a33  ldarg.0
0x26a34  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x26a39  brfalse.s loc_26A46
0x26a3b  ldarg.1
0x26a3c  ldstr    aDisabled_0// " disabled"
0x26a41  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26a46  ldarg.0
0x26a47  ldfld    valuetype Microsoft.Crm.Application.Components.UI.OptionSorting Microsoft.Crm.Application.Components.UI.Select::_sorting
0x26a4c  brfalse.s loc_26A74
0x26a4e  ldstr    aSort// "Sort"
0x26a53  ldarg.0
0x26a54  ldflda   valuetype Microsoft.Crm.Application.Components.UI.OptionSorting Microsoft.Crm.Application.Components.UI.Select::_sorting
0x26a59  constrained. Microsoft.Crm.Application.Components.UI.OptionSorting
0x26a5f  callvirt instance string [mscorlib]System.Object::ToString()
0x26a64  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26a69  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x26a6e  ldarg.1
0x26a6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x26a74  ldarg.1
0x26a75  ldstr    asc_2B7B6// ">"
0x26a7a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26a7f  ldarg.0
0x26a80  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Application.Components.UI.Select::_optionGroups
0x26a85  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x26a8a  stloc.0
0x26a8b  br.s     loc_26AE5
0x26a8d  ldloc.0
0x26a8e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x26a93  castclass Microsoft.Crm.Application.Components.UI.OptionGroup
0x26a98  stloc.s  7
0x26a9a  ldloc.s  7
0x26a9c  ldarg.0
0x26a9d  ldfld    string Microsoft.Crm.Application.Components.UI.Select::_selected
0x26aa2  callvirt instance void Microsoft.Crm.Application.Components.UI.OptionGroup::set_Selected(string value)
0x26aa7  ldloc.s  7
0x26aa9  callvirt instance valuetype Microsoft.Crm.Application.Components.UI.OptionSorting Microsoft.Crm.Application.Components.UI.OptionGroup::get_Sorting()
0x26aae  ldc.i4.3
0x26aaf  bne.un.s loc_26ADD
0x26ab1  ldloc.s  7
0x26ab3  ldarg.0
0x26ab4  ldfld    valuetype Microsoft.Crm.Application.Components.UI.OptionSorting Microsoft.Crm.Application.Components.UI.Select::_sorting
0x26ab9  callvirt instance void Microsoft.Crm.Application.Components.UI.OptionGroup::set_Sorting(valuetype Microsoft.Crm.Application.Components.UI.OptionSorting value)
0x26abe  ldloc.s  7
0x26ac0  ldarg.0
0x26ac1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Components.UI.Select::_cultureInfo
0x26ac6  callvirt instance void Microsoft.Crm.Application.Components.UI.OptionGroup::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo value)
0x26acb  ldloc.s  7
0x26acd  ldarg.1
0x26ace  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x26ad3  ldloc.s  7
0x26ad5  ldc.i4.3
0x26ad6  callvirt instance void Microsoft.Crm.Application.Components.UI.OptionGroup::set_Sorting(valuetype Microsoft.Crm.Application.Components.UI.OptionSorting value)
0x26adb  br.s     loc_26AE5
0x26add  ldloc.s  7
0x26adf  ldarg.1
0x26ae0  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x26ae5  ldloc.0
0x26ae6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26aeb  brtrue.s loc_26A8D
0x26aed  leave.s  loc_26B00
0x26aef  ldloc.0
0x26af0  isinst   [mscorlib]System.IDisposable
0x26af5  stloc.3
0x26af6  ldloc.3
0x26af7  brfalse.s loc_26AFF
0x26af9  ldloc.3
0x26afa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26aff  endfinally
0x26b00  ldarg.1
0x26b01  ldstr    aSelect_1// "</select>"
0x26b06  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26b0b  ret
```
