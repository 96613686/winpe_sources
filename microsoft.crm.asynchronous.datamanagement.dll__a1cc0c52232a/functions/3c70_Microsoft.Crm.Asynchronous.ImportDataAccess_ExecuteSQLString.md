# Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLString

- ea: `0x3c70`
- end: `0x3c95`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLString`
- size: `37`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbce0`
- `0xf190`
- `0xfd90`
- `0x1c5c0`

## callees

- `0x3c70`

## pseudocode

```c

```

## disassembly

```asm
0x3c70  ldarg.1
0x3c71  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3c76  stloc.0
0x3c77  ldarg.0
0x3c78  ldloc.0
0x3c79  ldloca.s 1
0x3c7b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3c81  ldloc.1
0x3c82  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x3c87  pop
0x3c88  leave.s  loc_3C94
0x3c8a  ldloc.0
0x3c8b  brfalse.s loc_3C93
0x3c8d  ldloc.0
0x3c8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c93  endfinally
0x3c94  ret
```
