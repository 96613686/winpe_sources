# Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderMocaControlOpen

- ea: `0x16b50`
- end: `0x16d38`
- name: `Microsoft.Crm.Application.Components.UI.MocaDateTimeUI::RenderMocaControlOpen`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x16b30`

## callees

- `0x167a0`
- `0x167f0`
- `0x168d0`
- `0x168f0`
- `0x16910`
- `0x16950`
- `0x16970`
- `0x16b50`
- `0x23c20`
- `0x24120`
- `0x24280`

## string_xrefs

- `0x16c44`: `cacheValuesOnClient`

## pseudocode

```c

```

## disassembly

```asm
0x16b50  ldarg.1
0x16b51  ldstr    aDivClassTouchd// "<div class=\"touchDateTimeControl\""
0x16b56  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16b5b  ldarg.1
0x16b5c  ldstr    aTabindex_0// "tabIndex"
0x16b61  ldstr    a0// "0"
0x16b66  ldc.i4.0
0x16b67  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16b6c  ldstr    aId// "id"
0x16b71  ldarg.0
0x16b72  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x16b77  ldarg.1
0x16b78  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16b7d  ldstr    aFormat// "format"
0x16b82  ldarg.0
0x16b83  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x16b88  ldarg.1
0x16b89  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16b8e  ldarg.1
0x16b8f  ldstr    aInitialshowtim// "initialShowTime"
0x16b94  ldarg.0
0x16b95  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_ShowTime()
0x16b9a  stloc.0
0x16b9b  ldloca.s 0
0x16b9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16ba2  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16ba7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16bac  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16bb1  ldc.i4.0
0x16bb2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16bb7  ldarg.1
0x16bb8  ldstr    aInitialallowbl// "initialAllowBlankDate"
0x16bbd  ldarg.0
0x16bbe  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_AllowBlankDate()
0x16bc3  stloc.0
0x16bc4  ldloca.s 0
0x16bc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16bcb  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16bd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16bd5  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16bda  ldc.i4.0
0x16bdb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16be0  ldarg.1
0x16be1  ldstr    aInitialdisable// "initialDisableInit"
0x16be6  ldarg.0
0x16be7  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisableInit()
0x16bec  stloc.0
0x16bed  ldloca.s 0
0x16bef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16bf4  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16bf9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16bfe  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16c03  ldc.i4.0
0x16c04  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16c09  ldarg.1
0x16c0a  ldstr    aInitialalldayd// "initialAllDayDisplayMode"
0x16c0f  ldarg.0
0x16c10  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_AllDayDisplayMode()
0x16c15  stloc.0
0x16c16  ldloca.s 0
0x16c18  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16c1d  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16c22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16c27  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16c2c  ldc.i4.0
0x16c2d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16c32  ldarg.1
0x16c33  ldstr    aInitialallowti// "initialAllowTimeEdit"
0x16c38  ldstr    aTrue// "true"
0x16c3d  ldc.i4.0
0x16c3e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16c43  ldarg.1
0x16c44  ldstr    aCachevaluesonc// "cacheValuesOnClient"
0x16c49  ldarg.0
0x16c4a  call     instance bool Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_CacheValuesOnClient()
0x16c4f  stloc.0
0x16c50  ldloca.s 0
0x16c52  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16c57  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x16c5c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16c61  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x16c66  ldc.i4.0
0x16c67  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x16c6c  ldstr    aShortdatepatte// "shortDatePattern"
0x16c71  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x16c76  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x16c7b  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x16c80  ldarg.1
0x16c81  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16c86  ldstr    aShorttimepatte// "shortTimePattern"
0x16c8b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x16c90  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x16c95  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortTimePattern()
0x16c9a  ldarg.1
0x16c9b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16ca0  ldarg.0
0x16ca1  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x16ca6  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x16cab  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x16cb0  brtrue.s loc_16CC4
0x16cb2  ldarg.0
0x16cb3  call     instance string Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_DisplayFormat()
0x16cb8  ldstr    aTime// "time"
0x16cbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16cc2  brfalse.s loc_16CE7
0x16cc4  ldstr    aInitialvalue// "initialValue"
0x16cc9  ldarg.0
0x16cca  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Components.UI.DateTimeUIBase::get_Value()
0x16ccf  stloc.1
0x16cd0  ldloca.s 1
0x16cd2  ldstr    aS// "s"
0x16cd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16cdc  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x16ce1  ldarg.1
0x16ce2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x16ce7  ldarg.0
0x16ce8  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x16ced  brtrue.s loc_16CF7
0x16cef  ldarg.0
0x16cf0  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x16cf5  brfalse.s loc_16D02
0x16cf7  ldarg.1
0x16cf8  ldstr    aContenteditabl// " contenteditable=\"false\" disabled=\"t"...
0x16cfd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16d02  ldarg.1
0x16d03  ldarg.0
0x16d04  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x16d09  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16d0e  ldarg.1
0x16d0f  ldc.i4.s 0x3E
0x16d11  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x16d16  ldarg.1
0x16d17  ldstr    aDivClassDateti// "<div class=\"dateTimeControlHeader\">"
0x16d1c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16d21  ldarg.1
0x16d22  ldstr    aSpanClassContr// "<span class=\"controlValue\"></span>"
0x16d27  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16d2c  ldarg.1
0x16d2d  ldstr    aDiv// "</div>"
0x16d32  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16d37  ret
```
