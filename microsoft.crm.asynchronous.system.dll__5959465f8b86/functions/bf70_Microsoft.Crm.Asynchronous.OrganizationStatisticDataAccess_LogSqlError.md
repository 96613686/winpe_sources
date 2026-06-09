# Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::LogSqlError

- ea: `0xbf70`
- end: `0xbfb6`
- name: `Microsoft.Crm.Asynchronous.OrganizationStatisticDataAccess::LogSqlError`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbde0`

## callees

- `0xbf70`

## pseudocode

```c

```

## disassembly

```asm
0xbf70  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0xbf75  stloc.0
0xbf76  ldloc.0
0xbf77  ldstr    aAsyncSystem// "Async.System"
0xbf7c  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0xbf81  ldloc.0
0xbf82  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog)
0xbf87  stloc.1
0xbf88  ldloc.1
0xbf89  ldc.i4.1
0xbf8a  ldc.i4   0xC0004B02
0xbf8f  conv.u8
0xbf90  ldc.i4.1
0xbf91  newarr   [mscorlib]System.Object
0xbf96  dup
0xbf97  ldc.i4.0
0xbf98  ldarg.1
0xbf99  stelem.ref
0xbf9a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xbf9f  leave.s  loc_BFB5
0xbfa1  ldloc.1
0xbfa2  brfalse.s loc_BFAA
0xbfa4  ldloc.1
0xbfa5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbfaa  endfinally
0xbfab  ldloc.0
0xbfac  brfalse.s loc_BFB4
0xbfae  ldloc.0
0xbfaf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbfb4  endfinally
0xbfb5  ret
```
