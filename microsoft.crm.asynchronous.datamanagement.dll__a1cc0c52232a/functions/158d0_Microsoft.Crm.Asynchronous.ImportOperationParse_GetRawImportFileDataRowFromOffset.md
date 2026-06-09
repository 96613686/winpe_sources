# Microsoft.Crm.Asynchronous.ImportOperationParse::GetRawImportFileDataRowFromOffset

- ea: `0x158d0`
- end: `0x15af2`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::GetRawImportFileDataRowFromOffset`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x156f0`

## callees

- `0x3c60`
- `0x158d0`
- `0x15b00`
- `0x15b40`

## string_xrefs

- `0x1593f`: `{Import}: Exception while trying to open the database connection {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x158d0  ldarg.0
0x158d1  ldarg.s  7
0x158d3  ldind.ref
0x158d4  ldc.i4.0
0x158d5  ldarg.s  4
0x158d7  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperationParse::GetNewLineIndex(string reader, int32 countDelim, string dataDelimiter)
0x158dc  stloc.0
0x158dd  ldloc.0
0x158de  ldc.i4.m1
0x158df  beq.s    loc_15908
0x158e1  ldarg.s  5
0x158e3  ldarg.s  7
0x158e5  ldind.ref
0x158e6  ldc.i4.0
0x158e7  ldloc.0
0x158e8  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x158ed  stind.ref
0x158ee  ldarg.s  6
0x158f0  ldarg.s  6
0x158f2  ldind.i4
0x158f3  ldloc.0
0x158f4  ldc.i4.1
0x158f5  add
0x158f6  add
0x158f7  stind.i4
0x158f8  ldarg.s  7
0x158fa  ldarg.s  7
0x158fc  ldind.ref
0x158fd  ldloc.0
0x158fe  ldc.i4.1
0x158ff  add
0x15900  callvirt instance string [mscorlib]System.String::Substring(int32)
0x15905  stind.ref
0x15906  ldc.i4.1
0x15907  ret
0x15908  ldc.i4.1
0x15909  stloc.1
0x1590a  ldsfld   string [mscorlib]System.String::Empty
0x1590f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x15914  stloc.2
0x15915  ldc.i4.0
0x15916  stloc.3
0x15917  ldarg.0
0x15918  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1591d  ldarg.0
0x1591e  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x15923  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x15928  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection(valuetype [mscorlib]System.Guid organizationId)
0x1592d  stloc.s  4
0x1592f  ldloc.s  4
0x15931  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x15936  leave.s  loc_15965
0x15938  stloc.s  5
0x1593a  ldloc.s  5
0x1593c  ldarg.1
0x1593d  ldc.i4.s 0x18
0x1593f  ldstr    aImportExceptio// "{Import}: Exception while trying to ope"...
0x15944  ldc.i4.2
0x15945  newarr   [mscorlib]System.Object
0x1594a  dup
0x1594b  ldc.i4.0
0x1594c  ldloc.s  4
0x1594e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x15953  stelem.ref
0x15954  dup
0x15955  ldc.i4.1
0x15956  ldloc.s  5
0x15958  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1595d  stelem.ref
0x1595e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15963  rethrow
0x15965  ldloc.s  4
0x15967  ldstr    aSelectSubstrin// "Select SUBSTRING(Content, @startIndex ,"...
0x1596c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x15971  stloc.s  6
0x15973  ldloc.s  6
0x15975  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1597a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1597f  stloc.s  7
0x15981  ldloc.s  7
0x15983  ldstr    aBuffersize// "@bufferSize"
0x15988  ldarg.3
0x15989  box      [mscorlib]System.Int32
0x1598e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15993  pop
0x15994  ldloc.s  7
0x15996  ldstr    aImportfileid_0// "@importFileId"
0x1599b  ldarga.s 2
0x1599d  ldstr    aD_0// "D"
0x159a2  call     instance string [mscorlib]System.Guid::ToString(string)
0x159a7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x159ac  pop
0x159ad  ldloc.s  7
0x159af  ldstr    aStartindex// "@startIndex"
0x159b4  ldarg.s  6
0x159b6  ldind.i4
0x159b7  box      [mscorlib]System.Int32
0x159bc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x159c1  pop
0x159c2  ldloc.s  6
0x159c4  ldc.i4   0x3F5
0x159c9  ldstr    aGetrawimportfi// "GetRawImportFileDataRowFromOffset"
0x159ce  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x159d3  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x159d8  stloc.s  8
0x159da  ldloc.s  8
0x159dc  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x159e1  brfalse  loc_15A92
0x159e6  ldloc.s  8
0x159e8  ldc.i4.0
0x159e9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x159ee  callvirt instance string [mscorlib]System.Object::ToString()
0x159f3  stloc.s  9
0x159f5  ldloc.s  9
0x159f7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x159fc  brtrue.s loc_15A0D
0x159fe  ldloc.2
0x159ff  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x15a04  brtrue.s loc_15A08
0x15a06  ldc.i4.0
0x15a07  stloc.1
0x15a08  leave    loc_15AE7
0x15a0d  ldarg.0
0x15a0e  ldloc.s  9
0x15a10  ldloc.3
0x15a11  ldarg.s  4
0x15a13  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperationParse::GetNewLineIndex(string reader, int32 countDelim, string dataDelimiter)
0x15a18  stloc.0
0x15a19  ldloc.0
0x15a1a  ldc.i4.m1
0x15a1b  beq.s    loc_15A4F
0x15a1d  ldloc.s  9
0x15a1f  ldc.i4.0
0x15a20  ldloc.0
0x15a21  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x15a26  stloc.s  0xA
0x15a28  ldloc.2
0x15a29  ldloc.s  0xA
0x15a2b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a30  pop
0x15a31  ldc.i4.0
0x15a32  stloc.3
0x15a33  ldarg.s  6
0x15a35  ldarg.s  6
0x15a37  ldind.i4
0x15a38  ldloc.0
0x15a39  ldc.i4.1
0x15a3a  add
0x15a3b  add
0x15a3c  stind.i4
0x15a3d  ldarg.s  7
0x15a3f  ldloc.s  9
0x15a41  ldloc.0
0x15a42  ldc.i4.1
0x15a43  add
0x15a44  callvirt instance string [mscorlib]System.String::Substring(int32)
0x15a49  stind.ref
0x15a4a  leave    loc_15AE7
0x15a4f  ldloc.2
0x15a50  ldloc.s  9
0x15a52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a57  pop
0x15a58  ldloc.3
0x15a59  ldarg.0
0x15a5a  ldarg.s  4
0x15a5c  ldloc.s  9
0x15a5e  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperationParse::NumberofOccurances(string Find, string row)
0x15a63  add
0x15a64  stloc.3
0x15a65  ldarg.s  6
0x15a67  ldarg.s  6
0x15a69  ldind.i4
0x15a6a  ldloc.s  9
0x15a6c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15a71  add
0x15a72  stind.i4
0x15a73  ldloc.s  7
0x15a75  ldc.i4.2
0x15a76  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::RemoveAt(int32)
0x15a7b  ldloc.s  7
0x15a7d  ldstr    aStartindex// "@startIndex"
0x15a82  ldarg.s  6
0x15a84  ldind.i4
0x15a85  box      [mscorlib]System.Int32
0x15a8a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15a8f  pop
0x15a90  br.s     loc_15A96
0x15a92  ldc.i4.0
0x15a93  stloc.1
0x15a94  leave.s  loc_15AE7
0x15a96  leave    loc_159C2
0x15a9b  stloc.s  0xB
0x15a9d  ldloc.s  0xB
0x15a9f  ldarg.1
0x15aa0  ldc.i4.s 0x18
0x15aa2  ldstr    aImportExceptio_0// "{Import}: Exception while trying to exe"...
0x15aa7  ldc.i4.2
0x15aa8  newarr   [mscorlib]System.Object
0x15aad  dup
0x15aae  ldc.i4.0
0x15aaf  ldloc.s  6
0x15ab1  stelem.ref
0x15ab2  dup
0x15ab3  ldc.i4.1
0x15ab4  ldloc.s  0xB
0x15ab6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x15abb  stelem.ref
0x15abc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15ac1  rethrow
0x15ac3  ldloc.s  8
0x15ac5  brfalse.s loc_15ACE
0x15ac7  ldloc.s  8
0x15ac9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15ace  endfinally
0x15acf  ldloc.s  6
0x15ad1  brfalse.s loc_15ADA
0x15ad3  ldloc.s  6
0x15ad5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15ada  endfinally
0x15adb  ldloc.s  4
0x15add  brfalse.s loc_15AE6
0x15adf  ldloc.s  4
0x15ae1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15ae6  endfinally
0x15ae7  ldarg.s  5
0x15ae9  ldloc.2
0x15aea  callvirt instance string [mscorlib]System.Object::ToString()
0x15aef  stind.ref
0x15af0  ldloc.1
0x15af1  ret
```
