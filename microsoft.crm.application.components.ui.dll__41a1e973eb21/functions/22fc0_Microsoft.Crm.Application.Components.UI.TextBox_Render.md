# Microsoft.Crm.Application.Components.UI.TextBox::Render

- ea: `0x22fc0`
- end: `0x231e2`
- name: `Microsoft.Crm.Application.Components.UI.TextBox::Render`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x22d90`
- `0x22df0`
- `0x22e10`
- `0x22e90`
- `0x22eb0`
- `0x22ed0`
- `0x22ef0`
- `0x22fc0`
- `0x231f0`
- `0x23c20`
- `0x24120`
- `0x24280`
- `0x242c0`

## string_xrefs

- `0x2313f`: ` ms-crm-ReadOnly`
- `0x2311b`: `readonly`
- `0x23120`: `readonly`
- `0x2304a`: `SM_Customer_Service_Schedule_Dialog_Title_01`

## pseudocode

```c

```

## disassembly

```asm
0x22fc0  ldarg.0
0x22fc1  ldarg.1
0x22fc2  call     instance void Microsoft.Crm.Application.Components.UI.TextBox::RenderTextBoxContainer(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x22fc7  ldarg.1
0x22fc8  ldstr    aInput_2// "<input "
0x22fcd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x22fd2  ldarg.1
0x22fd3  ldstr    aType// "type"
0x22fd8  ldarg.0
0x22fd9  ldfld    bool Microsoft.Crm.Application.Components.UI.TextBox::_isPassword
0x22fde  brtrue.s loc_22FF6
0x22fe0  ldarg.0
0x22fe1  ldfld    bool Microsoft.Crm.Application.Components.UI.TextBox::_isColorValue
0x22fe6  brtrue.s loc_22FEF
0x22fe8  ldstr    aText// "text"
0x22fed  br.s     loc_22FFB
0x22fef  ldstr    aColor// "color"
0x22ff4  br.s     loc_22FFB
0x22ff6  ldstr    aPassword// "password"
0x22ffb  ldc.i4.0
0x22ffc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x23001  ldstr    aId// "id"
0x23006  ldarg.0
0x23007  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2300c  ldarg.1
0x2300d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x23012  ldarg.0
0x23013  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_ToolTip()
0x23018  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2301d  brtrue.s loc_23033
0x2301f  ldarg.1
0x23020  ldstr    aTitle_2// "title"
0x23025  ldarg.0
0x23026  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_ToolTip()
0x2302b  ldc.i4.0
0x2302c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x23031  br.s     loc_23062
0x23033  ldarg.0
0x23034  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x23039  ldstr    aTxtname// "txtName"
0x2303e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23043  brfalse.s loc_23062
0x23045  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2304a  ldstr    aSmCustomerServ_0// "SM_Customer_Service_Schedule_Dialog_Tit"...
0x2304f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x23054  stloc.1
0x23055  ldarg.1
0x23056  ldstr    aTitle_2// "title"
0x2305b  ldloc.1
0x2305c  ldc.i4.0
0x2305d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x23062  ldarg.0
0x23063  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x23068  brfalse.s loc_2308E
0x2306a  ldarg.1
0x2306b  ldstr    aTabindex// "tabindex"
0x23070  ldarg.0
0x23071  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x23076  stloc.2
0x23077  ldloca.s 2
0x23079  ldstr    aD_1// "D"
0x2307e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23083  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x23088  ldc.i4.0
0x23089  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2308e  ldarg.0
0x2308f  call     instance int32 Microsoft.Crm.Application.Components.UI.TextBox::get_MaxLength()
0x23094  ldc.i4.m1
0x23095  beq.s    loc_230BB
0x23097  ldarg.1
0x23098  ldstr    aMaxlength// "maxlength"
0x2309d  ldarg.0
0x2309e  call     instance int32 Microsoft.Crm.Application.Components.UI.TextBox::get_MaxLength()
0x230a3  stloc.2
0x230a4  ldloca.s 2
0x230a6  ldstr    aD_1// "D"
0x230ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x230b0  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x230b5  ldc.i4.0
0x230b6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x230bb  ldarg.0
0x230bc  ldfld    bool Microsoft.Crm.Application.Components.UI.TextBox::_isColorValue
0x230c1  brtrue.s loc_230CA
0x230c3  ldstr    aMsCrmInput_1// "ms-crm-Input "
0x230c8  br.s     loc_230CF
0x230ca  ldstr    aMsCrmInputMsCr// "ms-crm-Input ms-crm-InputColor "
0x230cf  stloc.0
0x230d0  ldloc.0
0x230d1  ldarg.0
0x230d2  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_InnerCssClass()
0x230d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x230dc  brtrue.s loc_230E6
0x230de  ldarg.0
0x230df  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_InnerCssClass()
0x230e4  br.s     loc_230EB
0x230e6  ldstr    aMsCrmText// "ms-crm-Text"
0x230eb  call     string [mscorlib]System.String::Concat(string, string)
0x230f0  stloc.0
0x230f1  ldarg.0
0x230f2  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x230f7  brtrue.s loc_23101
0x230f9  ldarg.0
0x230fa  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x230ff  brfalse.s loc_2314A
0x23101  ldarg.1
0x23102  ldstr    aContenteditabl_2// "contenteditable"
0x23107  ldstr    aFalse// "false"
0x2310c  ldc.i4.0
0x2310d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x23112  ldarg.0
0x23113  call     instance bool Microsoft.Crm.Application.Components.UI.TextBox::get_ContentCopyAble()
0x23118  brfalse.s loc_2312D
0x2311a  ldarg.1
0x2311b  ldstr    aReadonly_1// "readonly"
0x23120  ldstr    aReadonly_1// "readonly"
0x23125  ldc.i4.0
0x23126  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2312b  br.s     loc_2313E
0x2312d  ldarg.1
0x2312e  ldstr    aDisabled// "disabled"
0x23133  ldstr    aDisabled// "disabled"
0x23138  ldc.i4.0
0x23139  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2313e  ldloc.0
0x2313f  ldstr    aMsCrmReadonly// " ms-crm-ReadOnly"
0x23144  call     string [mscorlib]System.String::Concat(string, string)
0x23149  stloc.0
0x2314a  ldstr    aClass_1// "class"
0x2314f  ldloc.0
0x23150  ldarg.1
0x23151  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x23156  ldarg.0
0x23157  ldfld    string Microsoft.Crm.Application.Components.UI.TextBox::_onChange
0x2315c  brfalse.s loc_2317D
0x2315e  ldarg.0
0x2315f  ldfld    string Microsoft.Crm.Application.Components.UI.TextBox::_onChange
0x23164  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23169  ldc.i4.0
0x2316a  ble.s    loc_2317D
0x2316c  ldstr    aOnchange_0// "onchange"
0x23171  ldarg.0
0x23172  ldfld    string Microsoft.Crm.Application.Components.UI.TextBox::_onChange
0x23177  ldarg.1
0x23178  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2317d  ldarg.0
0x2317e  call     instance bool Microsoft.Crm.Application.Components.UI.TextBox::get_TrimValue()
0x23183  brtrue.s loc_231A5
0x23185  ldarg.1
0x23186  ldstr    aDefaulttrimval// "defaultTrimValue"
0x2318b  ldarg.0
0x2318c  call     instance bool Microsoft.Crm.Application.Components.UI.TextBox::get_TrimValue()
0x23191  brtrue.s loc_2319A
0x23193  ldstr    aFalse// "false"
0x23198  br.s     loc_2319F
0x2319a  ldstr    aTrue// "true"
0x2319f  ldc.i4.0
0x231a0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x231a5  ldstr    aValue_0// "value"
0x231aa  ldarg.0
0x231ab  call     instance string Microsoft.Crm.Application.Components.UI.TextBox::get_Text()
0x231b0  ldarg.1
0x231b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x231b6  ldarg.1
0x231b7  ldarg.0
0x231b8  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x231bd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x231c2  ldarg.0
0x231c3  call     instance bool Microsoft.Crm.Application.Components.UI.TextBox::get_IsHidden()
0x231c8  brfalse.s loc_231D6
0x231ca  ldarg.1
0x231cb  ldstr    aStyleDisplayNo_2// "style=\"display:none;\""
0x231d0  ldarg.1
0x231d1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x231d6  ldarg.1
0x231d7  ldstr    aDiv_8// "></div>"
0x231dc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x231e1  ret
```
