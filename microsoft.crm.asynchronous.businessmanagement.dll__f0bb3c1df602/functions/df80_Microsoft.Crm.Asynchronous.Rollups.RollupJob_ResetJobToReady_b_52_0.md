# Microsoft.Crm.Asynchronous.Rollups.RollupJob::<ResetJobToReady>b__52_0

- ea: `0xdf80`
- end: `0xdfd6`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJob::<ResetJobToReady>b__52_0`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xdf60`
- `0xdf80`
- `0xe150`

## string_xrefs

- `0xdfc0`: `Unexpected sqlCommandResult encountered while resetting RollupJob to ready : `

## pseudocode

```c

```

## disassembly

```asm
0xdf80  ldarg.0
0xdf81  ldfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier Microsoft.Crm.Asynchronous.Rollups.RollupJob::_jobModifier
0xdf86  ldarg.0
0xdf87  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::ResetStateToReady(class Microsoft.Crm.Asynchronous.Rollups.RollupJob rollupJob)
0xdf8c  stloc.0
0xdf8d  ldloc.0
0xdf8e  switch   loc_DFBC, loc_DFBE, loc_DFB1, loc_DFBA, loc_DFBA, loc_DFC0, loc_DFC0
0xdfaf  br.s     loc_DFC0
0xdfb1  ldarg.0
0xdfb2  call     instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete()
0xdfb7  pop
0xdfb8  ldloc.0
0xdfb9  ret
0xdfba  ldloc.0
0xdfbb  ret
0xdfbc  ldloc.0
0xdfbd  ret
0xdfbe  ldloc.0
0xdfbf  ret
0xdfc0  ldstr    aUnexpectedSqlc// "Unexpected sqlCommandResult encountered"...
0xdfc5  ldloc.0
0xdfc6  box      Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult
0xdfcb  call     string [mscorlib]System.String::Concat(object, object)
0xdfd0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Rollup.CrmRollupException::.ctor(string)
0xdfd5  throw
```
