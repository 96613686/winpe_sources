# Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillValidationDetails

- ea: `0x8cdb0`
- end: `0x8d3c6`
- name: `Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillValidationDetails`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x8c7d0`

## callees

- `0x6700`
- `0x6720`
- `0x11760`
- `0x2fb90`
- `0x2fbc0`
- `0x30260`
- `0x3a980`
- `0x3aa00`
- `0x65c90`
- `0x8cdb0`
- `0x8d520`
- `0x8d540`
- `0x8d580`

## string_xrefs

- `0x8d169`: `IW_ExportTemplate_MultiLookup`
- `0x8d17a`: `IW_ExportTemplate_LookupValue`
- `0x8d18b`: `IW_ExportTemplate_LookupValue_LongLookup`

## pseudocode

```c

```

## disassembly

```asm
0x8cdb0  ldarg.1
0x8cdb1  ldstr    aDisplayname_0// "DisplayName"
0x8cdb6  ldarg.s  4
0x8cdb8  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_DisplayName()
0x8cdbd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8cdc2  ldarg.1
0x8cdc3  ldstr    aDisplaynametru// "DisplayNameTruncated"
0x8cdc8  ldarg.s  4
0x8cdca  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_DisplayName()
0x8cdcf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8cdd4  ldc.i4.s 0x20
0x8cdd6  bgt.s    loc_8CDE1
0x8cdd8  ldarg.s  4
0x8cdda  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_DisplayName()
0x8cddf  br.s     loc_8CDF0
0x8cde1  ldarg.s  4
0x8cde3  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_DisplayName()
0x8cde8  ldc.i4.0
0x8cde9  ldc.i4.s 0x20
0x8cdeb  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8cdf0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8cdf5  ldarg.s  4
0x8cdf7  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_Description()
0x8cdfc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8ce01  brtrue.s loc_8CE4E
0x8ce03  ldarg.1
0x8ce04  ldstr    aDescription_1// "Description"
0x8ce09  ldarg.s  4
0x8ce0b  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_Description()
0x8ce10  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8ce15  ldarg.1
0x8ce16  ldstr    aDescriptiontru// "DescriptionTruncated"
0x8ce1b  ldarg.s  4
0x8ce1d  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_Description()
0x8ce22  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8ce27  ldc.i4   0xFF
0x8ce2c  bgt.s    loc_8CE37
0x8ce2e  ldarg.s  4
0x8ce30  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_Description()
0x8ce35  br.s     loc_8CE49
0x8ce37  ldarg.s  4
0x8ce39  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_Description()
0x8ce3e  ldc.i4.0
0x8ce3f  ldc.i4   0xFF
0x8ce44  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8ce49  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8ce4e  ldarg.s  4
0x8ce50  callvirt instance bool Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_IsRequired()
0x8ce55  stloc.s  9
0x8ce57  ldarg.3
0x8ce58  brtrue.s loc_8CE5E
0x8ce5a  ldc.i4.s 9
0x8ce5c  starg.s  2
0x8ce5e  ldarg.2
0x8ce5f  switch   loc_8D143, loc_8CF15, loc_8CF15, loc_8CF15, loc_8CEAF, loc_8CFE6, loc_8D0EF, loc_8D0AD, loc_8D164, loc_8CE91
0x8ce8c  br       loc_8D2D0
0x8ce91  ldarg.0
0x8ce92  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::textFieldInputTitle
0x8ce97  stloc.0
0x8ce98  ldstr    a10// "&#10;"
0x8ce9d  stloc.1
0x8ce9e  ldsfld   string [mscorlib]System.String::Empty
0x8cea3  stloc.2
0x8cea4  ldsfld   string [mscorlib]System.String::Empty
0x8cea9  stloc.3
0x8ceaa  br       loc_8D2E8
0x8ceaf  ldarg.3
0x8ceb0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata
0x8ceb5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x8ceba  stloc.s  0x10
0x8cebc  ldloca.s 0x10
0x8cebe  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8cec3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8cec8  stloc.s  0xA
0x8ceca  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8cecf  ldarg.0
0x8ced0  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxLengthInputMessageFormat
0x8ced5  ldc.i4.1
0x8ced6  newarr   [mscorlib]System.Object
0x8cedb  dup
0x8cedc  ldc.i4.0
0x8cedd  ldloc.s  0xA
0x8cedf  stelem.ref
0x8cee0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8cee5  ldarg.0
0x8cee6  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::textFieldInputTitle
0x8ceeb  stloc.0
0x8ceec  stloc.1
0x8ceed  ldarg.0
0x8ceee  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::textFieldErrorTitle
0x8cef3  stloc.2
0x8cef4  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8cef9  ldarg.0
0x8cefa  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxLengthErrorMessageFormat
0x8ceff  ldc.i4.1
0x8cf00  newarr   [mscorlib]System.Object
0x8cf05  dup
0x8cf06  ldc.i4.0
0x8cf07  ldloc.s  0xA
0x8cf09  stelem.ref
0x8cf0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8cf0f  stloc.3
0x8cf10  br       loc_8D2E8
0x8cf15  ldarg.3
0x8cf16  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata
0x8cf1b  dup
0x8cf1c  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MinValue()
0x8cf21  stloc.s  0x11
0x8cf23  ldloca.s 0x11
0x8cf25  ldstr    aF// "F"
0x8cf2a  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8cf2f  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x8cf34  stloc.s  4
0x8cf36  callvirt instance float64 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_MaxValue()
0x8cf3b  stloc.s  0x11
0x8cf3d  ldloca.s 0x11
0x8cf3f  ldstr    aF// "F"
0x8cf44  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8cf49  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x8cf4e  stloc.s  5
0x8cf50  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8cf55  ldarg.0
0x8cf56  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::minValueInputMessageFormat
0x8cf5b  ldc.i4.1
0x8cf5c  newarr   [mscorlib]System.Object
0x8cf61  dup
0x8cf62  ldc.i4.0
0x8cf63  ldloc.s  4
0x8cf65  stelem.ref
0x8cf66  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8cf6b  stloc.s  6
0x8cf6d  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8cf72  ldarg.0
0x8cf73  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxValueInputMessageFormat
0x8cf78  ldc.i4.1
0x8cf79  newarr   [mscorlib]System.Object
0x8cf7e  dup
0x8cf7f  ldc.i4.0
0x8cf80  ldloc.s  5
0x8cf82  stelem.ref
0x8cf83  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8cf88  stloc.s  7
0x8cf8a  ldarg.0
0x8cf8b  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::decimalFieldInputTitle
0x8cf90  stloc.0
0x8cf91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8cf96  ldstr    a012_5// "{0}{1}{2}"
0x8cf9b  ldc.i4.3
0x8cf9c  newarr   [mscorlib]System.Object
0x8cfa1  dup
0x8cfa2  ldc.i4.0
0x8cfa3  ldloc.s  6
0x8cfa5  stelem.ref
0x8cfa6  dup
0x8cfa7  ldc.i4.1
0x8cfa8  ldstr    a10// "&#10;"
0x8cfad  stelem.ref
0x8cfae  dup
0x8cfaf  ldc.i4.2
0x8cfb0  ldloc.s  7
0x8cfb2  stelem.ref
0x8cfb3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8cfb8  stloc.1
0x8cfb9  ldarg.0
0x8cfba  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::decimalFieldErrorTitle
0x8cfbf  stloc.2
0x8cfc0  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8cfc5  ldarg.0
0x8cfc6  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::decimalFieldErrorMessageFormat
0x8cfcb  ldc.i4.2
0x8cfcc  newarr   [mscorlib]System.Object
0x8cfd1  dup
0x8cfd2  ldc.i4.0
0x8cfd3  ldloc.s  4
0x8cfd5  stelem.ref
0x8cfd6  dup
0x8cfd7  ldc.i4.1
0x8cfd8  ldloc.s  5
0x8cfda  stelem.ref
0x8cfdb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8cfe0  stloc.3
0x8cfe1  br       loc_8D2E8
0x8cfe6  ldarg.3
0x8cfe7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata
0x8cfec  dup
0x8cfed  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MinValue()
0x8cff2  stloc.s  0x10
0x8cff4  ldloca.s 0x10
0x8cff6  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8cffb  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8d000  stloc.s  4
0x8d002  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata::get_MaxValue()
0x8d007  stloc.s  0x10
0x8d009  ldloca.s 0x10
0x8d00b  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8d010  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8d015  stloc.s  5
0x8d017  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8d01c  ldarg.0
0x8d01d  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::minValueInputMessageFormat
0x8d022  ldc.i4.1
0x8d023  newarr   [mscorlib]System.Object
0x8d028  dup
0x8d029  ldc.i4.0
0x8d02a  ldloc.s  4
0x8d02c  stelem.ref
0x8d02d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d032  stloc.s  6
0x8d034  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8d039  ldarg.0
0x8d03a  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxValueInputMessageFormat
0x8d03f  ldc.i4.1
0x8d040  newarr   [mscorlib]System.Object
0x8d045  dup
0x8d046  ldc.i4.0
0x8d047  ldloc.s  5
0x8d049  stelem.ref
0x8d04a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d04f  stloc.s  7
0x8d051  ldarg.0
0x8d052  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::integerFieldInputTitle
0x8d057  stloc.0
0x8d058  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d05d  ldstr    a012_5// "{0}{1}{2}"
0x8d062  ldc.i4.3
0x8d063  newarr   [mscorlib]System.Object
0x8d068  dup
0x8d069  ldc.i4.0
0x8d06a  ldloc.s  6
0x8d06c  stelem.ref
0x8d06d  dup
0x8d06e  ldc.i4.1
0x8d06f  ldstr    a10// "&#10;"
0x8d074  stelem.ref
0x8d075  dup
0x8d076  ldc.i4.2
0x8d077  ldloc.s  7
0x8d079  stelem.ref
0x8d07a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d07f  stloc.1
0x8d080  ldarg.0
0x8d081  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::integerFieldErrorTitle
0x8d086  stloc.2
0x8d087  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8d08c  ldarg.0
0x8d08d  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::integerFieldErrorMessageFormat
0x8d092  ldc.i4.2
0x8d093  newarr   [mscorlib]System.Object
0x8d098  dup
0x8d099  ldc.i4.0
0x8d09a  ldloc.s  4
0x8d09c  stelem.ref
0x8d09d  dup
0x8d09e  ldc.i4.1
0x8d09f  ldloc.s  5
0x8d0a1  stelem.ref
0x8d0a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d0a7  stloc.3
0x8d0a8  br       loc_8D2E8
0x8d0ad  ldarg.0
0x8d0ae  ldfld    class Microsoft.Crm.ExcelNumberFormats Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::excelFormats
0x8d0b3  callvirt instance string Microsoft.Crm.ExcelNumberFormats::GetDateFormat()
0x8d0b8  stloc.s  8
0x8d0ba  ldarg.0
0x8d0bb  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateFieldInputTitle
0x8d0c0  stloc.0
0x8d0c1  ldstr    a10// "&#10;"
0x8d0c6  stloc.1
0x8d0c7  ldarg.0
0x8d0c8  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateFieldErrorTitle
0x8d0cd  stloc.2
0x8d0ce  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8d0d3  ldarg.0
0x8d0d4  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateFieldErrorMessageFormat
0x8d0d9  ldc.i4.1
0x8d0da  newarr   [mscorlib]System.Object
0x8d0df  dup
0x8d0e0  ldc.i4.0
0x8d0e1  ldloc.s  8
0x8d0e3  stelem.ref
0x8d0e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d0e9  stloc.3
0x8d0ea  br       loc_8D2E8
0x8d0ef  ldarg.0
0x8d0f0  ldfld    class Microsoft.Crm.ExcelNumberFormats Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::excelFormats
0x8d0f5  callvirt instance string Microsoft.Crm.ExcelNumberFormats::GetDateFormat()
0x8d0fa  stloc.s  8
0x8d0fc  ldarg.0
0x8d0fd  ldfld    class Microsoft.Crm.ExcelNumberFormats Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::excelFormats
0x8d102  callvirt instance string Microsoft.Crm.ExcelNumberFormats::GetTimeFormat()
0x8d107  stloc.s  0xB
0x8d109  ldarg.0
0x8d10a  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateTimeFieldInputTitle
0x8d10f  stloc.0
0x8d110  ldstr    a10// "&#10;"
0x8d115  stloc.1
0x8d116  ldarg.0
0x8d117  ldfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateTimeFieldErrorTitle
0x8d11c  stloc.2
0x8d11d  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
  ... truncated ...
```
