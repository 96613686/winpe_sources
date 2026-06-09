# Microsoft.Crm.Asynchronous.Rollups.RollupJob::<Delete>b__56_0

- ea: `0xe0a0`
- end: `0xe0ed`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJob::<Delete>b__56_0`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0xe0a0`
- `0xe410`

## string_xrefs

- `0xe0d7`: `Unexpected sqlCommandResult encountered while trying to delete RollupJob : `

## pseudocode

```c

```

## disassembly

```asm
0xe0a0  ldarg.0
0xe0a1  ldfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier Microsoft.Crm.Asynchronous.Rollups.RollupJob::_jobModifier
0xe0a6  ldarg.0
0xe0a7  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::Delete(class Microsoft.Crm.Asynchronous.Rollups.RollupJob rollupJob)
0xe0ac  stloc.0
0xe0ad  ldloc.0
0xe0ae  switch   loc_E0D5, loc_E0D5, loc_E0D1, loc_E0D3, loc_E0D3, loc_E0D7, loc_E0D7
0xe0cf  br.s     loc_E0D7
0xe0d1  ldloc.0
0xe0d2  ret
0xe0d3  ldloc.0
0xe0d4  ret
0xe0d5  ldc.i4.1
0xe0d6  ret
0xe0d7  ldstr    aUnexpectedSqlc_1// "Unexpected sqlCommandResult encountered"...
0xe0dc  ldloc.0
0xe0dd  box      Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult
0xe0e2  call     string [mscorlib]System.String::Concat(object, object)
0xe0e7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Rollup.CrmRollupException::.ctor(string)
0xe0ec  throw
```
