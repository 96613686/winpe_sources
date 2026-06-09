# Microsoft.Crm.CrmLive.ConfigDB.SprocBase::ExecuteNonQuery

- ea: `0x47fc0`
- end: `0x48063`
- name: `Microsoft.Crm.CrmLive.ConfigDB.SprocBase::ExecuteNonQuery`
- size: `163`
- prototype: ``
- caller_count: `40`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x45580`
- `0x455b0`
- `0x455e0`
- `0x45610`
- `0x45930`
- `0x45d20`
- `0x45e30`
- `0x45eb0`
- `0x45ff0`
- `0x46070`
- `0x460f0`
- `0x461b0`
- `0x46230`
- `0x46370`
- `0x467e0`
- `0x468a0`
- `0x46ac0`
- `0x46ea0`
- `0x46fa0`
- `0x47180`
- `0x471b0`
- `0x471e0`
- `0x47210`
- `0x47240`
- `0x47270`
- `0x472f0`
- `0x47370`
- `0x474c0`
- `0x474f0`
- `0x47570`
- `0x47630`
- `0x47730`
- `0x47830`
- `0x478b0`
- `0x47970`
- `0x47a30`
- `0x47c10`
- `0x47c90`
- `0x47cc0`
- `0x47cf0`

## callees

- `0xdab0`
- `0x47f60`
- `0x47fc0`
- `0x483e0`
- `0x485a0`

## string_xrefs

- `0x47fec`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\StoredProc\SprocBase.cs`

## pseudocode

```c

```

## disassembly

```asm
0x47fc0  ldarg.0
0x47fc1  ldarg.1
0x47fc2  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x47fc7  callvirt instance class [mscorlib]System.IDisposable Microsoft.Crm.CrmLive.ConfigDB.SprocBase::GetTrace(string trace)
0x47fcc  stloc.0
0x47fcd  ldarg.0
0x47fce  ldfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmLive.ConfigDB.SprocBase::_transaction
0x47fd3  brfalse.s loc_47FE1
0x47fd5  ldarg.1
0x47fd6  ldarg.0
0x47fd7  ldfld    class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmLive.ConfigDB.SprocBase::_transaction
0x47fdc  callvirt instance void [System.Data]System.Data.IDbCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction)
0x47fe1  ldarg.1
0x47fe2  ldc.i4   0x89
0x47fe7  ldstr    aExecutenonquer// "ExecuteNonQuery"
0x47fec  ldstr    aDA1SSrcPlatfor_29// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x47ff1  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x47ff6  stloc.1
0x47ff7  leave.s  loc_48061
0x47ff9  stloc.2
0x47ffa  ldloc.2
0x47ffb  call     class Microsoft.Crm.CrmException Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Sql2CrmException(class [System.Data]System.Data.SqlClient.SqlException e)
0x48000  stloc.3
0x48001  ldloc.3
0x48002  brtrue.s loc_48020
0x48004  ldloc.2
0x48005  ldstr    aSqlErrorRunnin// "SQL error running {0}"
0x4800a  ldc.i4.1
0x4800b  newarr   [mscorlib]System.Object
0x48010  dup
0x48011  ldc.i4.0
0x48012  ldarg.1
0x48013  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x48018  stelem.ref
0x48019  call     void Microsoft.Crm.CrmLive.ConfigDB.SprocBase::TraceError(class [mscorlib]System.Exception exception, string format, object[] parameters)
0x4801e  rethrow
0x48020  ldloc.2
0x48021  ldstr    aStoredProcedur// "Stored procedure exception in {0}"
0x48026  ldc.i4.1
0x48027  newarr   [mscorlib]System.Object
0x4802c  dup
0x4802d  ldc.i4.0
0x4802e  ldarg.1
0x4802f  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x48034  stelem.ref
0x48035  call     void Microsoft.Crm.CrmLive.ConfigDB.SprocBase::TraceError(class [mscorlib]System.Exception exception, string format, object[] parameters)
0x4803a  ldloc.3
0x4803b  throw
0x4803c  ldstr    aNonSqlErrorRun// "Non-SQL error running {0}"
0x48041  ldc.i4.1
0x48042  newarr   [mscorlib]System.Object
0x48047  dup
0x48048  ldc.i4.0
0x48049  ldarg.1
0x4804a  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x4804f  stelem.ref
0x48050  call     void Microsoft.Crm.CrmLive.ConfigDB.SprocBase::TraceError(class [mscorlib]System.Exception exception, string format, object[] parameters)
0x48055  rethrow
0x48057  ldloc.0
0x48058  brfalse.s loc_48060
0x4805a  ldloc.0
0x4805b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48060  endfinally
0x48061  ldloc.1
0x48062  ret
```
