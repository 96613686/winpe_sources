# Microsoft.Crm.Asynchronous.SqlTraceManager::CreateTrace

- ea: `0x5c70`
- end: `0x5d36`
- name: `Microsoft.Crm.Asynchronous.SqlTraceManager::CreateTrace`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5e60`

## callees

- `0x5c70`
- `0x5fe0`
- `0x60c0`

## string_xrefs

- `0x5c7d`: `\ndeclare @d datetime\nset @d = DATEADD(n, @Minutes, GETUTCDATE())\nexec sp_trace_create @TraceId output, 0, @TraceFile, @MaxFileSize, @d\n`

## pseudocode

```c

```

## disassembly

```asm
0x5c70  ldarg.0
0x5c71  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.SqlTraceManager::_connection
0x5c76  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x5c7b  stloc.0
0x5c7c  ldloc.0
0x5c7d  ldstr    aDeclareDDateti// "\r\ndeclare @d datetime\r\nset @d = DAT"...
0x5c82  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5c87  ldloc.0
0x5c88  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x5c8d  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5c92  dup
0x5c93  ldstr    aTraceid// "@TraceId"
0x5c98  ldc.i4.8
0x5c99  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c9e  stloc.1
0x5c9f  ldloc.1
0x5ca0  ldc.i4.2
0x5ca1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5ca6  dup
0x5ca7  ldstr    aReturnvalue// "ReturnValue"
0x5cac  ldc.i4.8
0x5cad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cb2  ldc.i4.6
0x5cb3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5cb8  dup
0x5cb9  ldstr    aTracefile// "@TraceFile"
0x5cbe  ldarg.0
0x5cbf  ldfld    string Microsoft.Crm.Asynchronous.SqlTraceManager::_fullTracePathParameter
0x5cc4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cc9  pop
0x5cca  dup
0x5ccb  ldstr    aMaxfilesize// "@MaxFileSize"
0x5cd0  ldarg.0
0x5cd1  ldfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_traceMaxFileSize
0x5cd6  box      [mscorlib]System.Int32
0x5cdb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5ce0  ldc.i4.s 0xC
0x5ce2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_DbType(valuetype [System.Data]System.Data.DbType)
0x5ce7  ldstr    aMinutes// "@Minutes"
0x5cec  ldarg.0
0x5ced  ldfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_traceDurationMinutes
0x5cf2  box      [mscorlib]System.Int32
0x5cf7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5cfc  pop
0x5cfd  ldloc.0
0x5cfe  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x5d03  pop
0x5d04  ldarg.0
0x5d05  ldloc.1
0x5d06  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5d0b  unbox.any [mscorlib]System.Int32
0x5d10  stfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_traceID
0x5d15  ldarg.0
0x5d16  ldloc.0
0x5d17  call     instance void Microsoft.Crm.Asynchronous.SqlTraceManager::SetTraceEvents(class [System.Data]System.Data.IDbCommand command)
0x5d1c  ldarg.0
0x5d1d  ldloc.0
0x5d1e  call     instance void Microsoft.Crm.Asynchronous.SqlTraceManager::SetTraceFilters(class [System.Data]System.Data.IDbCommand command)
0x5d23  leave.s  loc_5D2F
0x5d25  ldloc.0
0x5d26  brfalse.s loc_5D2E
0x5d28  ldloc.0
0x5d29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d2e  endfinally
0x5d2f  ldarg.0
0x5d30  ldfld    int32 Microsoft.Crm.Asynchronous.SqlTraceManager::_traceID
0x5d35  ret
```
