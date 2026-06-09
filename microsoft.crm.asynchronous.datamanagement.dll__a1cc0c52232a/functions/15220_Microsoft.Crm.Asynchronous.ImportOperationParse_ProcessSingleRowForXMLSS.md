# Microsoft.Crm.Asynchronous.ImportOperationParse::ProcessSingleRowForXMLSS

- ea: `0x15220`
- end: `0x15566`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::ProcessSingleRowForXMLSS`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14cb0`

## callees

- `0x3b80`
- `0x51d0`
- `0x8f40`
- `0x15220`
- `0x15570`
- `0x156b0`
- `0x15f30`
- `0x15fb0`
- `0x163d0`

## pseudocode

```c

```

## disassembly

```asm
0x15220  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x15225  stloc.0
0x15226  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1522b  stloc.1
0x1522c  ldc.i4.0
0x1522d  stloc.2
0x1522e  ldarg.2
0x1522f  ldstr    aFielddelimiter// "fielddelimitercode"
0x15234  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15239  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1523e  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x15243  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CsvDataParser::GetFieldDelimiter(int32)
0x15248  stloc.3
0x15249  ldarg.s  4
0x1524b  newarr   [mscorlib]System.String
0x15250  stloc.s  4
0x15252  ldc.i4.0
0x15253  stloc.s  0xB
0x15255  br       loc_153ED
0x1525a  ldloc.s  0xB
0x1525c  ldc.i4.1
0x1525d  add
0x1525e  stloc.s  0xC
0x15260  ldloc.s  4
0x15262  ldloc.s  0xB
0x15264  ldarg.s  5
0x15266  ldloc.s  0xC
0x15268  callvirt instance class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::GetCellAtIndex(int32)
0x1526d  brfalse.s loc_1527F
0x1526f  ldarg.s  5
0x15271  ldloc.s  0xC
0x15273  callvirt instance class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow::GetCellAtIndex(int32)
0x15278  callvirt instance string [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLCell::get_CellData()
0x1527d  br.s     loc_15284
0x1527f  ldsfld   string [mscorlib]System.String::Empty
0x15284  stelem.ref
0x15285  ldarg.0
0x15286  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1528b  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x15290  ldc.i4.1
0x15291  bne.un   loc_153A3
0x15296  ldloc.s  4
0x15298  ldloc.s  0xB
0x1529a  ldelem.ref
0x1529b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x152a0  brtrue   loc_153A3
0x152a5  ldarg.s  7
0x152a7  brfalse  loc_153A3
0x152ac  ldarg.s  7
0x152ae  ldloc.s  0xB
0x152b0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>>::ContainsKey(var<u1>)
0x152b5  brfalse  loc_153A3
0x152ba  ldarg.s  7
0x152bc  ldloc.s  0xB
0x152be  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>>::get_Item(void)
0x152c3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>::get_Item1()
0x152c8  stloc.s  0xE
0x152ca  ldarg.s  7
0x152cc  ldloc.s  0xB
0x152ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>>::get_Item(void)
0x152d3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, class [mscorlib]System.Type>::get_Item2()
0x152d8  stloc.s  0xF
0x152da  ldloc.s  0xF
0x152dc  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money
0x152e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152e6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x152eb  brtrue.s loc_15300
0x152ed  ldloc.s  0xF
0x152ef  ldtoken  [mscorlib]System.Decimal
0x152f4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x152f9  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x152fe  brfalse.s loc_1534B
0x15300  ldloc.s  4
0x15302  ldloc.s  0xB
0x15304  ldelem.ref
0x15305  ldc.i4   0xA7
0x1530a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1530f  ldloca.s 0x10
0x15311  call     bool [mscorlib]System.Decimal::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Decimal&)
0x15316  brfalse  loc_153A3
0x1531b  ldloc.s  0x10
0x1531d  ldloc.s  0xE
0x1531f  ldc.i4.1
0x15320  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Round(valuetype [mscorlib]System.Decimal, int32, valuetype [mscorlib]System.MidpointRounding)
0x15325  stloc.s  0x10
0x15327  ldloc.s  4
0x15329  ldloc.s  0xB
0x1532b  ldloca.s 0x10
0x1532d  ldstr    aF// "F"
0x15332  ldloc.s  0xE
0x15334  box      [mscorlib]System.Int32
0x15339  call     string [mscorlib]System.String::Concat(object, object)
0x1533e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15343  call     instance string [mscorlib]System.Decimal::ToString(string, class [mscorlib]System.IFormatProvider)
0x15348  stelem.ref
0x15349  br.s     loc_153A3
0x1534b  ldloc.s  0xF
0x1534d  ldtoken  [mscorlib]System.Double
0x15352  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15357  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1535c  brfalse.s loc_153A3
0x1535e  ldloc.s  4
0x15360  ldloc.s  0xB
0x15362  ldelem.ref
0x15363  ldc.i4   0xA7
0x15368  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1536d  ldloca.s 0x11
0x1536f  call     bool [mscorlib]System.Double::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, float64&)
0x15374  brfalse.s loc_153A3
0x15376  ldloc.s  0x11
0x15378  ldloc.s  0xE
0x1537a  call     float64 [mscorlib]System.Math::Round(float64, int32)
0x1537f  stloc.s  0x12
0x15381  ldloc.s  4
0x15383  ldloc.s  0xB
0x15385  ldloca.s 0x12
0x15387  ldstr    aF// "F"
0x1538c  ldloc.s  0xE
0x1538e  box      [mscorlib]System.Int32
0x15393  call     string [mscorlib]System.String::Concat(object, object)
0x15398  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1539d  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x153a2  stelem.ref
0x153a3  ldloc.s  4
0x153a5  ldloc.s  0xB
0x153a7  ldelem.ref
0x153a8  stloc.s  0xD
0x153aa  ldloc.s  0xD
0x153ac  ldloc.3
0x153ad  callvirt instance bool [mscorlib]System.String::Contains(string)
0x153b2  brfalse.s loc_153D6
0x153b4  ldstr    asc_2D7D0// "\""
0x153b9  ldloc.s  0xD
0x153bb  ldstr    asc_2D7D0// "\""
0x153c0  ldstr    asc_2D7D4// "\"\""
0x153c5  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x153ca  ldstr    asc_2D7D0// "\""
0x153cf  call     string [mscorlib]System.String::Concat(string, string, string)
0x153d4  stloc.s  0xD
0x153d6  ldloc.1
0x153d7  ldloc.s  0xD
0x153d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x153de  pop
0x153df  ldloc.1
0x153e0  ldloc.3
0x153e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x153e6  pop
0x153e7  ldloc.s  0xB
0x153e9  ldc.i4.1
0x153ea  add
0x153eb  stloc.s  0xB
0x153ed  ldloc.s  0xB
0x153ef  ldarg.s  4
0x153f1  blt      loc_1525A
0x153f6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x153fb  stloc.s  5
0x153fd  ldloc.1
0x153fe  ldc.i4.0
0x153ff  ldloc.1
0x15400  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x15405  ldloc.3
0x15406  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1540b  sub
0x1540c  callvirt instance string [mscorlib]System.Text.StringBuilder::ToString(int32, int32)
0x15411  stloc.s  6
0x15413  ldstr    aCellsAtTheFoll// "Cells at the following column indexes h"...
0x15418  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1541d  stloc.s  7
0x1541f  ldarg.0
0x15420  ldarg.s  4
0x15422  ldarg.s  5
0x15424  ldloc.s  7
0x15426  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationParse::CheckForCellsHavingInvalidContent(int32 numColumns, class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow smlRow, class [mscorlib]System.Text.StringBuilder cellsHavingInvalidContent)
0x1542b  stloc.s  8
0x1542d  ldc.i4.0
0x1542e  stloc.s  9
0x15430  ldstr    aTheFollowingCo// "The following column indexes have data "...
0x15435  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x1543a  stloc.s  0xA
0x1543c  ldloc.s  8
0x1543e  brtrue.s loc_15462
0x15440  ldarg.0
0x15441  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x15446  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1544b  ldc.i4.1
0x1544c  bne.un.s loc_15462
0x1544e  ldarg.0
0x1544f  ldarg.s  6
0x15451  ldarg.s  4
0x15453  ldarg.s  5
0x15455  ldloc.s  0xA
0x15457  ldloc.s  4
0x15459  ldloca.s 9
0x1545b  ldloca.s 2
0x1545d  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::ProcessSingleRowForUpdateViaImport(class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLMetadata spreadsheetMLMetadata, int32 numColumns, class [Microsoft.Crm]Microsoft.Crm.SpreadsheetMLRow smlRow, class [mscorlib]System.Text.StringBuilder columnIndexesHavingTypeProblems, string[] rowItems, bool& hasError, bool& skipRowForUpdate)
0x15462  ldloc.2
0x15463  brtrue   loc_15553
0x15468  ldarg.0
0x15469  ldarg.1
0x1546a  ldloc.s  5
0x1546c  ldloc.0
0x1546d  ldloc.s  6
0x1546f  ldarg.s  8
0x15471  ldind.i8
0x15472  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::AddImportDataRecord(valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid importDataId, valuetype [mscorlib]System.Guid recordId, string rawRecord, int64 originalDataRowNumber)
0x15477  ldarg.0
0x15478  ldloc.s  5
0x1547a  ldloc.0
0x1547b  ldarg.1
0x1547c  ldarg.3
0x1547d  ldarg.2
0x1547e  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x15483  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x15488  ldarg.2
0x15489  ldstr    aParsedtablecol_0// "parsedtablecolumnsnumber"
0x1548e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x15493  unbox.any [mscorlib]System.Int32
0x15498  ldloc.s  4
0x1549a  ldarg.s  8
0x1549c  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::CreateParsedRow(valuetype [mscorlib]System.Guid importDataId, valuetype [mscorlib]System.Guid recordId, valuetype [mscorlib]System.Guid importFileId, string parsedTableName, string parsedTableColumnPrefix, int32 parsedTableColumnsNumber, string[] values, int64& rowNumber)
0x154a1  ldloc.s  9
0x154a3  brfalse.s loc_154FA
0x154a5  ldloc.s  0xA
0x154a7  ldloc.s  0xA
0x154a9  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x154ae  ldc.i4.1
0x154af  sub
0x154b0  ldc.i4.1
0x154b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x154b6  pop
0x154b7  ldarg.0
0x154b8  ldarg.3
0x154b9  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables(string parsedTableName)
0x154be  ldarg.0
0x154bf  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x154c4  ldarg.0
0x154c5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x154ca  ldarg.0
0x154cb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x154d0  ldarg.1
0x154d1  ldloc.s  5
0x154d3  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x154d8  ldc.i4.0
0x154d9  ldsfld   string [mscorlib]System.String::Empty
0x154de  ldsfld   string [mscorlib]System.String::Empty
0x154e3  ldc.i4   0x8004F601
0x154e8  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x154ed  ldloc.s  0xA
0x154ef  callvirt instance string [mscorlib]System.Object::ToString()
0x154f4  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x154f9  ret
0x154fa  ldloc.s  8
0x154fc  brfalse.s loc_15565
0x154fe  ldloc.s  7
0x15500  ldloc.s  7
0x15502  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x15507  ldc.i4.1
0x15508  sub
0x15509  ldc.i4.1
0x1550a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x1550f  pop
0x15510  ldarg.0
0x15511  ldarg.3
0x15512  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables(string parsedTableName)
0x15517  ldarg.0
0x15518  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1551d  ldarg.0
0x1551e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x15523  ldarg.0
0x15524  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x15529  ldarg.1
0x1552a  ldloc.s  5
0x1552c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x15531  ldc.i4.0
0x15532  ldsfld   string [mscorlib]System.String::Empty
0x15537  ldsfld   string [mscorlib]System.String::Empty
0x1553c  ldc.i4   0x80040351
0x15541  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x15546  ldloc.s  7
0x15548  callvirt instance string [mscorlib]System.Object::ToString()
0x1554d  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x15552  ret
0x15553  ldarg.s  8
0x15555  ldarg.s  8
0x15557  ldind.i8
0x15558  ldc.i4.1
0x15559  conv.i8
0x1555a  add
0x1555b  stind.i8
0x1555c  ldarg.s  9
0x1555e  ldarg.s  9
0x15560  ldind.i8
0x15561  ldc.i4.1
0x15562  conv.i8
0x15563  add
0x15564  stind.i8
0x15565  ret
```
