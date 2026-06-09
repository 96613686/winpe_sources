# Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyPickListTransformationsForUpdate

- ea: `0x1b1e0`
- end: `0x1b369`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyPickListTransformationsForUpdate`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16690`

## callees

- `0x3b80`
- `0x3c60`
- `0x47e0`
- `0x4820`
- `0x5ed0`
- `0x60f0`
- `0x71a0`
- `0x8f40`
- `0x8f70`
- `0xba70`
- `0xbcb0`
- `0x17eb0`
- `0x1b1e0`
- `0x1b370`
- `0x1b7b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b1e0  ldnull
0x1b1e1  stloc.0
0x1b1e2  ldarg.0
0x1b1e3  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1b1e8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x1b1ed  ldarg.1
0x1b1ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x1b1f3  stloc.1
0x1b1f4  ldloc.1
0x1b1f5  callvirt instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateValueMappingsDictionary()
0x1b1fa  ldloc.1
0x1b1fb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1b200  ldstr    aParsedtablenam_0// "parsedtablename"
0x1b205  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1b20a  stloc.2
0x1b20b  ldloc.1
0x1b20c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1b211  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x1b216  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1b21b  stloc.3
0x1b21c  ldarg.0
0x1b21d  ldarg.1
0x1b21e  ldloca.s 4
0x1b220  call     instance string[] Microsoft.Crm.Asynchronous.ImportOperationTransform::GetParsedTableColumnsToBePicklistTransformed(valuetype [mscorlib]System.Guid importFileId, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>& columnNameToArrayIndex)
0x1b225  stloc.s  5
0x1b227  ldloc.s  5
0x1b229  ldlen
0x1b22a  brtrue.s loc_1B22E
0x1b22c  ldnull
0x1b22d  ret
0x1b22e  ldarg.0
0x1b22f  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0x1b234  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_BatchSize()
0x1b239  stloc.s  6
0x1b23b  ldc.i4.1
0x1b23c  conv.i8
0x1b23d  stloc.s  7
0x1b23f  ldarg.0
0x1b240  ldloc.2
0x1b241  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperation::GetTotalNumberOfRecords(string tableName)
0x1b246  conv.i8
0x1b247  stloc.s  8
0x1b249  ldloc.s  6
0x1b24b  conv.i8
0x1b24c  stloc.s  9
0x1b24e  ldarg.0
0x1b24f  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1b254  ldarg.0
0x1b255  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1b25a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1b25f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection(valuetype [mscorlib]System.Guid organizationId)
0x1b264  stloc.s  0xA
0x1b266  ldloc.s  0xA
0x1b268  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1b26d  br       loc_1B34D
0x1b272  ldarg.0
0x1b273  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1b278  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1b27d  ldc.i4.1
0x1b27e  bne.un.s loc_1B2AC
0x1b280  ldarg.0
0x1b281  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1b286  ldloc.2
0x1b287  ldloc.3
0x1b288  ldloc.s  5
0x1b28a  ldarg.0
0x1b28b  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1b290  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1b295  ldc.i4.0
0x1b296  ceq
0x1b298  ldloc.1
0x1b299  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ParseTableColumnNewValueToParseTableColumnOldValueDictionary()
0x1b29e  ldloc.s  7
0x1b2a0  ldloc.s  9
0x1b2a2  ldc.i4.8
0x1b2a3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet(string tableName, string parsedTableColumnPrefix, string[] columnNames, bool addIsExistingRecordCheck, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> parseTableColumnNewValueToParseTableColumnOldValueDictionary, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x1b2a8  stloc.s  0xB
0x1b2aa  br.s     loc_1B2D0
0x1b2ac  ldarg.0
0x1b2ad  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1b2b2  ldloc.2
0x1b2b3  ldloc.3
0x1b2b4  ldloc.s  5
0x1b2b6  ldarg.0
0x1b2b7  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1b2bc  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1b2c1  ldc.i4.0
0x1b2c2  ceq
0x1b2c4  ldloc.s  7
0x1b2c6  ldloc.s  9
0x1b2c8  ldc.i4.8
0x1b2c9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataSet(string tableName, string parsedTableColumnPrefix, string[] columnNames, bool addIsExistingRecordCheck, int64 lowerBound, int64 upperBound, int32 importFileStatusCode)
0x1b2ce  stloc.s  0xB
0x1b2d0  ldloc.s  0xB
0x1b2d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::get_Count()
0x1b2d7  ldc.i4.0
0x1b2d8  bgt.s    loc_1B2EC
0x1b2da  ldloc.s  7
0x1b2dc  ldloc.s  6
0x1b2de  conv.i8
0x1b2df  add
0x1b2e0  stloc.s  7
0x1b2e2  ldloc.s  9
0x1b2e4  ldloc.s  6
0x1b2e6  conv.i8
0x1b2e7  add
0x1b2e8  stloc.s  9
0x1b2ea  br.s     loc_1B34D
0x1b2ec  ldarg.0
0x1b2ed  ldarg.1
0x1b2ee  ldloc.s  0xB
0x1b2f0  ldloc.s  4
0x1b2f2  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> Microsoft.Crm.Asynchronous.ImportOperationTransform::ApplyPicklistTransformationsOnDataSet(valuetype [mscorlib]System.Guid importFileId, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> inputData, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> columnNameToArrayIndex)
0x1b2f7  stloc.s  0xC
0x1b2f9  ldloc.s  0xA
0x1b2fb  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1b300  stloc.s  0xD
0x1b302  ldarg.0
0x1b303  ldarg.1
0x1b304  ldloc.2
0x1b305  ldloc.3
0x1b306  ldloc.3
0x1b307  ldstr    a0_0// "0"
0x1b30c  call     string [mscorlib]System.String::Concat(string, string)
0x1b311  ldloc.s  0xC
0x1b313  ldloc.s  0xD
0x1b315  ldloc.s  7
0x1b317  ldloc.s  9
0x1b319  ldc.i4.s 9
0x1b31b  call     instance void Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateColumnValues(valuetype [mscorlib]System.Guid importFileId, string parsedTableName, string parsedTableColumnPrefix, string recordIdColumnName, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> outputParsedDataRowList, class [System.Data]System.Data.IDbCommand command, int64 lowerCount, int64 upperCount, int32 importFileStatusCode)
0x1b320  leave.s  loc_1B32E
0x1b322  ldloc.s  0xD
0x1b324  brfalse.s loc_1B32D
0x1b326  ldloc.s  0xD
0x1b328  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b32d  endfinally
0x1b32e  ldarg.0
0x1b32f  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused()
0x1b334  dup
0x1b335  stloc.0
0x1b336  brfalse.s loc_1B33D
0x1b338  ldloc.0
0x1b339  stloc.s  0xE
0x1b33b  leave.s  loc_1B366
0x1b33d  ldloc.s  7
0x1b33f  ldloc.s  6
0x1b341  conv.i8
0x1b342  add
0x1b343  stloc.s  7
0x1b345  ldloc.s  9
0x1b347  ldloc.s  6
0x1b349  conv.i8
0x1b34a  add
0x1b34b  stloc.s  9
0x1b34d  ldloc.s  7
0x1b34f  ldloc.s  8
0x1b351  ble      loc_1B272
0x1b356  leave.s  loc_1B364
0x1b358  ldloc.s  0xA
0x1b35a  brfalse.s loc_1B363
0x1b35c  ldloc.s  0xA
0x1b35e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b363  endfinally
0x1b364  ldloc.0
0x1b365  ret
0x1b366  ldloc.s  0xE
0x1b368  ret
```
