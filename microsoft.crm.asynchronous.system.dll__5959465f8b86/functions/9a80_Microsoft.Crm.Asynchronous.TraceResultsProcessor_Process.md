# Microsoft.Crm.Asynchronous.TraceResultsProcessor::Process

- ea: `0x9a80`
- end: `0x9ae4`
- name: `Microsoft.Crm.Asynchronous.TraceResultsProcessor::Process`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1f60`

## callees

- `0x9a80`
- `0x9af0`

## string_xrefs

- `0x9a81`: `traceWriter`

## pseudocode

```c

```

## disassembly

```asm
0x9a80  ldarg.1
0x9a81  ldstr    aTracewriter// "traceWriter"
0x9a86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9a8b  ldarg.0
0x9a8c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.TraceResultsProcessor::_connection
0x9a91  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x9a96  stloc.0
0x9a97  ldloc.0
0x9a98  ldstr    aSelectTextdata// "select TextData, EventClass from ::fn_t"...
0x9a9d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x9aa2  ldloc.0
0x9aa3  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x9aa8  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x9aad  ldstr    aTracefile// "@TraceFile"
0x9ab2  ldarg.0
0x9ab3  ldfld    string Microsoft.Crm.Asynchronous.TraceResultsProcessor::_fullTracePath
0x9ab8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9abd  pop
0x9abe  ldloc.0
0x9abf  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x9ac4  stloc.1
0x9ac5  ldarg.0
0x9ac6  ldloc.1
0x9ac7  ldarg.1
0x9ac8  call     instance void Microsoft.Crm.Asynchronous.TraceResultsProcessor::Process(class [System.Data]System.Data.IDataReader rdr, class Microsoft.Crm.Asynchronous.ISqlTraceWriter traceWriter)
0x9acd  leave.s  loc_9AE3
0x9acf  ldloc.1
0x9ad0  brfalse.s loc_9AD8
0x9ad2  ldloc.1
0x9ad3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9ad8  endfinally
0x9ad9  ldloc.0
0x9ada  brfalse.s loc_9AE2
0x9adc  ldloc.0
0x9add  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9ae2  endfinally
0x9ae3  ret
```
