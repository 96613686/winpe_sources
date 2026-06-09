# Microsoft.Crm.Asynchronous.ImportDataAccess::BulkInsert

- ea: `0x4f20`
- end: `0x51c4`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::BulkInsert`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15f40`
- `0x15f80`

## callees

- `0x4f20`
- `0xaab0`

## string_xrefs

- `0x514a`: `d:\dbs\sh\dccm2\1101_190851\cmd\32\src\Core\ObjectModel\Async\Handlers\DataManagement\ImportDataAccess.cs`
- `0x4f57`: `Exception while trying to open database connection for organization {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4f20  ldarg.0
0x4f21  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::CreateConnection()
0x4f26  stloc.0
0x4f27  ldloc.0
0x4f28  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x4f2d  leave.s  loc_4F74
0x4f2f  stloc.s  4
0x4f31  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4f36  ldstr    aConnectionstri// "ConnectionString: {0}, "
0x4f3b  ldc.i4.1
0x4f3c  newarr   [mscorlib]System.Object
0x4f41  dup
0x4f42  ldc.i4.0
0x4f43  ldloc.0
0x4f44  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x4f49  stelem.ref
0x4f4a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4f4f  stloc.s  5
0x4f51  ldarg.0
0x4f52  ldloc.s  4
0x4f54  ldnull
0x4f55  ldloc.s  5
0x4f57  ldstr    aExceptionWhile// "Exception while trying to open database"...
0x4f5c  call     string [mscorlib]System.String::Concat(string, string)
0x4f61  ldarg.0
0x4f62  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x4f67  ldarg.0
0x4f68  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x4f6d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x4f72  rethrow
0x4f74  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4f79  stloc.1
0x4f7a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4f7f  stloc.2
0x4f80  ldc.i4.0
0x4f81  stloc.3
0x4f82  br.s     loc_4FBE
0x4f84  ldloc.1
0x4f85  ldarg.3
0x4f86  ldloc.3
0x4f87  ldelem.ref
0x4f88  ldstr    asc_24112// ","
0x4f8d  call     string [mscorlib]System.String::Concat(string, string)
0x4f92  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4f97  pop
0x4f98  ldloc.2
0x4f99  ldstr    aColvalue// "@colValue"
0x4f9e  ldloca.s 3
0x4fa0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fa5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4faa  ldstr    asc_24112// ","
0x4faf  call     string [mscorlib]System.String::Concat(string, string, string)
0x4fb4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4fb9  pop
0x4fba  ldloc.3
0x4fbb  ldc.i4.1
0x4fbc  add
0x4fbd  stloc.3
0x4fbe  ldloc.3
0x4fbf  ldarg.3
0x4fc0  ldlen
0x4fc1  conv.i4
0x4fc2  ldc.i4.1
0x4fc3  sub
0x4fc4  blt.s    loc_4F84
0x4fc6  ldloc.1
0x4fc7  ldarg.3
0x4fc8  ldloc.3
0x4fc9  ldelem.ref
0x4fca  ldstr    aValues// ") values ("
0x4fcf  call     string [mscorlib]System.String::Concat(string, string)
0x4fd4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4fd9  pop
0x4fda  ldloc.2
0x4fdb  ldstr    aColvalue// "@colValue"
0x4fe0  ldloca.s 3
0x4fe2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fe7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4fec  ldstr    asc_275CE// ")"
0x4ff1  call     string [mscorlib]System.String::Concat(string, string, string)
0x4ff6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4ffb  pop
0x4ffc  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5001  dup
0x5002  ldstr    aInsertInto// "insert into "
0x5007  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x500c  pop
0x500d  dup
0x500e  ldarg.2
0x500f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5014  pop
0x5015  dup
0x5016  ldstr    asc_275EC// "("
0x501b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5020  pop
0x5021  dup
0x5022  ldloc.1
0x5023  callvirt instance string [mscorlib]System.Object::ToString()
0x5028  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x502d  pop
0x502e  dup
0x502f  ldloc.2
0x5030  callvirt instance string [mscorlib]System.Object::ToString()
0x5035  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x503a  pop
0x503b  callvirt instance string [mscorlib]System.Object::ToString()
0x5040  stloc.s  6
0x5042  ldloc.0
0x5043  ldloc.s  6
0x5045  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x504a  stloc.s  7
0x504c  ldloc.s  7
0x504e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5053  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5058  stloc.s  8
0x505a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::.ctor()
0x505f  stloc.s  9
0x5061  ldarg.1
0x5062  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x5067  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Data]System.Data.InternalDataCollectionBase::GetEnumerator()
0x506c  stloc.s  0xA
0x506e  br       loc_518A
0x5073  ldloc.s  0xA
0x5075  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x507a  castclass [System.Data]System.Data.DataRow
0x507f  stloc.s  0xB
0x5081  ldarg.s  4
0x5083  call     void Microsoft.Crm.Asynchronous.ImportOperation::IncrementPerfCounter(class [System]System.Diagnostics.PerformanceCounter pc)
0x5088  ldloc.s  8
0x508a  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x508f  ldloc.s  9
0x5091  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::ResetParameters()
0x5096  ldc.i4.0
0x5097  stloc.s  0xC
0x5099  br       loc_5123
0x509e  ldstr    aColvalue_0// "colValue"
0x50a3  ldloca.s 0xC
0x50a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50aa  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x50af  call     string [mscorlib]System.String::Concat(string, string)
0x50b4  stloc.s  0xD
0x50b6  ldarg.s  5
0x50b8  brfalse.s loc_5102
0x50ba  ldloc.s  0xB
0x50bc  ldarg.3
0x50bd  ldloc.s  0xC
0x50bf  ldelem.ref
0x50c0  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x50c5  isinst   [mscorlib]System.String
0x50ca  brfalse.s loc_5102
0x50cc  ldloc.s  0xB
0x50ce  ldarg.3
0x50cf  ldloc.s  0xC
0x50d1  ldelem.ref
0x50d2  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x50d7  callvirt instance string [mscorlib]System.Object::ToString()
0x50dc  stloc.s  0xE
0x50de  ldloc.s  9
0x50e0  ldloc.s  0xD
0x50e2  ldloc.s  0xE
0x50e4  ldc.i4   0xFA0
0x50e9  ldloc.s  0xE
0x50eb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x50f0  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x50f5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, int32)
0x50fa  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithExactName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x50ff  pop
0x5100  br.s     loc_511D
0x5102  ldloc.s  9
0x5104  ldloc.s  0xD
0x5106  ldloc.s  0xB
0x5108  ldarg.3
0x5109  ldloc.s  0xC
0x510b  ldelem.ref
0x510c  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x5111  ldc.i4.0
0x5112  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, bool)
0x5117  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithExactName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x511c  pop
0x511d  ldloc.s  0xC
0x511f  ldc.i4.1
0x5120  add
0x5121  stloc.s  0xC
0x5123  ldloc.s  0xC
0x5125  ldarg.1
0x5126  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x512b  callvirt instance int32 [System.Data]System.Data.InternalDataCollectionBase::get_Count()
0x5130  blt      loc_509E
0x5135  ldloc.s  9
0x5137  ldloc.s  8
0x5139  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParametersToSqlParameterCollection(class [System.Data]System.Data.SqlClient.SqlParameterCollection)
0x513e  ldloc.s  7
0x5140  ldc.i4   0x43B
0x5145  ldstr    aBulkinsert// "BulkInsert"
0x514a  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x514f  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x5154  pop
0x5155  leave.s  loc_518A
0x5157  stloc.s  0xF
0x5159  ldstr    aBulkinserterro// "BulkInsertError: "
0x515e  stloc.s  0x10
0x5160  ldarg.0
0x5161  ldloc.s  0xF
0x5163  ldnull
0x5164  ldloc.s  0x10
0x5166  ldstr    aExceptionWhile_0// "Exception while executing database quer"...
0x516b  call     string [mscorlib]System.String::Concat(string, string)
0x5170  ldloc.0
0x5171  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0x5176  ldarg.0
0x5177  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x517c  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0x5181  ldloc.s  7
0x5183  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5188  rethrow
0x518a  ldloc.s  0xA
0x518c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5191  brtrue   loc_5073
0x5196  leave.s  loc_51C3
0x5198  ldloc.s  0xA
0x519a  isinst   [mscorlib]System.IDisposable
0x519f  stloc.s  0x11
0x51a1  ldloc.s  0x11
0x51a3  brfalse.s loc_51AC
0x51a5  ldloc.s  0x11
0x51a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51ac  endfinally
0x51ad  ldloc.s  7
0x51af  brfalse.s loc_51B8
0x51b1  ldloc.s  7
0x51b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51b8  endfinally
0x51b9  ldloc.0
0x51ba  brfalse.s loc_51C2
0x51bc  ldloc.0
0x51bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51c2  endfinally
0x51c3  ret
```
