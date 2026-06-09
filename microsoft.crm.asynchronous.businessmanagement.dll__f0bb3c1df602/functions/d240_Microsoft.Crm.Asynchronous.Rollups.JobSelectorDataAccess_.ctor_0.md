# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::.ctor_0

- ea: `0xd240`
- end: `0xd279`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::.ctor_0`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc2b0`
- `0xc310`
- `0xd220`

## callees

- `0xe140`

## pseudocode

```c

```

## disassembly

```asm
0xd240  ldarg.0
0xd241  call     instance void [mscorlib]System.Object::.ctor()
0xd246  ldarg.0
0xd247  ldarg.1
0xd248  stfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupsAsyncContext
0xd24d  ldarg.0
0xd24e  ldarg.0
0xd24f  ldfld    class Microsoft.Crm.Asynchronous.RollupsAsyncContext Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupsAsyncContext
0xd254  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::.ctor(class Microsoft.Crm.Asynchronous.RollupsAsyncContext rollupsAsyncContext)
0xd259  stfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_modifier
0xd25e  ldarg.0
0xd25f  ldarg.2
0xd260  stfld    valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_initialState
0xd265  ldarg.0
0xd266  ldarg.3
0xd267  stfld    valuetype [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.RollupJobState Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_finalState
0xd26c  ldarg.0
0xd26d  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::_rollupPropertiesId
0xd272  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xd278  ret
```
