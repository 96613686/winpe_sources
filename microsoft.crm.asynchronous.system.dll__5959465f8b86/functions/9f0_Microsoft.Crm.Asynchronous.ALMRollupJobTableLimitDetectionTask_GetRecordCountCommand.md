# Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::GetRecordCountCommand

- ea: `0x9f0`
- end: `0x9fc`
- name: `Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::GetRecordCountCommand`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x910`

## pseudocode

```c

```

## disassembly

```asm
0x9f0  ldstr    aSelectCount1Fr// "SELECT COUNT(1) FROM [dbo].[RollupJobBa"...
0x9f5  ldc.i4.1
0x9f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x9fb  ret
```
