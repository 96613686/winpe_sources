# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForOutputClause

- ea: `0xd660`
- end: `0xd66f`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForOutputClause`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xd5a0`

## callees

- `0xd660`

## string_xrefs

- `0xd669`: `OUTPUT \n	[INSERTED].[RollupJobId],\n	[INSERTED].[RollupPropertiesId],\n	[INSERTED].[RegardingObjectId],\n	[INSERTED].[RegardingObjectTypeCode],\n	[INSERTED].[SourceEntityTypeCode],\n	[INSERTED].[PostponeUntil],\n	[INSERTED].[RetryCount],\n	[INSERTED].[DepthProcessed],\n	[INSERTED].[RecordCreatedOn]\n`

## pseudocode

```c

```

## disassembly

```asm
0xd660  ldarg.1
0xd661  brtrue.s loc_D669
0xd663  ldsfld   string [mscorlib]System.String::Empty
0xd668  ret
0xd669  ldstr    aOutputInserted// "OUTPUT \r\n\t[INSERTED].[RollupJobId],"...
0xd66e  ret
```
