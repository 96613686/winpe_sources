# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping

- ea: `0x8050`
- end: `0x807e`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping`
- size: `46`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6e20`
- `0x7340`
- `0x73d0`
- `0x7c10`

## callees

- `0x8050`
- `0x8080`

## pseudocode

```c

```

## disassembly

```asm
0x8050  ldarg.1
0x8051  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x8056  stloc.0
0x8057  ldarg.1
0x8058  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x805d  stloc.1
0x805e  ldarg.0
0x805f  ldloc.0
0x8060  ldloc.1
0x8061  ldarg.2
0x8062  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::UpdateSyncIdMapping(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, class SyncData syncData)
0x8067  leave.s  loc_807D
0x8069  ldloc.1
0x806a  brfalse.s loc_8072
0x806c  ldloc.1
0x806d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8072  endfinally
0x8073  ldloc.0
0x8074  brfalse.s loc_807C
0x8076  ldloc.0
0x8077  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x807c  endfinally
0x807d  ret
```
