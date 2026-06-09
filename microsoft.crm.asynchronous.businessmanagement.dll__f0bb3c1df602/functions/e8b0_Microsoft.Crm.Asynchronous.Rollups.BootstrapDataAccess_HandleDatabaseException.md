# Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::HandleDatabaseException

- ea: `0xe8b0`
- end: `0xe921`
- name: `Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::HandleDatabaseException`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0xe8b0`
- `0xe930`

## string_xrefs

- `0xe8d9`: `IF @@TRANCOUNT > 0 BEGIN ; ROLLBACK ;  END`
- `0xe902`: `Command for transaction rollback failed. \nOriginal exception before rollback started: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe8b0  ldarg.0
0xe8b1  ldarg.1
0xe8b2  ldarg.2
0xe8b3  ldarg.3
0xe8b4  ldarg.s  4
0xe8b6  ldarg.s  5
0xe8b8  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [mscorlib]System.Guid, string)
0xe8bd  ldarg.0
0xe8be  ldfld    bool Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::isTransactionRollback
0xe8c3  brfalse.s loc_E8C6
0xe8c5  ret
0xe8c6  nop
0xe8c7  ldarg.0
0xe8c8  ldc.i4.1
0xe8c9  stfld    bool Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::isTransactionRollback
0xe8ce  ldarg.2
0xe8cf  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0xe8d4  castclass [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection
0xe8d9  ldstr    aIfTrancount0Be// "IF @@TRANCOUNT > 0 BEGIN ; ROLLBACK ;  "...
0xe8de  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xe8e3  stloc.0
0xe8e4  ldarg.0
0xe8e5  ldloc.0
0xe8e6  call     instance object Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand command)
0xe8eb  pop
0xe8ec  leave.s  loc_E8F8
0xe8ee  ldloc.0
0xe8ef  brfalse.s loc_E8F7
0xe8f1  ldloc.0
0xe8f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe8f7  endfinally
0xe8f8  leave.s  loc_E920
0xe8fa  ldarg.0
0xe8fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0xe900  ldc.i4.s 0x15
0xe902  ldstr    aCommandForTran// "Command for transaction rollback failed"...
0xe907  ldc.i4.1
0xe908  newarr   [mscorlib]System.Object
0xe90d  dup
0xe90e  ldc.i4.0
0xe90f  ldarg.1
0xe910  stelem.ref
0xe911  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe916  leave.s  loc_E920
0xe918  ldarg.0
0xe919  ldc.i4.0
0xe91a  stfld    bool Microsoft.Crm.Asynchronous.Rollups.BootstrapDataAccess::isTransactionRollback
0xe91f  endfinally
0xe920  ret
```
