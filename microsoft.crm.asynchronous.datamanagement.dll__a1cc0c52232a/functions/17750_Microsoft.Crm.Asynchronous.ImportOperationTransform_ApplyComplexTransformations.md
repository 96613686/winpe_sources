# Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyComplexTransformations

- ea: `0x17750`
- end: `0x17902`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyComplexTransformations`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x16690`

## callees

- `0x3b80`
- `0x3c60`
- `0x47e0`
- `0x5ed0`
- `0x8f40`
- `0x8f70`
- `0xba70`
- `0xbcb0`
- `0x17750`
- `0x17910`
- `0x17eb0`
- `0x19a80`
- `0x19b50`

## string_xrefs

- `0x1782f`: `Applying Complex Transformation on records {0} to {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17750  ldnull
0x17751  stloc.0
0x17752  ldarg.0
0x17753  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x17758  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x1775d  ldarg.1
0x1775e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x17763  ldarg.0
0x17764  ldarg.1
0x17765  ldloca.s 1
0x17767  call     instance string[] Microsoft.Crm.Asynchronous.ImportOperationTransform::GetUniqueSourceColumnsAcrossAllTransformationMappings(valuetype [mscorlib]System.Guid importFileId, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>& columnNameToArrayIndex)
0x1776c  stloc.2
0x1776d  ldarg.0
0x1776e  ldarg.1
0x1776f  ldloc.2
0x17770  call     instance string[] Microsoft.Crm.Asynchronous.ImportOperationTransform::GetParsedTableColumnNames(valuetype [mscorlib]System.Guid importFileId, string[] csvColumns)
0x17775  stloc.3
0x17776  dup
0x17777  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1777c  ldstr    aParsedtablenam_0// "parsedtablename"
0x17781  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x17786  stloc.s  4
0x17788  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1778d  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x17792  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x17797  stloc.s  5
0x17799  ldarg.0
0x1779a  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0x1779f  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_BatchSize()
0x177a4  stloc.s  6
0x177a6  ldc.i4.1
0x177a7  conv.i8
0x177a8  stloc.s  7
0x177aa  ldarg.0
0x177ab  ldloc.s  4
0x177ad  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperation::GetTotalNumberOfRecords(string tableName)
0x177b2  conv.i8
0x177b3  stloc.s  8
0x177b5  ldloc.s  6
0x177b7  conv.i8
0x177b8  stloc.s  9
0x177ba  ldarg.0
0x177bb  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x177c0  ldarg.0
0x177c1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x177c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x177cb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection(valuetype [mscorlib]System.Guid organizationId)
0x177d0  stloc.s  0xA
0x177d2  ldloc.s  0xA
0x177d4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x177d9  br       loc_178E6
0x177de  ldarg.0
0x177df  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x177e4  ldloc.s  4
0x177e6  ldloc.s  5
0x177e8  ldloc.3
0x177e9  ldarg.0
0x177ea  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x177ef  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x177f4  ldc.i4.0
0x177f5  ceq
0x177f7  ldloc.s  7
0x177f9  ldloc.s  9
0x177fb  ldc.i4.6
0x177fc  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet(string tableName, string parsedTableColumnPrefix, string[] columnNames, bool addIsExistingRecordCheck, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x17801  stloc.s  0xB
0x17803  ldloc.s  0xB
0x17805  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Count()
0x1780a  ldc.i4.0
0x1780b  bgt.s    loc_17822
0x1780d  ldloc.s  7
0x1780f  ldloc.s  6
0x17811  conv.i8
0x17812  add
0x17813  stloc.s  7
0x17815  ldloc.s  9
0x17817  ldloc.s  6
0x17819  conv.i8
0x1781a  add
0x1781b  stloc.s  9
0x1781d  br       loc_178E6
0x17822  ldarg.0
0x17823  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x17828  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1782d  ldc.i4.s 0x18
0x1782f  ldstr    aApplyingComple_0// "Applying Complex Transformation on reco"...
0x17834  ldc.i4.2
0x17835  newarr   [mscorlib]System.Object
0x1783a  dup
0x1783b  ldc.i4.0
0x1783c  ldloc.s  7
0x1783e  box      [mscorlib]System.Int64
0x17843  stelem.ref
0x17844  dup
0x17845  ldc.i4.1
0x17846  ldloc.s  9
0x17848  box      [mscorlib]System.Int64
0x1784d  stelem.ref
0x1784e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17853  ldarg.0
0x17854  ldarg.1
0x17855  ldloc.s  0xB
0x17857  ldloc.1
0x17858  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyComplexTransformationsOnDataSet(valuetype [mscorlib]System.Guid importFileId, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> parsedDataRowList, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> columnNameToArrayIndex)
0x1785d  stloc.s  0xC
0x1785f  ldarg.0
0x17860  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x17865  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1786a  ldc.i4.s 0x18
0x1786c  ldstr    aUpdatingParsed// "Updating parsed table with transformed "...
0x17871  ldc.i4.2
0x17872  newarr   [mscorlib]System.Object
0x17877  dup
0x17878  ldc.i4.0
0x17879  ldloc.s  7
0x1787b  box      [mscorlib]System.Int64
0x17880  stelem.ref
0x17881  dup
0x17882  ldc.i4.1
0x17883  ldloc.s  9
0x17885  box      [mscorlib]System.Int64
0x1788a  stelem.ref
0x1788b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17890  ldloc.s  0xA
0x17892  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x17897  stloc.s  0xD
0x17899  ldarg.0
0x1789a  ldarg.1
0x1789b  ldloc.s  4
0x1789d  ldloc.s  5
0x1789f  ldloc.s  5
0x178a1  ldstr    a0_0// "0"
0x178a6  call     string [mscorlib]System.String::Concat(string, string)
0x178ab  ldloc.s  0xC
0x178ad  ldloc.s  0xD
0x178af  ldloc.s  7
0x178b1  ldloc.s  9
0x178b3  ldc.i4.7
0x178b4  call     instance void Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateColumnValues(valuetype [mscorlib]System.Guid importFileId, string parsedTableName, string parsedTableColumnPrefix, string recordIdColumnName, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> outputParsedDataRowList, class [System.Data]System.Data.IDbCommand command, int64 lowerCount, int64 upperCount, int32 importFileStatusCode)
0x178b9  leave.s  loc_178C7
0x178bb  ldloc.s  0xD
0x178bd  brfalse.s loc_178C6
0x178bf  ldloc.s  0xD
0x178c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x178c6  endfinally
0x178c7  ldarg.0
0x178c8  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused()
0x178cd  dup
0x178ce  stloc.0
0x178cf  brfalse.s loc_178D6
0x178d1  ldloc.0
0x178d2  stloc.s  0xE
0x178d4  leave.s  loc_178FF
0x178d6  ldloc.s  7
0x178d8  ldloc.s  6
0x178da  conv.i8
0x178db  add
0x178dc  stloc.s  7
0x178de  ldloc.s  9
0x178e0  ldloc.s  6
0x178e2  conv.i8
0x178e3  add
0x178e4  stloc.s  9
0x178e6  ldloc.s  7
0x178e8  ldloc.s  8
0x178ea  ble      loc_177DE
0x178ef  leave.s  loc_178FD
0x178f1  ldloc.s  0xA
0x178f3  brfalse.s loc_178FC
0x178f5  ldloc.s  0xA
0x178f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x178fc  endfinally
0x178fd  ldloc.0
0x178fe  ret
0x178ff  ldloc.s  0xE
0x17901  ret
```
