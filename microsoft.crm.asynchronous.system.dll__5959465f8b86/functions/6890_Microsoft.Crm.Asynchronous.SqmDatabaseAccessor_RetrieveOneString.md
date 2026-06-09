# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneString

- ea: `0x6890`
- end: `0x68d4`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneString`
- size: `68`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6830`
- `0x6850`
- `0x6870`

## callees

- `0x6890`

## pseudocode

```c

```

## disassembly

```asm
0x6890  ldnull
0x6891  stloc.0
0x6892  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6897  stloc.1
0x6898  ldloc.1
0x6899  ldarg.1
0x689a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x689f  ldloc.1
0x68a0  ldarg.2
0x68a1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x68a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68ab  ldstr    a0// "{0}"
0x68b0  ldc.i4.1
0x68b1  newarr   [mscorlib]System.Object
0x68b6  dup
0x68b7  ldc.i4.0
0x68b8  ldarg.0
0x68b9  ldloc.1
0x68ba  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x68bf  stelem.ref
0x68c0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x68c5  stloc.0
0x68c6  leave.s  loc_68D2
0x68c8  ldloc.1
0x68c9  brfalse.s loc_68D1
0x68cb  ldloc.1
0x68cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68d1  endfinally
0x68d2  ldloc.0
0x68d3  ret
```
