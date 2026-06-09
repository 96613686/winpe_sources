# Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow_0

- ea: `0x51f0`
- end: `0x5570`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow_0`
- size: `896`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x51d0`
- `0xe130`
- `0xea10`
- `0xf190`
- `0x10ec0`
- `0x11690`
- `0x12610`
- `0x12780`
- `0x128c0`
- `0x12e20`
- `0x13030`
- `0x13300`
- `0x133e0`
- `0x13670`

## callees

- `0x42b0`
- `0x51f0`

## string_xrefs

- `0x5295`: `INSERT INTO ImportLogBase(ImportLogId, ModifiedOn, OwnerId, OwningBusinessUnit, CreatedBy, StatusCode, ModifiedBy, StateCode, CreatedOn, \nImportFileId, ImportDataId, LineNumber, LogPhaseCode, HeaderColumn, ColumnValue, ErrorNumber, AdditionalInfo, SequenceNumber)\nVALUES\n(NEWID(), @modifiedOn, @OwnerId, @OwningBusinessUnit, @CreatedBy, @StatusCode, @ModifiedBy, @StateCode, GETUTCDATE(), \n@ImportFileId, @ImportDataId, @LineNumber, @LogPhaseCode, @HeaderColumn, @ColumnValue, @ErrorNumber, @`
- `0x52d5`: `@CreatedBy`
- `0x54ba`: `UPDATE ImportDataBase SET HasError = @value, ErrorType=@errortype WHERE ImportDataId = @importdataid and HasError != @value`

## pseudocode

```c

```

## disassembly

```asm
0x51f0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x51f5  stloc.0
0x51f6  ldc.i4.0
0x51f7  conv.i8
0x51f8  stloc.1
0x51f9  ldc.i4.m1
0x51fa  conv.i8
0x51fb  stloc.2
0x51fc  ldarga.s 4
0x51fe  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5203  brfalse.s loc_5244
0x5205  ldloc.0
0x5206  ldstr    aSelectLinenumb// "SELECT LineNumber FROM ImportDataBase W"...
0x520b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5210  ldloc.0
0x5211  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5216  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x521b  ldstr    aImportdataid_1// "@ImportDataId"
0x5220  ldarg.s  4
0x5222  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x5227  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x522c  pop
0x522d  ldarg.0
0x522e  ldloc.0
0x522f  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x5234  callvirt instance string [mscorlib]System.Object::ToString()
0x5239  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x523e  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x5243  stloc.2
0x5244  ldloc.0
0x5245  ldstr    aSelectMaxSeque// "SELECT max(SequenceNumber) FROM ImportL"...
0x524a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x524f  ldloc.0
0x5250  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5255  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x525a  ldstr    aImportfileid_0// "@importFileId"
0x525f  ldarg.3
0x5260  box      [mscorlib]System.Guid
0x5265  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x526a  pop
0x526b  ldarg.0
0x526c  ldloc.0
0x526d  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x5272  stloc.3
0x5273  ldloc.3
0x5274  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5279  beq.s    loc_528C
0x527b  ldloc.3
0x527c  callvirt instance string [mscorlib]System.Object::ToString()
0x5281  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5286  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x528b  stloc.1
0x528c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x5291  stloc.s  4
0x5293  ldloc.s  4
0x5295  ldstr    aInsertIntoImpo// "INSERT INTO ImportLogBase(ImportLogId, "...
0x529a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x529f  ldloc.s  4
0x52a1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x52a6  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x52ab  stloc.s  5
0x52ad  ldloc.s  5
0x52af  ldstr    aOwnerid_0// "@OwnerId"
0x52b4  ldarg.1
0x52b5  box      [mscorlib]System.Guid
0x52ba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52bf  pop
0x52c0  ldloc.s  5
0x52c2  ldstr    aOwningbusiness_0// "@OwningBusinessUnit"
0x52c7  ldarg.2
0x52c8  box      [mscorlib]System.Guid
0x52cd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52d2  pop
0x52d3  ldloc.s  5
0x52d5  ldstr    aCreatedby_0// "@CreatedBy"
0x52da  ldarg.1
0x52db  box      [mscorlib]System.Guid
0x52e0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52e5  pop
0x52e6  ldloc.s  5
0x52e8  ldstr    aStatuscode_1// "@StatusCode"
0x52ed  ldc.i4.0
0x52ee  box      [mscorlib]System.Int32
0x52f3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52f8  pop
0x52f9  ldloc.s  5
0x52fb  ldstr    aModifiedby_0// "@ModifiedBy"
0x5300  ldarg.1
0x5301  box      [mscorlib]System.Guid
0x5306  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x530b  pop
0x530c  ldloc.s  5
0x530e  ldstr    aStatecode_1// "@StateCode"
0x5313  ldc.i4.0
0x5314  box      [mscorlib]System.Int32
0x5319  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x531e  pop
0x531f  ldloc.s  5
0x5321  ldstr    aImportfileid_1// "@ImportFileId"
0x5326  ldarg.3
0x5327  box      [mscorlib]System.Guid
0x532c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5331  pop
0x5332  ldloc.s  5
0x5334  ldstr    aLogphasecode// "@LogPhaseCode"
0x5339  ldarg.s  5
0x533b  box      [mscorlib]System.Int32
0x5340  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5345  pop
0x5346  ldloc.s  5
0x5348  ldstr    aModifiedon// "@modifiedOn"
0x534d  ldarg.0
0x534e  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x5353  box      [mscorlib]System.DateTime
0x5358  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x535d  pop
0x535e  ldarg.s  6
0x5360  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5365  brfalse.s loc_537B
0x5367  ldloc.s  5
0x5369  ldstr    aHeadercolumn// "@HeaderColumn"
0x536e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5373  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5378  pop
0x5379  br.s     loc_538A
0x537b  ldloc.s  5
0x537d  ldstr    aHeadercolumn// "@HeaderColumn"
0x5382  ldarg.s  6
0x5384  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5389  pop
0x538a  ldarg.s  7
0x538c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5391  brfalse.s loc_53A7
0x5393  ldloc.s  5
0x5395  ldstr    aColumnvalue// "@ColumnValue"
0x539a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x539f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x53a4  pop
0x53a5  br.s     loc_53B6
0x53a7  ldloc.s  5
0x53a9  ldstr    aColumnvalue// "@ColumnValue"
0x53ae  ldarg.s  7
0x53b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x53b5  pop
0x53b6  ldarg.s  9
0x53b8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x53bd  brfalse.s loc_53D3
0x53bf  ldloc.s  5
0x53c1  ldstr    aAdditionalinfo// "@AdditionalInfo"
0x53c6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x53cb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x53d0  pop
0x53d1  br.s     loc_53E2
0x53d3  ldloc.s  5
0x53d5  ldstr    aAdditionalinfo// "@AdditionalInfo"
0x53da  ldarg.s  9
0x53dc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x53e1  pop
0x53e2  ldloc.s  5
0x53e4  ldstr    aSequencenumber// "@SequenceNumber"
0x53e9  ldloc.1
0x53ea  ldc.i4.1
0x53eb  conv.i8
0x53ec  add
0x53ed  dup
0x53ee  stloc.1
0x53ef  box      [mscorlib]System.Int64
0x53f4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x53f9  pop
0x53fa  ldloc.2
0x53fb  ldc.i4.m1
0x53fc  conv.i8
0x53fd  beq.s    loc_5414
0x53ff  ldloc.s  5
0x5401  ldstr    aLinenumber// "@LineNumber"
0x5406  ldloc.2
0x5407  box      [mscorlib]System.Int64
0x540c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5411  pop
0x5412  br.s     loc_5426
0x5414  ldloc.s  5
0x5416  ldstr    aLinenumber// "@LineNumber"
0x541b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5420  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5425  pop
0x5426  ldarga.s 4
0x5428  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x542d  brfalse.s loc_5445
0x542f  ldloc.s  5
0x5431  ldstr    aImportdataid_1// "@ImportDataId"
0x5436  ldarg.s  4
0x5438  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x543d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5442  pop
0x5443  br.s     loc_5457
0x5445  ldloc.s  5
0x5447  ldstr    aImportdataid_1// "@ImportDataId"
0x544c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5451  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5456  pop
0x5457  ldarga.s 8
0x5459  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x545e  brfalse.s loc_5476
0x5460  ldloc.s  5
0x5462  ldstr    aErrornumber// "@ErrorNumber"
0x5467  ldarg.s  8
0x5469  box      valuetype [mscorlib]System.Nullable`1<int32>
0x546e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5473  pop
0x5474  br.s     loc_5488
0x5476  ldloc.s  5
0x5478  ldstr    aErrornumber// "@ErrorNumber"
0x547d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5482  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5487  pop
0x5488  ldarg.0
0x5489  ldloc.s  4
0x548b  ldloca.s 6
0x548d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x5493  ldloc.s  6
0x5495  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x549a  pop
0x549b  leave.s  loc_54A9
0x549d  ldloc.s  4
0x549f  brfalse.s loc_54A8
0x54a1  ldloc.s  4
0x54a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54a8  endfinally
0x54a9  ldarga.s 4
0x54ab  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x54b0  brfalse  loc_5563
0x54b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x54ba  ldstr    aUpdateImportda_0// "UPDATE ImportDataBase SET HasError = @v"...
0x54bf  ldc.i4.0
0x54c0  newarr   [mscorlib]System.Object
0x54c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x54ca  ldc.i4.0
0x54cb  stloc.s  7
0x54cd  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x54d2  stloc.s  8
0x54d4  ldloc.s  8
0x54d6  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x54db  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x54e0  dup
0x54e1  ldstr    aValue// "@value"
0x54e6  ldc.i4.1
0x54e7  box      [mscorlib]System.Boolean
0x54ec  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x54f1  pop
0x54f2  dup
0x54f3  ldstr    aImportdataid// "@importdataid"
0x54f8  ldarga.s 4
0x54fa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x54ff  box      [mscorlib]System.Guid
0x5504  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5509  pop
0x550a  ldstr    aErrortype// "@errortype"
0x550f  ldarg.s  0xA
0x5511  box      [mscorlib]System.Int32
0x5516  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x551b  pop
0x551c  ldarg.0
0x551d  ldloc.s  8
0x551f  ldloca.s 6
0x5521  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x5527  ldloc.s  6
0x5529  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x552e  stloc.s  7
0x5530  leave.s  loc_553E
0x5532  ldloc.s  8
0x5534  brfalse.s loc_553D
0x5536  ldloc.s  8
0x5538  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x553d  endfinally
0x553e  ldloc.s  7
0x5540  ldc.i4.0
0x5541  ble.s    loc_5563
0x5543  ldarg.s  0xA
0x5545  brtrue.s loc_5556
0x5547  ldarg.0
0x5548  ldarg.3
0x5549  ldstr    aFailurecount// "FailureCount"
0x554e  ldc.i4.1
0x554f  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::IncrementImportFileCountField(valuetype [mscorlib]System.Guid importFileId, string countField, int32 incrementValue)
0x5554  leave.s  loc_556F
0x5556  ldarg.0
0x5557  ldarg.3
0x5558  ldstr    aPartialfailure// "PartialFailureCount"
0x555d  ldc.i4.1
0x555e  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::IncrementImportFileCountField(valuetype [mscorlib]System.Guid importFileId, string countField, int32 incrementValue)
0x5563  leave.s  loc_556F
0x5565  ldloc.0
0x5566  brfalse.s loc_556E
0x5568  ldloc.0
0x5569  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x556e  endfinally
0x556f  ret
```
