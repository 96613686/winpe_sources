# Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderTableOpen

- ea: `0x160c0`
- end: `0x16254`
- name: `Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderTableOpen`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x15ff0`

## callees

- `0x16060`
- `0x160c0`
- `0x167a0`
- `0x167f0`
- `0x168d0`
- `0x168f0`
- `0x16910`
- `0x16950`
- `0x16970`
- `0x23c20`
- `0x24120`
- `0x24280`

## string_xrefs

- `0x161a3`: `cacheValuesOnClient`

## pseudocode

```c

```

## disassembly

```asm
0x160c0  ldarg.1
0x160c1  ldstr    aTableCellpaddi// "<table cellpadding=\"0\" cellspacing=\""...
0x160c6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x160cb  ldstr    aId// "id"
0x160d0  ldarg.0
0x160d1  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x160d6  ldarg.1
0x160d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x160dc  ldstr    aFormat// "format"
0x160e1  ldarg.0
0x160e2  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x160e7  ldarg.1
0x160e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x160ed  ldarg.1
0x160ee  ldstr    aInitialshowtim// "initialShowTime"
0x160f3  ldarg.0
0x160f4  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_ShowTime()
0x160f9  stloc.0
0x160fa  ldloca.s 0
0x160fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16101  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16106  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1610b  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16110  ldc.i4.0
0x16111  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16116  ldarg.1
0x16117  ldstr    aInitialallowbl// "initialAllowBlankDate"
0x1611c  ldarg.0
0x1611d  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_AllowBlankDate()
0x16122  stloc.0
0x16123  ldloca.s 0
0x16125  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1612a  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x1612f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16134  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16139  ldc.i4.0
0x1613a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1613f  ldarg.1
0x16140  ldstr    aInitialdisable// "initialDisableInit"
0x16145  ldarg.0
0x16146  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisableInit()
0x1614b  stloc.0
0x1614c  ldloca.s 0
0x1614e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16153  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16158  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1615d  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16162  ldc.i4.0
0x16163  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16168  ldarg.1
0x16169  ldstr    aInitialalldayd// "initialAllDayDisplayMode"
0x1616e  ldarg.0
0x1616f  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_AllDayDisplayMode()
0x16174  stloc.0
0x16175  ldloca.s 0
0x16177  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1617c  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16181  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16186  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x1618b  ldc.i4.0
0x1618c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16191  ldarg.1
0x16192  ldstr    aInitialallowti// "initialAllowTimeEdit"
0x16197  ldstr    aTrue// "true"
0x1619c  ldc.i4.0
0x1619d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x161a2  ldarg.1
0x161a3  ldstr    aCachevaluesonc// "cacheValuesOnClient"
0x161a8  ldarg.0
0x161a9  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_CacheValuesOnClient()
0x161ae  stloc.0
0x161af  ldloca.s 0
0x161b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x161b6  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x161bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x161c0  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x161c5  ldc.i4.0
0x161c6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x161cb  ldarg.0
0x161cc  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x161d1  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x161d6  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x161db  brtrue.s loc_161EF
0x161dd  ldarg.0
0x161de  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x161e3  ldstr    aTime// "time"
0x161e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x161ed  brfalse.s loc_16212
0x161ef  ldstr    aInitialvalue// "initialValue"
0x161f4  ldarg.0
0x161f5  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x161fa  stloc.1
0x161fb  ldloca.s 1
0x161fd  ldstr    aS// "s"
0x16202  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16207  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x1620c  ldarg.1
0x1620d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16212  ldarg.0
0x16213  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x16218  brtrue.s loc_16222
0x1621a  ldarg.0
0x1621b  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x16220  brfalse.s loc_1622D
0x16222  ldarg.1
0x16223  ldstr    aContenteditabl// " contenteditable=\"false\" disabled=\"t"...
0x16228  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1622d  ldarg.1
0x1622e  ldarg.0
0x1622f  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x16234  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16239  ldarg.1
0x1623a  ldc.i4.s 0x3E
0x1623c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x16241  ldarg.0
0x16242  ldarg.1
0x16243  call     instance void Microsoft.Crm.Application.Components.UI.DateTimeUI::RenderTableColumns(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x16248  ldarg.1
0x16249  ldstr    aTr_1// "<tr>"
0x1624e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16253  ret
```
