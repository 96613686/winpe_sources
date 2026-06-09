# Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillMiscDetails

- ea: `0x8c530`
- end: `0x8c6f9`
- name: `Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillMiscDetails`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x8c330`

## callees

- `0xe1c0`
- `0xfd20`
- `0x11760`
- `0x2fb90`
- `0x30260`
- `0x8c530`
- `0x8d3f0`

## string_xrefs

- `0x8c551`: `Created`
- `0x8c566`: `Company`
- `0x8c584`: `IW_ExportTemplate_HeaderChange_Message`
- `0x8c594`: `IW_ExportTemplate_HeaderChange_Title`

## pseudocode

```c

```

## disassembly

```asm
0x8c530  ldarg.1
0x8c531  ldstr    aMiscdetails// "MiscDetails"
0x8c536  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x8c53b  ldarg.1
0x8c53c  ldstr    aAuthor// "Author"
0x8c541  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser Microsoft.Crm.Security.User::get_Current()
0x8c546  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x8c54b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c550  ldarg.1
0x8c551  ldstr    aCreated// "Created"
0x8c556  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_Now()
0x8c55b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_Value()
0x8c560  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c565  ldarg.1
0x8c566  ldstr    aCompany// "Company"
0x8c56b  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c570  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8c575  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_Name()
0x8c57a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c57f  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c584  ldstr    aIwExporttempla_23// "IW_ExportTemplate_HeaderChange_Message"
0x8c589  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c58e  stloc.0
0x8c58f  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c594  ldstr    aIwExporttempla_24// "IW_ExportTemplate_HeaderChange_Title"
0x8c599  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c59e  stloc.1
0x8c59f  ldloc.0
0x8c5a0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8c5a5  ldc.i4   0xFF
0x8c5aa  ble.s    loc_8C5B9
0x8c5ac  ldloc.0
0x8c5ad  ldc.i4.0
0x8c5ae  ldc.i4   0xFF
0x8c5b3  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8c5b8  stloc.0
0x8c5b9  ldloc.1
0x8c5ba  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8c5bf  ldc.i4.s 0x20
0x8c5c1  ble.s    loc_8C5CD
0x8c5c3  ldloc.1
0x8c5c4  ldc.i4.0
0x8c5c5  ldc.i4.s 0x20
0x8c5c7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8c5cc  stloc.1
0x8c5cd  ldarg.1
0x8c5ce  ldstr    aHeadererrormes// "HeaderErrorMessage"
0x8c5d3  ldloc.0
0x8c5d4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c5d9  ldarg.1
0x8c5da  ldstr    aHeadererrortit// "HeaderErrorTitle"
0x8c5df  ldloc.1
0x8c5e0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c5e5  ldarg.1
0x8c5e6  ldstr    aHeaderrowforeg// "HeaderRowForegroundColor"
0x8c5eb  ldstr    aFfffff// "#FFFFFF"
0x8c5f0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c5f5  ldarg.1
0x8c5f6  ldstr    aHeaderrowbackg// "HeaderRowBackgroundColor"
0x8c5fb  ldstr    a333399// "#333399"
0x8c600  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c605  ldarg.1
0x8c606  ldstr    aHeaderrowbackg_0// "HeaderRowBackgroundColorPattern"
0x8c60b  ldstr    aSolid// "Solid"
0x8c610  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c615  ldarg.1
0x8c616  ldstr    aHeaderrowfontn// "HeaderRowFontName"
0x8c61b  ldstr    aCalibri// "Calibri"
0x8c620  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c625  ldarg.1
0x8c626  ldstr    aHeaderrowfontf// "HeaderRowFontFamily"
0x8c62b  ldstr    aSwiss// "Swiss"
0x8c630  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c635  ldarg.1
0x8c636  ldstr    aHeaderrowfonts// "HeaderRowFontSize"
0x8c63b  ldstr    a11// "11"
0x8c640  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c645  ldarg.1
0x8c646  ldstr    aHeaderrowrequi// "HeaderRowRequiredCellBold"
0x8c64b  ldstr    a1// "1"
0x8c650  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c655  ldarg.1
0x8c656  ldstr    aDefaultfontnam// "DefaultFontName"
0x8c65b  ldstr    aCalibri// "Calibri"
0x8c660  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c665  ldarg.1
0x8c666  ldstr    aDefaultfontfam// "DefaultFontFamily"
0x8c66b  ldstr    aSwiss// "Swiss"
0x8c670  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c675  ldarg.1
0x8c676  ldstr    aDefaultfontsiz// "DefaultFontSize"
0x8c67b  ldstr    a10_0// "10"
0x8c680  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c685  ldarg.1
0x8c686  ldstr    aDefaultforegro// "DefaultForegroundColor"
0x8c68b  ldstr    a000000// "#000000"
0x8c690  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c695  ldarg.1
0x8c696  ldstr    aEnabledatavali// "EnableDataValidation"
0x8c69b  ldc.i4.1
0x8c69c  stloc.2
0x8c69d  ldloca.s 2
0x8c69f  call     instance string [mscorlib]System.Boolean::ToString()
0x8c6a4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c6a9  ldarg.1
0x8c6aa  ldstr    aEnabledatavali_0// "EnableDataValidationForHeaderRow"
0x8c6af  ldc.i4.1
0x8c6b0  stloc.2
0x8c6b1  ldloca.s 2
0x8c6b3  call     instance string [mscorlib]System.Boolean::ToString()
0x8c6b8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c6bd  ldarg.1
0x8c6be  ldstr    aAddcellindexes// "AddCellIndexes"
0x8c6c3  ldarg.0
0x8c6c4  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c6c9  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetExportMode Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_SpreadsheetMode()
0x8c6ce  ldc.i4.1
0x8c6cf  ceq
0x8c6d1  stloc.2
0x8c6d2  ldloca.s 2
0x8c6d4  call     instance string [mscorlib]System.Boolean::ToString()
0x8c6d9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c6de  ldarg.1
0x8c6df  ldstr    aAddcolumnwidth// "AddColumnWidths"
0x8c6e4  ldc.i4.0
0x8c6e5  stloc.2
0x8c6e6  ldloca.s 2
0x8c6e8  call     instance string [mscorlib]System.Boolean::ToString()
0x8c6ed  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c6f2  ldarg.1
0x8c6f3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x8c6f8  ret
```
