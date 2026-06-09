# Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::GetRollupFieldInfoCommand

- ea: `0xa00`
- end: `0xa0c`
- name: `Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::GetRollupFieldInfoCommand`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x910`

## string_xrefs

- `0xa00`: `\n			DECLARE @RollupProperties TABLE\n			(\n				RollupPropertiesId uniqueidentifier\n			)\n\n			INSERT INTO @RollupProperties (RollupPropertiesId) SELECT DISTINCT RollupPropertiesId FROM [dbo].[RollupJob] (nolock)\n			\n			SELECT Count(1) FROM @RollupProperties`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldstr    aDeclareRollupp// "\r\n\t\t\tDECLARE @RollupProperties TAB"...
0xa05  ldc.i4.1
0xa06  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0xa0b  ret
```
