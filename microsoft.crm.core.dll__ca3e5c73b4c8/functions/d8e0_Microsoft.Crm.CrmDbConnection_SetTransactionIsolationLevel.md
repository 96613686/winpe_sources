# Microsoft.Crm.CrmDbConnection::SetTransactionIsolationLevel

- ea: `0xd8e0`
- end: `0xd95a`
- name: `Microsoft.Crm.CrmDbConnection::SetTransactionIsolationLevel`
- size: `122`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xd410`
- `0x103e0`
- `0x10510`
- `0x105b0`

## callees

- `0xd110`
- `0xd620`
- `0xd8e0`
- `0xdab0`
- `0x1b9b0`

## string_xrefs

- `0xd8f0`: `CrmDbConnection.SetTransactionIsolationLevel is only supported for ReadCommitted and Snapshot`
- `0xd912`: `SET TRANSACTION ISOLATION LEVEL READ COMMITTED`
- `0xd93b`: `D:\a\1\s\src\Platform\Core\DataServices\Connection\CrmDbConnection.cs`

## pseudocode

```c

```

## disassembly

```asm
0xd8e0  ldarg.1
0xd8e1  ldc.i4   0x1000
0xd8e6  beq.s    loc_D8FB
0xd8e8  ldarg.1
0xd8e9  ldc.i4   0x1000000
0xd8ee  beq.s    loc_D8FB
0xd8f0  ldstr    aCrmdbconnectio_0// "CrmDbConnection.SetTransactionIsolation"...
0xd8f5  newobj   instance void Microsoft.Crm.CrmNotSupportedException::.ctor(string objectName)
0xd8fa  throw
0xd8fb  ldarg.0
0xd8fc  call     instance valuetype [System.Data]System.Data.ConnectionState Microsoft.Crm.CrmDbConnection::get_State()
0xd901  ldc.i4.1
0xd902  bne.un.s loc_D959
0xd904  ldsfld   string [mscorlib]System.String::Empty
0xd909  stloc.0
0xd90a  ldarg.1
0xd90b  ldc.i4   0x1000
0xd910  bne.un.s loc_D91A
0xd912  ldstr    aSetTransaction// "SET TRANSACTION ISOLATION LEVEL READ CO"...
0xd917  stloc.0
0xd918  br.s     loc_D928
0xd91a  ldarg.1
0xd91b  ldc.i4   0x1000000
0xd920  bne.un.s loc_D928
0xd922  ldstr    aSetTransaction_0// "SET TRANSACTION ISOLATION LEVEL SNAPSHO"...
0xd927  stloc.0
0xd928  ldarg.0
0xd929  ldloc.0
0xd92a  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0xd92f  stloc.1
0xd930  ldloc.1
0xd931  ldc.i4   0x24A
0xd936  ldstr    aSettransaction// "SetTransactionIsolationLevel"
0xd93b  ldstr    aDA1SSrcPlatfor_3// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xd940  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xd945  pop
0xd946  leave.s  loc_D952
0xd948  ldloc.1
0xd949  brfalse.s loc_D951
0xd94b  ldloc.1
0xd94c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd951  endfinally
0xd952  ldarg.0
0xd953  ldarg.1
0xd954  stfld    valuetype [System.Data]System.Data.IsolationLevel Microsoft.Crm.CrmDbConnection::_isolationLevel
0xd959  ret
```
