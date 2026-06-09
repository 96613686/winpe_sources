# Microsoft.Crm.Asynchronous.ImportOperationParse::PopulateParseTableForSpreadsheetML

- ea: `0x14cb0`
- end: `0x15056`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::PopulateParseTableForSpreadsheetML`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14370`

## callees

- `0x3b80`
- `0x3d80`
- `0x4240`
- `0x4320`
- `0x51d0`
- `0x61e0`
- `0x6220`
- `0x62b0`
- `0x8f40`
- `0xbcb0`
- `0x14cb0`
- `0x15060`
- `0x15220`
- `0x15f30`

## string_xrefs

- `0x14f12`: `urn:schemas-microsoft-com:office:spreadsheet`

## pseudocode

```c

```

## disassembly

```asm
0x14cb0  ldarg.2
0x14cb1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x14cb6  stloc.0
0x14cb7  ldarg.2
0x14cb8  ldstr    aIsfirstrowhead// "isfirstrowheader"
0x14cbd  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14cc2  unbox.any [mscorlib]System.Boolean
0x14cc7  stloc.1
0x14cc8  ldarg.0
0x14cc9  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x14cce  ldarg.1
0x14ccf  ldloc.0
0x14cd0  callvirt instance string Microsoft.Crm.Asynchronous.ImportDataAccess::GetContentFromImportFile(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid importFileId)
0x14cd5  stloc.2
0x14cd6  ldarg.3
0x14cd7  ldlen
0x14cd8  conv.i4
0x14cd9  stloc.3
0x14cda  ldarg.2
0x14cdb  ldstr    aParsedtablenam_0// "parsedtablename"
0x14ce0  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x14ce5  stloc.s  4
0x14ce7  ldnull
0x14ce8  stloc.s  5
0x14cea  ldc.i4.0
0x14ceb  stloc.s  6
0x14ced  ldc.i4.1
0x14cee  conv.i8
0x14cef  stloc.s  7
0x14cf1  ldnull
0x14cf2  stloc.s  8
0x14cf4  ldc.i4.0
0x14cf5  stloc.s  9
0x14cf7  ldc.i4.0
0x14cf8  stloc.s  0xA
0x14cfa  ldc.i4.0
0x14cfb  stloc.s  0xB
0x14cfd  ldc.i4.0
0x14cfe  conv.i8
0x14cff  stloc.s  0xC
0x14d01  ldc.i4.0
0x14d02  conv.i8
0x14d03  stloc.s  0xD
0x14d05  ldc.i4.0
0x14d06  stloc.s  0xE
0x14d08  ldarg.0
0x14d09  ldarg.2
0x14d0a  ldstr    aParsedtablecol_0// "parsedtablecolumnsnumber"
0x14d0f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14d14  unbox.any [mscorlib]System.Int32
0x14d19  newarr   [mscorlib]System.Int32
0x14d1e  stfld    int32[] Microsoft.Crm.Asynchronous.ImportOperationParse::_parseTableCurrentColumnLength
0x14d23  ldc.i4.0
0x14d24  stloc.s  0x10
0x14d26  br.s     loc_14D42
0x14d28  ldarg.0
0x14d29  ldfld    int32[] Microsoft.Crm.Asynchronous.ImportOperationParse::_parseTableCurrentColumnLength
0x14d2e  ldloc.s  0x10
0x14d30  ldarg.0
0x14d31  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0x14d36  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_ParsedColumnDefaultSize()
0x14d3b  stelem.i4
0x14d3c  ldloc.s  0x10
0x14d3e  ldc.i4.1
0x14d3f  add
0x14d40  stloc.s  0x10
0x14d42  ldloc.s  0x10
0x14d44  ldarg.0
0x14d45  ldfld    int32[] Microsoft.Crm.Asynchronous.ImportOperationParse::_parseTableCurrentColumnLength
0x14d4a  ldlen
0x14d4b  conv.i4
0x14d4c  blt.s    loc_14D28
0x14d4e  ldarg.0
0x14d4f  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x14d54  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x14d59  ldc.i4.1
0x14d5a  bne.un.s loc_14D7A
0x14d5c  ldarg.s  4
0x14d5e  callvirt instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAttributeMetadata()
0x14d63  ldarg.0
0x14d64  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0x14d69  ldc.i4.1
0x14d6a  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0x14d6f  stloc.s  0x11
0x14d71  ldarg.s  4
0x14d73  ldloc.s  0x11
0x14d75  callvirt instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulatePrecisionDictionary(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmServiceInSystemUserContext)
0x14d7a  ldnull
0x14d7b  stloc.s  0xF
0x14d7d  ldarg.0
0x14d7e  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x14d83  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x14d88  ldc.i4.1
0x14d89  bne.un.s loc_14DF6
0x14d8b  ldarg.2
0x14d8c  ldstr    aRelatedentityc// "relatedentitycolumns"
0x14d91  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14d96  castclass [mscorlib]System.String
0x14d9b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLMetadata::.ctor(string)
0x14da0  stloc.s  0xF
0x14da2  ldloc.s  0xF
0x14da4  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLMetadata::IsValidMetadata()
0x14da9  brtrue.s loc_14DF6
0x14dab  ldarg.0
0x14dac  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x14db1  ldarg.0
0x14db2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x14db7  ldarg.0
0x14db8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x14dbd  ldloc.0
0x14dbe  ldloca.s 0x12
0x14dc0  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x14dc6  ldloc.s  0x12
0x14dc8  ldc.i4.0
0x14dc9  ldsfld   string [mscorlib]System.String::Empty
0x14dce  ldsfld   string [mscorlib]System.String::Empty
0x14dd3  ldc.i4   0x80040349
0x14dd8  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x14ddd  ldsfld   string [mscorlib]System.String::Empty
0x14de2  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x14de7  ldarg.0
0x14de8  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x14ded  ldloc.0
0x14dee  ldc.i4.5
0x14def  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatus(valuetype [mscorlib]System.Guid importFileId, int32 status)
0x14df4  ldnull
0x14df5  ret
0x14df6  ldloc.2
0x14df7  ldc.i4.1
0x14df8  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string, bool)
0x14dfd  stloc.s  0x13
0x14dff  br       loc_15008
0x14e04  ldloc.s  0x13
0x14e06  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x14e0b  ldc.i4.1
0x14e0c  bne.un   loc_14F7F
0x14e11  ldloc.s  0x13
0x14e13  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x14e18  ldstr    aWorksheet// "Worksheet"
0x14e1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e22  brfalse.s loc_14E34
0x14e24  ldloc.s  0xB
0x14e26  ldc.i4.1
0x14e27  add
0x14e28  stloc.s  0xB
0x14e2a  ldloc.s  0xB
0x14e2c  ldc.i4.1
0x14e2d  ble.s    loc_14E34
0x14e2f  leave    loc_15022
0x14e34  ldloc.s  0x13
0x14e36  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x14e3b  ldstr    aRow// "Row"
0x14e40  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e45  brfalse.s loc_14EB2
0x14e47  ldc.i4.0
0x14e48  stloc.s  9
0x14e4a  ldloc.s  0x13
0x14e4c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x14e51  ldc.i4.1
0x14e52  bne.un.s loc_14E8B
0x14e54  ldloc.s  0x13
0x14e56  ldstr    aSsIndex// "ss:Index"
0x14e5b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToAttribute(string)
0x14e60  brfalse.s loc_14E8B
0x14e62  ldloc.s  0x13
0x14e64  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x14e69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14e6e  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x14e73  stloc.s  0x14
0x14e75  ldloc.s  0xD
0x14e77  ldloc.s  0x14
0x14e79  ldloc.s  7
0x14e7b  sub
0x14e7c  add
0x14e7d  stloc.s  0xD
0x14e7f  ldloc.s  0x14
0x14e81  stloc.s  7
0x14e83  ldloc.s  0x13
0x14e85  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x14e8a  pop
0x14e8b  ldloc.s  6
0x14e8d  ldc.i4.0
0x14e8e  ceq
0x14e90  ldloc.1
0x14e91  and
0x14e92  brfalse.s loc_14EA3
0x14e94  ldc.i4.1
0x14e95  stloc.s  6
0x14e97  ldc.i4.2
0x14e98  conv.i8
0x14e99  stloc.s  7
0x14e9b  ldc.i4.1
0x14e9c  stloc.s  0xA
0x14e9e  br       loc_15008
0x14ea3  ldc.i4.0
0x14ea4  stloc.s  0xA
0x14ea6  ldloc.s  7
0x14ea8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::.ctor(int64)
0x14ead  stloc.s  8
0x14eaf  ldc.i4.1
0x14eb0  stloc.s  0xE
0x14eb2  ldloc.s  0x13
0x14eb4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x14eb9  ldstr    aCell// "Cell"
0x14ebe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14ec3  brfalse  loc_14F7F
0x14ec8  ldloc.s  0xA
0x14eca  brtrue   loc_14F7F
0x14ecf  ldloc.s  9
0x14ed1  ldc.i4.1
0x14ed2  add
0x14ed3  stloc.s  9
0x14ed5  ldc.i4.3
0x14ed6  stloc.s  0x15
0x14ed8  ldloc.s  0x13
0x14eda  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x14edf  ldc.i4.1
0x14ee0  bne.un.s loc_14F0B
0x14ee2  ldloc.s  0x13
0x14ee4  ldstr    aSsIndex// "ss:Index"
0x14ee9  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToAttribute(string)
0x14eee  brfalse.s loc_14F0B
0x14ef0  ldloc.s  0x13
0x14ef2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x14ef7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14efc  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x14f01  stloc.s  9
0x14f03  ldloc.s  0x13
0x14f05  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x14f0a  pop
0x14f0b  ldloc.s  0x13
0x14f0d  ldstr    aData_1// "Data"
0x14f12  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:office:spread"...
0x14f17  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToDescendant(string, string)
0x14f1c  brfalse.s loc_14F7F
0x14f1e  ldloc.s  0x13
0x14f20  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x14f25  stloc.s  0x16
0x14f27  ldloc.s  0x13
0x14f29  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x14f2e  stloc.s  0x17
0x14f30  ldloc.s  0x13
0x14f32  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x14f37  ldc.i4.1
0x14f38  bne.un.s loc_14F6B
0x14f3a  ldloc.s  0x13
0x14f3c  ldstr    aSsType// "ss:Type"
0x14f41  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToAttribute(string)
0x14f46  brfalse.s loc_14F63
0x14f48  ldloc.s  0x13
0x14f4a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x14f4f  ldloca.s 0x15
0x14f51  call     T0x2B00000B
0x14f56  brtrue.s loc_14F5B
0x14f58  ldc.i4.3
0x14f59  stloc.s  0x15
0x14f5b  ldloc.s  0x13
0x14f5d  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x14f62  pop
0x14f63  ldloc.s  0x13
0x14f65  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x14f6a  pop
0x14f6b  ldarg.0
0x14f6c  ldloc.s  0x13
0x14f6e  ldloc.s  9
0x14f70  ldloc.s  0x16
0x14f72  ldloc.s  0x17
0x14f74  ldloc.s  0x15
0x14f76  ldloc.s  8
0x14f78  ldloca.s 0xE
0x14f7a  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::CreateSpreadsheetMLCell(class [System.Xml]System.Xml.XmlReader reader, int32 indexCount, int32 dataNodeDepth, bool isDataNodeEmpty, valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCellType cellDataType, class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow smlRow, bool& emptyRow)
0x14f7f  ldloc.s  0x13
0x14f81  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x14f86  ldc.i4.s 0xF
0x14f88  bne.un.s loc_15008
0x14f8a  ldloc.s  0x13
0x14f8c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x14f91  ldstr    aRow// "Row"
0x14f96  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14f9b  brfalse.s loc_15008
0x14f9d  ldloc.s  0xA
0x14f9f  brtrue.s loc_15008
0x14fa1  ldloc.s  8
0x14fa3  brfalse.s loc_15008
0x14fa5  ldloc.s  8
0x14fa7  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::get_NonemptyCellCount()
0x14fac  ldc.i4.0
0x14fad  cgt
0x14faf  ldc.i4.0
0x14fb0  ceq
0x14fb2  ldloc.s  0xE
0x14fb4  or
0x14fb5  brfalse.s loc_14FCA
0x14fb7  ldc.i4.0
0x14fb8  stloc.s  0xE
0x14fba  ldloc.s  0xD
0x14fbc  ldc.i4.1
0x14fbd  conv.i8
0x14fbe  add
0x14fbf  stloc.s  0xD
  ... truncated ...
```
