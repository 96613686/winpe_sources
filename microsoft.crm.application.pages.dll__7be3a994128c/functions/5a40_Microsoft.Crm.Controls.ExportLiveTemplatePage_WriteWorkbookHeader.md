# Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteWorkbookHeader

- ea: `0x5a40`
- end: `0x5cc3`
- name: `Microsoft.Crm.Controls.ExportLiveTemplatePage::WriteWorkbookHeader`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5400`

## callees

- `0x5a40`

## string_xrefs

- `0x5a41`: `<?xml version="1.0" ?>\n				<?mso-application progid="Excel.Sheet"?>`
- `0x5a4c`: `<Workbook xmlns="urn:schemas-microsoft-com:office:spreadsheet" xmlns:o="urn:schemas-microsoft-com:office:office"\n					xmlns:x="urn:schemas-microsoft-com:office:excel" xmlns:dt="uuid:C2F41010-65B3-11d1-A29F-00AA00C14882"\n					xmlns:ss="urn:schemas-microsoft-com:office:spreadsheet" xmlns:html="http://www.w3.org/TR/REC-html40">\n					<DocumentProperties xmlns="urn:schemas-microsoft-com:office:office">`
- `0x5a78`: `Created`
- `0x5ac6`: `<CustomDocumentProperties xmlns="urn:schemas-microsoft-com:office:office">\n					<MSCRMCreatePivot dt:dt="float">`
- `0x5ae6`: `</MSCRMCreatePivot>\n				</CustomDocumentProperties>`
- `0x5af1`: `<ExcelWorkbook xmlns="urn:schemas-microsoft-com:office:excel">\n						<WindowHeight>9090</WindowHeight>\n						<WindowWidth>13260</WindowWidth>\n						<WindowTopX>480</WindowTopX>\n						<WindowTopY>45</WindowTopY>\n						<ProtectStructure>False</ProtectStructure>\n						<ProtectWindows>False</ProtectWindows>\n					</ExcelWorkbook>\n					<Styles>\n						<Style ss:ID="Default" ss:Name="Normal">\n							<Alignment ss:Vertical="Bottom" `
- `0x5b0d`: `ss:Horizontal="Right" ss:ReadingOrder="RightToLeft" `

## pseudocode

```c

```

## disassembly

```asm
0x5a40  ldarg.1
0x5a41  ldstr    aXmlVersion10Ms// "<?xml version=\"1.0\" ?>\r\n\t\t\t\t<?m"...
0x5a46  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5a4b  ldarg.1
0x5a4c  ldstr    aWorkbookXmlnsU// "<Workbook xmlns=\"urn:schemas-microsoft"...
0x5a51  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5a56  ldarg.1
0x5a57  ldstr    aAuthor// "Author"
0x5a5c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x5a61  ldarg.1
0x5a62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x5a67  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x5a6c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x5a71  ldarg.1
0x5a72  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5a77  ldarg.1
0x5a78  ldstr    aCreated// "Created"
0x5a7d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x5a82  ldarg.1
0x5a83  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x5a88  stloc.2
0x5a89  ldloca.s 2
0x5a8b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x5a90  stloc.2
0x5a91  ldloca.s 2
0x5a93  ldstr    aS// "s"
0x5a98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a9d  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x5aa2  ldstr    aZ// "Z"
0x5aa7  call     string [mscorlib]System.String::Concat(string, string)
0x5aac  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x5ab1  ldarg.1
0x5ab2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5ab7  ldarg.1
0x5ab8  ldstr    aVersion118132V// "<Version>11.8132</Version>\r\n\t\t\t\t"...
0x5abd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5ac2  ldarg.3
0x5ac3  brtrue.s loc_5AF0
0x5ac5  ldarg.1
0x5ac6  ldstr    aCustomdocument// "<CustomDocumentProperties xmlns=\"urn:s"...
0x5acb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5ad0  ldarg.1
0x5ad1  ldarg.2
0x5ad2  brtrue.s loc_5ADB
0x5ad4  ldstr    a0_1// "0"
0x5ad9  br.s     loc_5AE0
0x5adb  ldstr    a1// "1"
0x5ae0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5ae5  ldarg.1
0x5ae6  ldstr    aMscrmcreatepiv// "</MSCRMCreatePivot>\r\n\t\t\t\t</Custom"...
0x5aeb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5af0  ldarg.1
0x5af1  ldstr    aExcelworkbookX// "<ExcelWorkbook xmlns=\"urn:schemas-micr"...
0x5af6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5afb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x5b00  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x5b05  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x5b0a  brfalse.s loc_5B17
0x5b0c  ldarg.1
0x5b0d  ldstr    aSsHorizontalRi// "ss:Horizontal=\"Right\" ss:ReadingOrder"...
0x5b12  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5b17  ldarg.1
0x5b18  ldstr    aBordersFontInt// "/>\r\n\t\t\t\t\t\t\t<Borders />\r\n\t\t"...
0x5b1d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5b22  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5b27  ldc.i4.1
0x5b28  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ExcelNumberFormats::.ctor(class [mscorlib]System.Globalization.CultureInfo, bool)
0x5b2d  stloc.0
0x5b2e  ldarg.0
0x5b2f  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5b34  ldstr    aS23// "s23"
0x5b39  ldloc.0
0x5b3a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ExcelNumberFormats::GetDateTimeFormat()
0x5b3f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5b44  ldarg.0
0x5b45  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5b4a  ldstr    aS24// "s24"
0x5b4f  ldloc.0
0x5b50  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ExcelNumberFormats::GetDateFormat()
0x5b55  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5b5a  ldarg.1
0x5b5b  ldc.i4.5
0x5b5c  newarr   [mscorlib]System.String
0x5b61  dup
0x5b62  ldc.i4.0
0x5b63  ldstr    aStyleSsIdS21Fo// "<Style ss:ID='s21'>\r\n\t\t\t\t\t\t\t<F"...
0x5b68  stelem.ref
0x5b69  dup
0x5b6a  ldc.i4.1
0x5b6b  ldarg.0
0x5b6c  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5b71  ldstr    aS23// "s23"
0x5b76  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x5b7b  stelem.ref
0x5b7c  dup
0x5b7d  ldc.i4.2
0x5b7e  ldstr    aStyleStyleSsId// "'/>\r\n\t\t\t\t\t\t</Style>\r\n\t\t\t\t"...
0x5b83  stelem.ref
0x5b84  dup
0x5b85  ldc.i4.3
0x5b86  ldarg.0
0x5b87  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5b8c  ldstr    aS24// "s24"
0x5b91  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x5b96  stelem.ref
0x5b97  dup
0x5b98  ldc.i4.4
0x5b99  ldstr    aStyle// "'/>\r\n\t\t\t\t\t\t</Style>"
0x5b9e  stelem.ref
0x5b9f  call     string [mscorlib]System.String::Concat(string[])
0x5ba4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5ba9  ldc.i4.0
0x5baa  stloc.3
0x5bab  br.s     loc_5C23
0x5bad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5bb2  ldstr    aS30// "s3{0}"
0x5bb7  ldc.i4.1
0x5bb8  newarr   [mscorlib]System.Object
0x5bbd  dup
0x5bbe  ldc.i4.0
0x5bbf  ldloc.3
0x5bc0  box      [mscorlib]System.Int32
0x5bc5  stelem.ref
0x5bc6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5bcb  stloc.s  4
0x5bcd  ldarg.0
0x5bce  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5bd3  ldloc.s  4
0x5bd5  ldloc.0
0x5bd6  ldloc.3
0x5bd7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ExcelNumberFormats::GetNumberFormat(int32)
0x5bdc  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5be1  ldarg.1
0x5be2  ldc.i4.5
0x5be3  newarr   [mscorlib]System.String
0x5be8  dup
0x5be9  ldc.i4.0
0x5bea  ldstr    aStyleSsId// "<Style ss:ID='"
0x5bef  stelem.ref
0x5bf0  dup
0x5bf1  ldc.i4.1
0x5bf2  ldloc.s  4
0x5bf4  stelem.ref
0x5bf5  dup
0x5bf6  ldc.i4.2
0x5bf7  ldstr    aFontXFamilySwi// "'>\r\n\t\t\t\t\t\t\t<Font x:Family='Swi"...
0x5bfc  stelem.ref
0x5bfd  dup
0x5bfe  ldc.i4.3
0x5bff  ldarg.0
0x5c00  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5c05  ldloc.s  4
0x5c07  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x5c0c  stelem.ref
0x5c0d  dup
0x5c0e  ldc.i4.4
0x5c0f  ldstr    aStyle// "'/>\r\n\t\t\t\t\t\t</Style>"
0x5c14  stelem.ref
0x5c15  call     string [mscorlib]System.String::Concat(string[])
0x5c1a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5c1f  ldloc.3
0x5c20  ldc.i4.1
0x5c21  add
0x5c22  stloc.3
0x5c23  ldloc.3
0x5c24  ldc.i4.5
0x5c25  ble.s    loc_5BAD
0x5c27  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5c2c  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::GetBaseCurrencySymbol(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c31  stloc.1
0x5c32  ldc.i4.0
0x5c33  stloc.s  5
0x5c35  br.s     loc_5CB2
0x5c37  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c3c  ldstr    aS40// "s4{0}"
0x5c41  ldc.i4.1
0x5c42  newarr   [mscorlib]System.Object
0x5c47  dup
0x5c48  ldc.i4.0
0x5c49  ldloc.s  5
0x5c4b  box      [mscorlib]System.Int32
0x5c50  stelem.ref
0x5c51  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5c56  stloc.s  6
0x5c58  ldarg.0
0x5c59  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5c5e  ldloc.s  6
0x5c60  ldloc.0
0x5c61  ldloc.1
0x5c62  ldloc.s  5
0x5c64  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ExcelNumberFormats::GetCurrencyFormat(string, int32)
0x5c69  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x5c6e  ldarg.1
0x5c6f  ldc.i4.5
0x5c70  newarr   [mscorlib]System.String
0x5c75  dup
0x5c76  ldc.i4.0
0x5c77  ldstr    aStyleSsId// "<Style ss:ID='"
0x5c7c  stelem.ref
0x5c7d  dup
0x5c7e  ldc.i4.1
0x5c7f  ldloc.s  6
0x5c81  stelem.ref
0x5c82  dup
0x5c83  ldc.i4.2
0x5c84  ldstr    aFontXFamilySwi// "'>\r\n\t\t\t\t\t\t\t<Font x:Family='Swi"...
0x5c89  stelem.ref
0x5c8a  dup
0x5c8b  ldc.i4.3
0x5c8c  ldarg.0
0x5c8d  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Controls.ExportLiveTemplatePage::_excelNumberFormats
0x5c92  ldloc.s  6
0x5c94  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x5c99  stelem.ref
0x5c9a  dup
0x5c9b  ldc.i4.4
0x5c9c  ldstr    aStyle// "'/>\r\n\t\t\t\t\t\t</Style>"
0x5ca1  stelem.ref
0x5ca2  call     string [mscorlib]System.String::Concat(string[])
0x5ca7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5cac  ldloc.s  5
0x5cae  ldc.i4.1
0x5caf  add
0x5cb0  stloc.s  5
0x5cb2  ldloc.s  5
0x5cb4  ldc.i4.5
0x5cb5  ble.s    loc_5C37
0x5cb7  ldarg.1
0x5cb8  ldstr    aStyles// "</Styles>"
0x5cbd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x5cc2  ret
```
