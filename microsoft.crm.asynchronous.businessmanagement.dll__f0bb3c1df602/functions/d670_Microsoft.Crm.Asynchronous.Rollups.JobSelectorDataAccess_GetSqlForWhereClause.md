# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForWhereClause

- ea: `0xd670`
- end: `0xd6ae`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::GetSqlForWhereClause`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xd320`
- `0xd410`
- `0xd5a0`

## callees

- `0xd670`

## string_xrefs

- `0xd680`: `WHERE\n[SourceEntityTypeCode] = @sourceEntityTypeCode\nAND [StateCode] = @initialStateCode\nAND [RetryCount] <= @maxRetryCount\nAND EXISTS(\n			SELECT \n				NULL \n			FROM \n				[RollupPropertiesBase] RP \n			WHERE \n				RP.RollupPropertiesId = RJ.RollupPropertiesId \n				AND RP.StateCode = @activeStateCode \n				AND RP.StatusCode = @activeStatusCode \n				AND RP.InitialValueCalculationStatus = @bootstrapCompleted\n			)\n`
- `0xd687`: `WHERE\n[SourceEntityTypeCode] = @sourceEntityTypeCode\nAND [StateCode] = @initialStateCode \nAND [RetryCount] <= @maxRetryCount\nAND [RollupPropertiesId] = @rollupPropertiesId\n`

## pseudocode

```c

```

## disassembly

```asm
0xd670  ldarg.0
0xd671  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupPropertiesId
0xd676  stloc.1
0xd677  ldloca.s 1
0xd679  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xd67e  brtrue.s loc_D687
0xd680  ldstr    aWhereSourceent// "WHERE\r\n[SourceEntityTypeCode] = @sour"...
0xd685  br.s     loc_D68C
0xd687  ldstr    aWhereSourceent_0// "WHERE\r\n[SourceEntityTypeCode] = @sour"...
0xd68c  stloc.0
0xd68d  ldarg.1
0xd68e  brfalse.s loc_D696
0xd690  ldarg.1
0xd691  ldc.i4.1
0xd692  beq.s    loc_D6A2
0xd694  br.s     loc_D6A2
0xd696  ldloc.0
0xd697  ldstr    aAndPostponeunt// " AND [PostponeUntil] IS NOT NULL "
0xd69c  call     string [mscorlib]System.String::Concat(string, string)
0xd6a1  ret
0xd6a2  ldloc.0
0xd6a3  ldstr    aAndPostponeunt_0// " AND ([PostponeUntil] IS NULL OR [Postp"...
0xd6a8  call     string [mscorlib]System.String::Concat(string, string)
0xd6ad  ret
```
