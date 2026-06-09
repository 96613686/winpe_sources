# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript_0

- ea: `0xf6e0`
- end: `0xf702`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlScript_0`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf6d0`

## callees

- `0xe930`
- `0xf6e0`

## pseudocode

```c

```

## disassembly

```asm
0xf6e0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xf6e5  stloc.0
0xf6e6  ldloc.0
0xf6e7  ldarg.1
0xf6e8  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xf6ed  ldarg.0
0xf6ee  ldloc.0
0xf6ef  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xf6f4  pop
0xf6f5  leave.s  loc_F701
0xf6f7  ldloc.0
0xf6f8  brfalse.s loc_F700
0xf6fa  ldloc.0
0xf6fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf700  endfinally
0xf701  ret
```
