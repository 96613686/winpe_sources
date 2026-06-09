# Microsoft.Crm.Asynchronous.ImportOperationParse::PopulateParseTableForExcel

- ea: `0x14940`
- end: `0x14ac8`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::PopulateParseTableForExcel`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14370`

## callees

- `0x3b80`
- `0x3c60`
- `0x4240`
- `0x14940`
- `0x15d20`
- `0x15f30`

## string_xrefs

- `0x149c7`: `{Import}: Exception while trying to open the database connection {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x14940  ldarg.2
0x14941  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x14946  stloc.0
0x14947  ldc.i4.1
0x14948  conv.i8
0x14949  stloc.1
0x1494a  ldc.i4.1
0x1494b  conv.i8
0x1494c  stloc.2
0x1494d  ldarg.0
0x1494e  ldarg.2
0x1494f  ldstr    aParsedtablecol_0// "parsedtablecolumnsnumber"
0x14954  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14959  unbox.any [mscorlib]System.Int32
0x1495e  newarr   [mscorlib]System.Int32
0x14963  stfld    int32[] Microsoft.Crm.Asynchronous.ImportOperationParse::_parseTableCurrentColumnLength
0x14968  ldc.i4.0
0x14969  stloc.s  4
0x1496b  br.s     loc_14987
0x1496d  ldarg.0
0x1496e  ldfld    int32[] Microsoft.Crm.Asynchronous.ImportOperationParse::_parseTableCurrentColumnLength
0x14973  ldloc.s  4
0x14975  ldarg.0
0x14976  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0x1497b  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_ParsedColumnDefaultSize()
0x14980  stelem.i4
0x14981  ldloc.s  4
0x14983  ldc.i4.1
0x14984  add
0x14985  stloc.s  4
0x14987  ldloc.s  4
0x14989  ldarg.0
0x1498a  ldfld    int32[] Microsoft.Crm.Asynchronous.ImportOperationParse::_parseTableCurrentColumnLength
0x1498f  ldlen
0x14990  conv.i4
0x14991  blt.s    loc_1496D
0x14993  ldarg.2
0x14994  ldstr    aParsedtablenam_0// "parsedtablename"
0x14999  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1499e  stloc.3
0x1499f  ldarg.0
0x149a0  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x149a5  ldarg.0
0x149a6  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x149ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x149b0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection(valuetype [mscorlib]System.Guid organizationId)
0x149b5  stloc.s  5
0x149b7  ldloc.s  5
0x149b9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x149be  leave.s  loc_149ED
0x149c0  stloc.s  6
0x149c2  ldloc.s  6
0x149c4  ldarg.1
0x149c5  ldc.i4.s 0x18
0x149c7  ldstr    aImportExceptio// "{Import}: Exception while trying to ope"...
0x149cc  ldc.i4.2
0x149cd  newarr   [mscorlib]System.Object
0x149d2  dup
0x149d3  ldc.i4.0
0x149d4  ldloc.s  5
0x149d6  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x149db  stelem.ref
0x149dc  dup
0x149dd  ldc.i4.1
0x149de  ldloc.s  6
0x149e0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x149e5  stelem.ref
0x149e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x149eb  rethrow
0x149ed  ldloc.s  5
0x149ef  ldstr    aSelectContentF// "Select Content From ImportFileBase Wher"...
0x149f4  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x149f9  stloc.s  7
0x149fb  ldloc.s  7
0x149fd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x14a02  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x14a07  ldstr    aImportfileid_0// "@importFileId"
0x14a0c  ldloca.s 0
0x14a0e  ldstr    aD_0// "D"
0x14a13  call     instance string [mscorlib]System.Guid::ToString(string)
0x14a18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a1d  pop
0x14a1e  ldloc.s  7
0x14a20  ldc.i4   0x117
0x14a25  ldstr    aPopulateparset// "PopulateParseTableForExcel"
0x14a2a  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x14a2f  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x14a34  stloc.s  8
0x14a36  ldloc.s  8
0x14a38  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x14a3d  brfalse.s loc_14A78
0x14a3f  ldloc.s  8
0x14a41  ldc.i4.0
0x14a42  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x14a47  callvirt instance string [mscorlib]System.Object::ToString()
0x14a4c  stloc.s  9
0x14a4e  ldarg.0
0x14a4f  ldloc.s  9
0x14a51  ldarg.2
0x14a52  ldloca.s 1
0x14a54  ldloc.2
0x14a55  ldarg.1
0x14a56  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::ProcessRowsForExcel(string importExcel, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity importFile, int64& rowNumber, int64 originalDataRowNumber, valuetype [mscorlib]System.Guid organizationId)
0x14a5b  ldarg.0
0x14a5c  ldloc.3
0x14a5d  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushParseTables(string parsedTableName)
0x14a62  ldarg.0
0x14a63  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x14a68  ldloc.0
0x14a69  ldarg.0
0x14a6a  ldfld    string Microsoft.Crm.Asynchronous.ImportOperation::_totalCountField
0x14a6f  ldloc.1
0x14a70  ldc.i4.1
0x14a71  conv.i8
0x14a72  sub
0x14a73  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateImportFileCountField(valuetype [mscorlib]System.Guid importFileId, string countField, int64 count)
0x14a78  leave.s  loc_14AC6
0x14a7a  stloc.s  0xA
0x14a7c  ldloc.s  0xA
0x14a7e  ldarg.1
0x14a7f  ldc.i4.s 0x18
0x14a81  ldstr    aImportExceptio_0// "{Import}: Exception while trying to exe"...
0x14a86  ldc.i4.2
0x14a87  newarr   [mscorlib]System.Object
0x14a8c  dup
0x14a8d  ldc.i4.0
0x14a8e  ldloc.s  7
0x14a90  stelem.ref
0x14a91  dup
0x14a92  ldc.i4.1
0x14a93  ldloc.s  0xA
0x14a95  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x14a9a  stelem.ref
0x14a9b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14aa0  rethrow
0x14aa2  ldloc.s  8
0x14aa4  brfalse.s loc_14AAD
0x14aa6  ldloc.s  8
0x14aa8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14aad  endfinally
0x14aae  ldloc.s  7
0x14ab0  brfalse.s loc_14AB9
0x14ab2  ldloc.s  7
0x14ab4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ab9  endfinally
0x14aba  ldloc.s  5
0x14abc  brfalse.s loc_14AC5
0x14abe  ldloc.s  5
0x14ac0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ac5  endfinally
0x14ac6  ldnull
0x14ac7  ret
```
