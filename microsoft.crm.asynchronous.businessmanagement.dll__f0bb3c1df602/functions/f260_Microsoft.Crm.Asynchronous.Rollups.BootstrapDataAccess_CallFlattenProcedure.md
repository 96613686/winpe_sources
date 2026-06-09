# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CallFlattenProcedure

- ea: `0xf260`
- end: `0xf2fd`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CallFlattenProcedure`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xc970`
- `0xe7b0`
- `0xe930`
- `0xf260`

## pseudocode

```c

```

## disassembly

```asm
0xf260  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf265  stloc.0
0xf266  ldloc.0
0xf267  ldc.i4.4
0xf268  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xf26d  ldloc.0
0xf26e  ldarg.0
0xf26f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xf274  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetBootstrapFlattenStoredProcName(valuetype [mscorlib]System.Guid)
0xf279  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf27e  ldloc.0
0xf27f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf284  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf289  dup
0xf28a  ldstr    aBatchsize// "@batchSize"
0xf28f  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupBulkBatchSize()
0xf294  box      [mscorlib]System.Int32
0xf299  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf29e  pop
0xf29f  ldstr    aMorerecords// "@moreRecords"
0xf2a4  ldc.i4.8
0xf2a5  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType)
0xf2aa  stloc.1
0xf2ab  ldloc.1
0xf2ac  ldc.i4.2
0xf2ad  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0xf2b2  dup
0xf2b3  ldloc.1
0xf2b4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0xf2b9  pop
0xf2ba  ldstr    aOperationtype// "@operationType"
0xf2bf  ldarg.1
0xf2c0  box      [mscorlib]System.Int32
0xf2c5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf2ca  pop
0xf2cb  ldarg.0
0xf2cc  ldloc.0
0xf2cd  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf2d2  pop
0xf2d3  ldloc.1
0xf2d4  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0xf2d9  isinst   [mscorlib]System.DBNull
0xf2de  brtrue.s loc_F2ED
0xf2e0  ldloc.1
0xf2e1  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0xf2e6  unbox.any [mscorlib]System.Int32
0xf2eb  br.s     loc_F2EE
0xf2ed  ldc.i4.0
0xf2ee  stloc.2
0xf2ef  leave.s  loc_F2FB
0xf2f1  ldloc.0
0xf2f2  brfalse.s loc_F2FA
0xf2f4  ldloc.0
0xf2f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf2fa  endfinally
0xf2fb  ldloc.2
0xf2fc  ret
```
