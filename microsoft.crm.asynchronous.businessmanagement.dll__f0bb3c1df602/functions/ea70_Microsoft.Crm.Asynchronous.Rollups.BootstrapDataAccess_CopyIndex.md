# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CopyIndex

- ea: `0xea70`
- end: `0xeae3`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::CopyIndex`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xe7b0`
- `0xe930`
- `0xea70`

## string_xrefs

- `0xeaad`: `@copyType`

## pseudocode

```c

```

## disassembly

```asm
0xea70  ldarg.0
0xea71  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::get_RollupPropertiesId()
0xea76  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetBootstrapIndexCopyStoredProcName(valuetype [mscorlib]System.Guid)
0xea7b  stloc.0
0xea7c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xea81  stloc.1
0xea82  ldloc.1
0xea83  ldc.i4.4
0xea84  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0xea89  ldloc.1
0xea8a  ldloc.0
0xea8b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xea90  ldloc.1
0xea91  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xea96  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xea9b  dup
0xea9c  ldstr    aBatchsize// "@batchSize"
0xeaa1  ldarg.1
0xeaa2  box      [mscorlib]System.Int32
0xeaa7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xeaac  pop
0xeaad  ldstr    aCopytype// "@copyType"
0xeab2  ldarg.2
0xeab3  box      [mscorlib]System.Int32
0xeab8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xeabd  pop
0xeabe  ldarg.0
0xeabf  ldloc.1
0xeac0  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xeac5  dup
0xeac6  brtrue.s loc_EACF
0xeac8  pop
0xeac9  ldc.i4.0
0xeaca  box      [mscorlib]System.Int32
0xeacf  unbox.any [mscorlib]System.Int32
0xead4  stloc.2
0xead5  leave.s  loc_EAE1
0xead7  ldloc.1
0xead8  brfalse.s loc_EAE0
0xeada  ldloc.1
0xeadb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeae0  endfinally
0xeae1  ldloc.2
0xeae2  ret
```
