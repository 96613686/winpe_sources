# Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderTimeControl

- ea: `0x16590`
- end: `0x16710`
- name: `Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderTimeControl`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x15ff0`

## callees

- `0x16590`
- `0x16710`
- `0x167a0`
- `0x167f0`
- `0x168d0`
- `0x179b0`
- `0x179d0`
- `0x179f0`
- `0x23c20`
- `0x23c30`
- `0x241d0`
- `0x241e0`
- `0x241f0`
- `0x24200`
- `0x242c0`
- `0x242d0`

## pseudocode

```c

```

## disassembly

```asm
0x16590  ldarg.0
0x16591  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x16596  ldarg.0
0x16597  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1659c  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x165a1  ldarg.0
0x165a2  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x165a7  ldarg.0
0x165a8  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Required()
0x165ad  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32 value)
0x165b2  ldarg.0
0x165b3  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x165b8  ldarg.0
0x165b9  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ImeMode()
0x165be  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_ImeMode(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode value)
0x165c3  ldarg.0
0x165c4  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x165c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x165ce  ldstr    aGeneralTimeBut// "General.Time.ButtonLabel"
0x165d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x165d8  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_ButtonTitle(string value)
0x165dd  ldarg.0
0x165de  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x165e3  brfalse.s loc_165F6
0x165e5  ldarg.0
0x165e6  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x165eb  ldarg.0
0x165ec  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x165f1  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_TabIndex(int32 value)
0x165f6  ldarg.0
0x165f7  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_ShowTime()
0x165fc  brtrue.s loc_16620
0x165fe  ldarg.0
0x165ff  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x16604  ldstr    aDatetime// "datetime"
0x16609  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1660e  brfalse.s loc_16620
0x16610  ldarg.0
0x16611  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x16616  ldstr    aDisplayNone// "display:none"
0x1661b  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_Style(string value)
0x16620  ldarg.0
0x16621  ldarg.0
0x16622  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x16627  call     instance void Microsoft.Crm.Application.Components.UI.DateTimeUI::AddTimeOptionsToPicklist(class Microsoft.Crm.Application.Components.UI.EditableSelect timeSelector)
0x1662c  ldarg.0
0x1662d  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x16632  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x16637  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1663c  brfalse.s loc_1666E
0x1663e  ldarg.0
0x1663f  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x16644  ldstr    aDatetime// "datetime"
0x16649  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1664e  brfalse.s loc_1666E
0x16650  ldarg.0
0x16651  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x16656  ldstr    asc_4C79A// " "
0x1665b  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_Selected(string value)
0x16660  ldarg.0
0x16661  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x16666  ldc.i4.1
0x16667  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x1666c  br.s     loc_16693
0x1666e  ldarg.0
0x1666f  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x16674  ldarg.0
0x16675  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x1667a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1667f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x16684  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16689  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatTime(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1668e  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_Selected(string value)
0x16693  ldarg.0
0x16694  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x16699  ldstr    aDatetime// "datetime"
0x1669e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x166a3  brfalse.s loc_166B2
0x166a5  ldarg.1
0x166a6  ldstr    aTdClassDatetim_0// "<td CLASS=\"DateTimeUI_RenderTimeContro"...
0x166ab  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x166b0  br.s     loc_166BD
0x166b2  ldarg.1
0x166b3  ldstr    aTdDiv// "<td><div>"
0x166b8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x166bd  ldarg.0
0x166be  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x166c3  ldstr    aDatetime// "datetime"
0x166c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x166cd  brfalse.s loc_166F8
0x166cf  ldarg.1
0x166d0  ldstr    aLabelClassMsCr// "<label class=\"ms-crm-Hidden\" for=\"ti"...
0x166d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x166da  ldstr    aGeneralTimeBut// "General.Time.ButtonLabel"
0x166df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x166e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x166e9  ldstr    aLabel_0// "</label>"
0x166ee  call     string [mscorlib]System.String::Concat(string, string, string)
0x166f3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x166f8  ldarg.0
0x166f9  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.DateTimeUI::_select
0x166fe  ldarg.1
0x166ff  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x16704  ldarg.1
0x16705  ldstr    aDivTd// "</div></td>"
0x1670a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1670f  ret
```
