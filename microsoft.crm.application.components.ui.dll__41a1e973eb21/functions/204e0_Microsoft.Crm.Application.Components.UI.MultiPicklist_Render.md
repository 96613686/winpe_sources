# Microsoft.Crm.Application.Components.UI.MultiPicklist::Render

- ea: `0x204e0`
- end: `0x20735`
- name: `Microsoft.Crm.Application.Components.UI.MultiPicklist::Render`
- size: `597`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x20450`
- `0x204e0`
- `0x20740`
- `0x20780`
- `0x23c20`
- `0x240a0`
- `0x24120`
- `0x242c0`
- `0x26080`

## string_xrefs

- `0x20557`: `OptionsXml`
- `0x206d6`: ` readonly></TD><TD></TD><TD><BUTTON `

## pseudocode

```c

```

## disassembly

```asm
0x204e0  ldarg.1
0x204e1  ldstr    aSpan_4// "<span"
0x204e6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x204eb  ldarg.0
0x204ec  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x204f1  brfalse.s loc_20512
0x204f3  ldarg.0
0x204f4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x204f9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x204fe  ldc.i4.0
0x204ff  ble.s    loc_20512
0x20501  ldstr    aId// "id"
0x20506  ldarg.0
0x20507  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2050c  ldarg.1
0x2050d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20512  ldarg.1
0x20513  ldstr    aClassMultipick// " class=\"multipicklist\""
0x20518  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2051d  ldsfld   string [mscorlib]System.String::Empty
0x20522  stloc.0
0x20523  ldarg.0
0x20524  ldfld    class Microsoft.Crm.Application.Components.UI.OptionGroup Microsoft.Crm.Application.Components.UI.MultiPicklist::_optionGroup
0x20529  brfalse.s loc_20557
0x2052b  ldarg.0
0x2052c  ldfld    class Microsoft.Crm.Application.Components.UI.OptionGroup Microsoft.Crm.Application.Components.UI.MultiPicklist::_optionGroup
0x20531  ldc.i4.0
0x20532  callvirt instance void Microsoft.Crm.Application.Components.UI.OptionGroup::set_DisplayGrouping(bool value)
0x20537  ldstr    aSelect_0// "<select>"
0x2053c  ldarg.0
0x2053d  ldfld    class Microsoft.Crm.Application.Components.UI.OptionGroup Microsoft.Crm.Application.Components.UI.MultiPicklist::_optionGroup
0x20542  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_OuterHtml()
0x20547  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x2054c  ldstr    aSelect_1// "</select>"
0x20551  call     string [mscorlib]System.String::Concat(string, string, string)
0x20556  stloc.0
0x20557  ldstr    aOptionsxml// "OptionsXml"
0x2055c  ldloc.0
0x2055d  ldarg.1
0x2055e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20563  ldarg.1
0x20564  ldarg.0
0x20565  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x2056a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2056f  ldarg.1
0x20570  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20575  ldstr    aTableClassMult// " ><TABLE class=\"multipicklist\" {0}"
0x2057a  ldc.i4.1
0x2057b  newarr   [mscorlib]System.Object
0x20580  dup
0x20581  ldc.i4.0
0x20582  ldarg.0
0x20583  call     instance bool Microsoft.Crm.Application.Components.UI.MultiPicklist::get_IsMultipleSelectionAllowed()
0x20588  brtrue.s loc_205B3
0x2058a  ldstr    aIsmultiplesele// "IsMultipleSelectionAllowed=\""
0x2058f  ldarg.0
0x20590  call     instance bool Microsoft.Crm.Application.Components.UI.MultiPicklist::get_IsMultipleSelectionAllowed()
0x20595  stloc.3
0x20596  ldloca.s 3
0x20598  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2059d  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x205a2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x205a7  ldstr    asc_32802// "\""
0x205ac  call     string [mscorlib]System.String::Concat(string, string, string)
0x205b1  br.s     loc_205B8
0x205b3  ldsfld   string [mscorlib]System.String::Empty
0x205b8  stelem.ref
0x205b9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x205be  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x205c3  ldarg.0
0x205c4  ldfld    string Microsoft.Crm.Application.Components.UI.MultiPicklist::_width
0x205c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x205ce  brtrue.s loc_205E1
0x205d0  ldstr    aWidth// "width"
0x205d5  ldarg.0
0x205d6  call     instance string Microsoft.Crm.Application.Components.UI.MultiPicklist::get_Width()
0x205db  ldarg.1
0x205dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x205e1  ldarg.0
0x205e2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x205e7  brfalse.s loc_2061B
0x205e9  ldarg.0
0x205ea  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x205ef  callvirt instance int32 [mscorlib]System.String::get_Length()
0x205f4  ldc.i4.0
0x205f5  ble.s    loc_2061B
0x205f7  ldarg.0
0x205f8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x205fd  ldstr    aInput_1// "_input"
0x20602  call     string [mscorlib]System.String::Concat(string, string)
0x20607  stloc.1
0x20608  ldarg.0
0x20609  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2060e  ldstr    aButton_2// "_button"
0x20613  call     string [mscorlib]System.String::Concat(string, string)
0x20618  stloc.2
0x20619  br.s     loc_20627
0x2061b  ldstr    aMultipicklistI// "multipicklist_input"
0x20620  stloc.1
0x20621  ldstr    aMultipicklistB// "multipicklist_button"
0x20626  stloc.2
0x20627  ldarg.1
0x20628  ldstr    aColgroupColCol_0// "><COLGROUP><COL><COL width=3><COL width"...
0x2062d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20632  ldarg.1
0x20633  ldstr    aTdStylePadding_0// "<TD style='padding-right:6px;'>"
0x20638  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2063d  ldarg.1
0x2063e  ldstr    aInputTabindex// "<INPUT tabindex=\""
0x20643  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20648  ldarg.1
0x20649  ldarg.0
0x2064a  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x2064f  stloc.s  4
0x20651  ldloca.s 4
0x20653  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20658  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2065d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20662  ldarg.1
0x20663  ldstr    asc_32802// "\""
0x20668  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2066d  ldarg.0
0x2066e  call     instance string Microsoft.Crm.Application.Components.UI.MultiPicklist::get_TitleId()
0x20673  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20678  brtrue.s loc_20695
0x2067a  ldstr    aTitle_2// "title"
0x2067f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x20684  ldarg.0
0x20685  call     instance string Microsoft.Crm.Application.Components.UI.MultiPicklist::get_TitleId()
0x2068a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2068f  ldarg.1
0x20690  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20695  ldstr    aId// "id"
0x2069a  ldloc.1
0x2069b  ldarg.1
0x2069c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x206a1  ldstr    aData_1// "Data"
0x206a6  ldarg.0
0x206a7  ldfld    string Microsoft.Crm.Application.Components.UI.MultiPicklist::_value
0x206ac  ldarg.1
0x206ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x206b2  ldstr    aType// "type"
0x206b7  ldstr    aText// "text"
0x206bc  ldarg.1
0x206bd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x206c2  ldarg.0
0x206c3  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x206c8  brfalse.s loc_206D5
0x206ca  ldarg.1
0x206cb  ldstr    aDisabled_0// " disabled"
0x206d0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x206d5  ldarg.1
0x206d6  ldstr    aReadonlyTdTdTd// " readonly></TD><TD></TD><TD><BUTTON "
0x206db  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x206e0  ldstr    aTitle_2// "title"
0x206e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x206ea  ldstr    aMultiSelectPic// "Multi_Select_Picklist_Tooltip"
0x206ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x206f4  ldarg.1
0x206f5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x206fa  ldstr    aType// "type"
0x206ff  ldstr    aButton_0// "button"
0x20704  ldarg.1
0x20705  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2070a  ldstr    aId// "id"
0x2070f  ldloc.2
0x20710  ldarg.1
0x20711  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20716  ldarg.0
0x20717  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x2071c  brfalse.s loc_20729
0x2071e  ldarg.1
0x2071f  ldstr    aDisabled_0// " disabled"
0x20724  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20729  ldarg.1
0x2072a  ldstr    aTabindex1Style// " tabindex=-1 style=\"WIDTH:25px\">...</"...
0x2072f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x20734  ret
```
