# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::RenderDocumentHeader

- ea: `0xd6c90`
- end: `0xd7030`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::RenderDocumentHeader`
- size: `928`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd5f70`
- `0xd6050`

## callees

- `0xd6c90`
- `0xd7040`

## string_xrefs

- `0xd6c91`: `<html xmlns:v="urn:schemas-microsoft-com:vml" xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:x="urn:schemas-microsoft-com:office:excel" xmlns="http://www.w3.org/TR/REC-html40"`
- `0xd6ea4`: `<!--[if gte mso 9]><xml>\n			 <o:DocumentProperties>\n			  <o:Author>`
- `0xd6f40`: `</o:MSCRMVersion>\n			 </o:CustomDocumentProperties>\n			</xml><![endif]-->`
- `0xd6f5c`: `<xml>`
- `0xd6ffe`: `</xml>`

## pseudocode

```c

```

## disassembly

```asm
0xd6c90  ldarg.1
0xd6c91  ldstr    aHtmlXmlnsVUrnS// "<html xmlns:v=\"urn:schemas-microsoft-c"...
0xd6c96  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6c9b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd6ca0  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xd6ca5  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xd6caa  brfalse.s loc_D6CB7
0xd6cac  ldarg.1
0xd6cad  ldstr    aDirRtl// " dir=RTL"
0xd6cb2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6cb7  ldarg.1
0xd6cb8  ldstr    asc_111CB6// ">"
0xd6cbd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6cc2  ldarg.1
0xd6cc3  ldstr    aHead_1// "<head>"
0xd6cc8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6ccd  ldarg.1
0xd6cce  ldstr    aMetaHttpEquivC// "<meta http-equiv=Content-Type content="...
0xd6cd3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6cd8  ldarg.1
0xd6cd9  ldstr    aMetaNameProgid// "<meta name=ProgId content=Excel.Sheet>"
0xd6cde  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6ce3  ldarg.1
0xd6ce4  ldstr    aStyleTypeTextC_1// "<style type=\"text/css\">\r\n\t\t\t\t<!"...
0xd6ce9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6cee  ldarg.1
0xd6cef  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd6cf4  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xd6cf9  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xd6cfe  brtrue.s loc_D6D07
0xd6d00  ldstr    aGeneral// "general"
0xd6d05  br.s     loc_D6D0C
0xd6d07  ldstr    aRight// "right"
0xd6d0c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6d11  ldarg.1
0xd6d12  ldc.i4.s 0x11
0xd6d14  newarr   [mscorlib]System.String
0xd6d19  dup
0xd6d1a  ldc.i4.0
0xd6d1b  ldstr    aVerticalAlignB_2// ";\r\n\t\t\t\t\tvertical-align:bottom;\r"...
0xd6d20  stelem.ref
0xd6d21  dup
0xd6d22  ldc.i4.1
0xd6d23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6d28  ldstr    aAppgridexportu// "AppGridExportUIProvider.cs.Render.style"...
0xd6d2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6d32  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6d37  stelem.ref
0xd6d38  dup
0xd6d39  ldc.i4.2
0xd6d3a  ldstr    aFontWeight// ";\r\n\t\t\t\t\tfont-weight:"
0xd6d3f  stelem.ref
0xd6d40  dup
0xd6d41  ldc.i4.3
0xd6d42  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6d47  ldstr    aAppgridexportu_0// "AppGridExportUIProvider.cs.Render.style"...
0xd6d4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6d51  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6d56  stelem.ref
0xd6d57  dup
0xd6d58  ldc.i4.4
0xd6d59  ldstr    aFontStyleNorma// ";\r\n\t\t\t\t\tfont-style:normal;\r\n\t"...
0xd6d5e  stelem.ref
0xd6d5f  dup
0xd6d60  ldc.i4.5
0xd6d61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6d66  ldstr    aAppgridexportu_1// "AppGridExportUIProvider.cs.Render.style"...
0xd6d6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6d70  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6d75  stelem.ref
0xd6d76  dup
0xd6d77  ldc.i4.6
0xd6d78  ldstr    aMsoGenericFont// ";\r\n\t\t\t\t\tmso-generic-font-family:"...
0xd6d7d  stelem.ref
0xd6d7e  dup
0xd6d7f  ldc.i4.7
0xd6d80  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6d85  ldstr    aAppgridexportu_2// "AppGridExportUIProvider.cs.Render.td.fo"...
0xd6d8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6d8f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6d94  stelem.ref
0xd6d95  dup
0xd6d96  ldc.i4.8
0xd6d97  ldstr    aFontWeight// ";\r\n\t\t\t\t\tfont-weight:"
0xd6d9c  stelem.ref
0xd6d9d  dup
0xd6d9e  ldc.i4.s 9
0xd6da0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6da5  ldstr    aAppgridexportu_3// "AppGridExportUIProvider.cs.Render.td.fo"...
0xd6daa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6daf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6db4  stelem.ref
0xd6db5  dup
0xd6db6  ldc.i4.s 0xA
0xd6db8  ldstr    aFontStyleNorma// ";\r\n\t\t\t\t\tfont-style:normal;\r\n\t"...
0xd6dbd  stelem.ref
0xd6dbe  dup
0xd6dbf  ldc.i4.s 0xB
0xd6dc1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6dc6  ldstr    aAppgridexportu_4// "AppGridExportUIProvider.cs.Render.td.fo"...
0xd6dcb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6dd0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6dd5  stelem.ref
0xd6dd6  dup
0xd6dd7  ldc.i4.s 0xC
0xd6dd9  ldstr    aMsoGenericFont_0// ";\r\n\t\t\t\t\tmso-generic-font-family:"...
0xd6dde  stelem.ref
0xd6ddf  dup
0xd6de0  ldc.i4.s 0xD
0xd6de2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6de7  ldstr    aAppgridexportu_5// "AppGridExportUIProvider.cs.Render.xl24."...
0xd6dec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6df1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6df6  stelem.ref
0xd6df7  dup
0xd6df8  ldc.i4.s 0xE
0xd6dfa  ldstr    aFontFamily// ";\r\n\t\t\t\t\tfont-family:"
0xd6dff  stelem.ref
0xd6e00  dup
0xd6e01  ldc.i4.s 0xF
0xd6e03  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6e08  ldstr    aAppgridexportu_6// "AppGridExportUIProvider.cs.Render.xl24."...
0xd6e0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6e12  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6e17  stelem.ref
0xd6e18  dup
0xd6e19  ldc.i4.s 0x10
0xd6e1b  ldstr    aMsoFontCharset// ";\r\n\t\t\t\t\tmso-font-charset:0;\r\n"...
0xd6e20  stelem.ref
0xd6e21  call     string [mscorlib]System.String::Concat(string[])
0xd6e26  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6e2b  ldarg.0
0xd6e2c  ldarg.1
0xd6e2d  call     instance void Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::RenderNumberFormats(class [mscorlib]System.IO.TextWriter writer)
0xd6e32  ldarg.1
0xd6e33  ldstr    aStyle_5// "\t-->\r\n\t\t\t\t</style>"
0xd6e38  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6e3d  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0xd6e42  stloc.0
0xd6e43  ldloc.0
0xd6e44  ldc.i4.1
0xd6e45  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0xd6e4a  ldarg.1
0xd6e4b  ldloc.0
0xd6e4c  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0xd6e51  stloc.1
0xd6e52  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0xd6e57  stloc.3
0xd6e58  ldloca.s 3
0xd6e5a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xd6e5f  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xd6e64  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_FullDateTimePattern()
0xd6e69  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xd6e6e  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xd6e73  stloc.2
0xd6e74  ldarg.1
0xd6e75  ldstr    aTitle_2// "<title>"
0xd6e7a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6e7f  ldstr    aExporttoexcelS// "ExportToExcel.Static.Title"
0xd6e84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6e89  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xd6e8e  ldstr    aTitle_3// "</title>"
0xd6e93  call     string [mscorlib]System.String::Concat(string, string, string)
0xd6e98  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6e9d  ldarg.1
0xd6e9e  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0xd6ea3  ldloc.1
0xd6ea4  ldstr    aIfGteMso9XmlOD// "<!--[if gte mso 9]><xml>\r\n\t\t\t <o:D"...
0xd6ea9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6eae  ldloc.1
0xd6eaf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xd6eb4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0xd6eb9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xd6ebe  ldloc.1
0xd6ebf  ldstr    aOAuthorOCatego// "</o:Author><o:Category>"
0xd6ec4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6ec9  ldloc.1
0xd6eca  ldarg.3
0xd6ecb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xd6ed0  ldloc.1
0xd6ed1  ldstr    aOCategoryODesc// "</o:Category><o:Description>"
0xd6ed6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6edb  ldloc.1
0xd6edc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd6ee1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6ee6  ldstr    aExporttoexcelS_0// "ExportToExcel.Static.Description"
0xd6eeb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6ef0  ldc.i4.1
0xd6ef1  newarr   [mscorlib]System.Object
0xd6ef6  dup
0xd6ef7  ldc.i4.0
0xd6ef8  ldloc.2
0xd6ef9  stelem.ref
0xd6efa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd6eff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xd6f04  ldloc.1
0xd6f05  ldstr    aODescriptionOD// "</o:Description>\r\n\t\t\t </o:Document"...
0xd6f0a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f0f  ldloc.1
0xd6f10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd6f15  ldstr    aExporttoexcelS_1// "ExportToExcel.Static.Source"
0xd6f1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd6f1f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xd6f24  ldloc.1
0xd6f25  ldstr    aOSourceOMscrmv// "</o:Source>\r\n\t\t\t  <o:MSCRMVersion "...
0xd6f2a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f2f  ldloc.1
0xd6f30  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0xd6f35  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_FullVersion()
0xd6f3a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xd6f3f  ldloc.1
0xd6f40  ldstr    aOMscrmversionO// "</o:MSCRMVersion>\r\n\t\t\t </o:CustomD"...
0xd6f45  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f4a  ldloc.1
0xd6f4b  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xd6f50  ldarg.1
0xd6f51  ldstr    aIfGteMso9// "<!--[if gte mso 9]>"
0xd6f56  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6f5b  ldarg.1
0xd6f5c  ldstr    aXml_1// "<xml>"
0xd6f61  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd6f66  ldarg.1
0xd6f67  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0xd6f6c  ldloc.1
0xd6f6d  ldstr    aXExcelworkbook// "<x:ExcelWorkbook><x:ExcelWorksheets><x:"...
0xd6f72  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f77  ldloc.1
0xd6f78  ldstr    aXName// "<x:Name>"
0xd6f7d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f82  ldloc.1
0xd6f83  ldarg.2
0xd6f84  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GenerateValidExcelWorkSheetTitle(string)
0xd6f89  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xd6f8e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f93  ldloc.1
0xd6f94  ldstr    aXName_0// "</x:Name>"
0xd6f99  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6f9e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd6fa3  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xd6fa8  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xd6fad  brfalse.s loc_D6FBA
0xd6faf  ldloc.1
0xd6fb0  ldstr    aXRighttoleft1X// "<x:RightToLeft>1</x:RightToLeft>"
0xd6fb5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6fba  ldloc.1
0xd6fbb  ldstr    aXWorksheetopti// "<x:WorksheetOptions><x:Selected/>"
0xd6fc0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6fc5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd6fca  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xd6fcf  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xd6fd4  brfalse.s loc_D6FE1
0xd6fd6  ldloc.1
0xd6fd7  ldstr    aXDisplayrightt// "<x:DisplayRightToLeft/>"
0xd6fdc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6fe1  ldloc.1
0xd6fe2  ldstr    aXWorksheetopti_0// "</x:WorksheetOptions>"
0xd6fe7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6fec  ldloc.1
0xd6fed  ldstr    aXExcelworkshee// "</x:ExcelWorksheet></x:ExcelWorksheets>"...
0xd6ff2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0xd6ff7  ldloc.1
0xd6ff8  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xd6ffd  ldarg.1
0xd6ffe  ldstr    aXml_2// "</xml>"
0xd7003  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd7008  ldarg.1
0xd7009  ldstr    aEndif// "<![endif]-->"
0xd700e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd7013  ldarg.1
0xd7014  ldstr    aHead_0// "</head>"
0xd7019  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd701e  ldarg.1
0xd701f  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine()
0xd7024  ldarg.1
0xd7025  ldstr    aBody_2// "<body>"
0xd702a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xd702f  ret
```
