# Microsoft.Crm.Asynchronous.ImportOperationParse::CreateParsedRow

- ea: `0x163d0`
- end: `0x164eb`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::CreateParsedRow`
- size: `283`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x15220`
- `0x15b80`
- `0x15d20`

## callees

- `0x51d0`
- `0x15f30`
- `0x16160`
- `0x163d0`

## pseudocode

```c

```

## disassembly

```asm
0x163d0  ldarg.s  7
0x163d2  brfalse.s loc_163D9
0x163d4  ldarg.s  7
0x163d6  ldlen
0x163d7  brtrue.s loc_1641A
0x163d9  ldarg.0
0x163da  ldarg.s  4
0x163dc  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables(string parsedTableName)
0x163e1  ldarg.0
0x163e2  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x163e7  ldarg.0
0x163e8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x163ed  ldarg.0
0x163ee  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x163f3  ldarg.3
0x163f4  ldarg.1
0x163f5  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x163fa  ldc.i4.0
0x163fb  ldsfld   string [mscorlib]System.String::Empty
0x16400  ldsfld   string [mscorlib]System.String::Empty
0x16405  ldc.i4   0x80040347
0x1640a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1640f  ldsfld   string [mscorlib]System.String::Empty
0x16414  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x16419  ret
0x1641a  ldarg.s  7
0x1641c  ldlen
0x1641d  conv.i4
0x1641e  ldarg.s  6
0x16420  beq.s    loc_16463
0x16422  ldarg.0
0x16423  ldarg.s  4
0x16425  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables(string parsedTableName)
0x1642a  ldarg.0
0x1642b  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x16430  ldarg.0
0x16431  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x16436  ldarg.0
0x16437  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1643c  ldarg.3
0x1643d  ldarg.1
0x1643e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x16443  ldc.i4.0
0x16444  ldsfld   string [mscorlib]System.String::Empty
0x16449  ldsfld   string [mscorlib]System.String::Empty
0x1644e  ldc.i4   0x80040345
0x16453  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x16458  ldsfld   string [mscorlib]System.String::Empty
0x1645d  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x16462  ret
0x16463  ldarg.0
0x16464  ldarg.s  4
0x16466  ldarg.s  5
0x16468  ldarg.2
0x16469  ldarg.1
0x1646a  ldarg.s  7
0x1646c  ldarg.s  8
0x1646e  ldind.i8
0x1646f  ldarg.s  6
0x16471  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationParse::AddParsedRecord(string tableName, string parsedTableColumnPrefix, valuetype [mscorlib]System.Guid recordId, valuetype [mscorlib]System.Guid importDataId, string[] values, int64 rowNumber, int32 parsedTableColumnsNumber)
0x16476  brtrue.s loc_164E1
0x16478  ldarg.0
0x16479  ldarg.s  4
0x1647b  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables(string parsedTableName)
0x16480  ldnull
0x16481  ldarg.0
0x16482  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x16487  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1648c  ldc.i4.s 0x18
0x1648e  ldstr    aErrorInParsing// "Error in parsing row number: {0}."
0x16493  ldc.i4.1
0x16494  newarr   [mscorlib]System.Object
0x16499  dup
0x1649a  ldc.i4.0
0x1649b  ldarg.s  8
0x1649d  ldind.i8
0x1649e  box      [mscorlib]System.Int64
0x164a3  stelem.ref
0x164a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x164a9  ldarg.0
0x164aa  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x164af  ldarg.0
0x164b0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x164b5  ldarg.0
0x164b6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x164bb  ldarg.3
0x164bc  ldarg.1
0x164bd  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x164c2  ldc.i4.0
0x164c3  ldsfld   string [mscorlib]System.String::Empty
0x164c8  ldsfld   string [mscorlib]System.String::Empty
0x164cd  ldc.i4   0x80040372
0x164d2  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x164d7  ldsfld   string [mscorlib]System.String::Empty
0x164dc  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0x164e1  ldarg.s  8
0x164e3  ldarg.s  8
0x164e5  ldind.i8
0x164e6  ldc.i4.1
0x164e7  conv.i8
0x164e8  add
0x164e9  stind.i8
0x164ea  ret
```
