# Microsoft.Crm.SpreadsheetMLParser::ReturnHiddenSheetData

- ea: `0x23ca0`
- end: `0x23e17`
- name: `Microsoft.Crm.SpreadsheetMLParser::ReturnHiddenSheetData`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x23ca0`
- `0x23e90`
- `0x23f30`
- `0x23f50`
- `0x23fe0`
- `0x24000`

## string_xrefs

- `0x23cad`: `SpreadsheetML file has not been initialized`

## pseudocode

```c

```

## disassembly

```asm
0x23ca0  ldarg.0
0x23ca1  ldfld    string Microsoft.Crm.SpreadsheetMLParser::_content
0x23ca6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23cab  brfalse.s loc_23CB8
0x23cad  ldstr    aSpreadsheetmlF// "SpreadsheetML file has not been initial"...
0x23cb2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x23cb7  throw
0x23cb8  ldnull
0x23cb9  stloc.0
0x23cba  newobj   instance void Microsoft.Crm.SpreadsheetMLTable::.ctor()
0x23cbf  stloc.1
0x23cc0  ldc.i4.0
0x23cc1  stloc.2
0x23cc2  ldc.i4.0
0x23cc3  stloc.3
0x23cc4  ldarg.1
0x23cc5  ldc.i4.0
0x23cc6  stind.i4
0x23cc7  ldarg.0
0x23cc8  ldfld    string Microsoft.Crm.SpreadsheetMLParser::_content
0x23ccd  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0x23cd2  stloc.s  4
0x23cd4  br       loc_23DE7
0x23cd9  ldloc.s  4
0x23cdb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x23ce0  ldc.i4.1
0x23ce1  bne.un   loc_23DE7
0x23ce6  ldloc.s  4
0x23ce8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x23ced  ldstr    aWorksheet// "Worksheet"
0x23cf2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23cf7  brfalse.s loc_23D07
0x23cf9  ldarg.1
0x23cfa  ldarg.1
0x23cfb  ldind.i4
0x23cfc  ldc.i4.1
0x23cfd  add
0x23cfe  stind.i4
0x23cff  ldarg.1
0x23d00  ldind.i4
0x23d01  ldc.i4.2
0x23d02  bgt      loc_23DF3
0x23d07  ldloc.s  4
0x23d09  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x23d0e  ldstr    aRow// "Row"
0x23d13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23d18  brfalse.s loc_23D66
0x23d1a  ldarg.1
0x23d1b  ldind.i4
0x23d1c  ldc.i4.2
0x23d1d  bne.un.s loc_23D66
0x23d1f  ldc.i4.0
0x23d20  stloc.2
0x23d21  ldloc.3
0x23d22  ldc.i4.1
0x23d23  add
0x23d24  stloc.3
0x23d25  ldloc.s  4
0x23d27  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x23d2c  ldc.i4.1
0x23d2d  bne.un.s loc_23D57
0x23d2f  ldloc.s  4
0x23d31  ldstr    aSsIndex// "ss:Index"
0x23d36  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToAttribute(string)
0x23d3b  brfalse.s loc_23D57
0x23d3d  ldloc.s  4
0x23d3f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x23d44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23d49  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x23d4e  stloc.3
0x23d4f  ldloc.s  4
0x23d51  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x23d56  pop
0x23d57  ldloc.3
0x23d58  conv.i8
0x23d59  newobj   instance void Microsoft.Crm.SpreadsheetMLRow::.ctor(int64 rowIndex)
0x23d5e  stloc.0
0x23d5f  ldloc.1
0x23d60  ldloc.0
0x23d61  callvirt instance void Microsoft.Crm.SpreadsheetMLTable::AddRowToTable(class Microsoft.Crm.SpreadsheetMLRow row)
0x23d66  ldloc.s  4
0x23d68  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x23d6d  ldstr    aCell// "Cell"
0x23d72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23d77  brfalse.s loc_23DE7
0x23d79  ldarg.1
0x23d7a  ldind.i4
0x23d7b  ldc.i4.2
0x23d7c  bne.un.s loc_23DE7
0x23d7e  ldloc.2
0x23d7f  ldc.i4.1
0x23d80  add
0x23d81  stloc.2
0x23d82  ldloc.s  4
0x23d84  ldstr    aSsIndex// "ss:Index"
0x23d89  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToAttribute(string)
0x23d8e  brfalse.s loc_23DAA
0x23d90  ldloc.s  4
0x23d92  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x23d97  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23d9c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x23da1  stloc.2
0x23da2  ldloc.s  4
0x23da4  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x23da9  pop
0x23daa  ldloc.s  4
0x23dac  ldstr    aData_0// "Data"
0x23db1  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToDescendant(string)
0x23db6  brfalse.s loc_23DE7
0x23db8  ldloc.s  4
0x23dba  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x23dbf  ldc.i4.1
0x23dc0  bne.un.s loc_23DCA
0x23dc2  ldloc.s  4
0x23dc4  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x23dc9  pop
0x23dca  ldloc.s  4
0x23dcc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x23dd1  ldc.i4.3
0x23dd2  bne.un.s loc_23DE7
0x23dd4  ldloc.0
0x23dd5  ldloc.2
0x23dd6  ldloc.s  4
0x23dd8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x23ddd  newobj   instance void Microsoft.Crm.SpreadsheetMLCell::.ctor(int32 columnIndex, string cellData)
0x23de2  callvirt instance void Microsoft.Crm.SpreadsheetMLRow::AddCellToRow(class Microsoft.Crm.SpreadsheetMLCell cell)
0x23de7  ldloc.s  4
0x23de9  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x23dee  brtrue   loc_23CD9
0x23df3  leave.s  loc_23E01
0x23df5  ldloc.s  4
0x23df7  brfalse.s loc_23E00
0x23df9  ldloc.s  4
0x23dfb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23e00  endfinally
0x23e01  leave.s  loc_23E15
0x23e03  pop
0x23e04  ldc.i4   0x80040351
0x23e09  ldc.i4.0
0x23e0a  newarr   [mscorlib]System.Object
0x23e0f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23e14  throw
0x23e15  ldloc.1
0x23e16  ret
```
