# Microsoft.Crm.CrmDbConnection::ExecuteReader_1

- ea: `0xdb40`
- end: `0xdb70`
- name: `Microsoft.Crm.CrmDbConnection::ExecuteReader_1`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x11ee0`

## callees

- `0xdb40`
- `0xdf00`
- `0x352e0`

## string_xrefs

- `0xdb57`: `D:\a\1\s\src\Platform\Core\DataServices\Connection\CrmDbConnection.cs`
- `0xdb52`: `ExecuteReader`

## pseudocode

```c

```

## disassembly

```asm
0xdb40  newobj   instance void Microsoft.Crm.AutoReimpersonator::.ctor()
0xdb45  stloc.0
0xdb46  ldarg.0
0xdb47  ldarg.1
0xdb48  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandBehavior>::.ctor(var<u1>)
0xdb4d  ldc.i4   0x2D6
0xdb52  ldstr    aExecutereader// "ExecuteReader"
0xdb57  ldstr    aDA1SSrcPlatfor_3// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xdb5c  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.CrmDbConnection::InternalExecuteReader(class [System.Data]System.Data.IDbCommand command, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandBehavior> commandBehavior, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xdb61  stloc.1
0xdb62  leave.s  loc_DB6E
0xdb64  ldloc.0
0xdb65  brfalse.s loc_DB6D
0xdb67  ldloc.0
0xdb68  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb6d  endfinally
0xdb6e  ldloc.1
0xdb6f  ret
```
