# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CallUpdateProcedure

- ea: `0xed70`
- end: `0xedf0`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CallUpdateProcedure`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc9b0`
- `0xe7b0`
- `0xe930`
- `0xed70`

## pseudocode

```c

```

## disassembly

```asm
0xed70  ldarg.0
0xed71  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xed76  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetBootstrapMainTableUpdateStoredProcName(valuetype [mscorlib]System.Guid)
0xed7b  stloc.0
0xed7c  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupUpdateBatchSize()
0xed81  stloc.1
0xed82  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xed87  stloc.2
0xed88  ldloc.2
0xed89  ldc.i4.4
0xed8a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xed8f  ldloc.2
0xed90  ldloc.0
0xed91  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xed96  ldloc.2
0xed97  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xed9c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xeda1  dup
0xeda2  ldstr    aBatchsize// "@batchSize"
0xeda7  ldloc.1
0xeda8  box      [mscorlib]System.Int32
0xedad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xedb2  pop
0xedb3  ldstr    aOperationtype// "@operationType"
0xedb8  ldarg.1
0xedb9  box      [mscorlib]System.Int32
0xedbe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xedc3  pop
0xedc4  ldarg.0
0xedc5  ldloc.2
0xedc6  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xedcb  stloc.3
0xedcc  ldloc.3
0xedcd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xedd2  bne.un.s loc_EDD9
0xedd4  ldc.i4.0
0xedd5  stloc.s  4
0xedd7  leave.s  loc_EDED
0xedd9  ldloc.3
0xedda  unbox.any [mscorlib]System.Int32
0xeddf  stloc.s  4
0xede1  leave.s  loc_EDED
0xede3  ldloc.2
0xede4  brfalse.s loc_EDEC
0xede6  ldloc.2
0xede7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xedec  endfinally
0xeded  ldloc.s  4
0xedef  ret
```
