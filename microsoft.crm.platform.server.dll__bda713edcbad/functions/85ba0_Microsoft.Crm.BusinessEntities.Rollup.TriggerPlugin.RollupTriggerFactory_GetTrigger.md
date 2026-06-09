# Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerFactory::GetTrigger

- ea: `0x85ba0`
- end: `0x85bf4`
- name: `Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerFactory::GetTrigger`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x72450`

## callees

- `0x85020`
- `0x85220`
- `0x85400`
- `0x85610`
- `0x85ba0`
- `0x85c00`

## string_xrefs

- `0x85bc2`: `Update`
- `0x85bcf`: `Delete`
- `0x85bb5`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x85ba0  ldarg.0
0x85ba1  ldloca.s 0
0x85ba3  ldarg.2
0x85ba4  call     bool Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerFactory::Validate(class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupsByEntity& rollupsByEntity, string primaryEntityName)
0x85ba9  brfalse.s loc_85BF2
0x85bab  ldarg.0
0x85bac  ldloc.0
0x85bad  ldarg.3
0x85bae  newobj   instance void Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupsByEntity rollupsByEntity, bool isActivityParty)
0x85bb3  stloc.1
0x85bb4  ldarg.1
0x85bb5  ldstr    aCreate// "Create"
0x85bba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x85bbf  brtrue.s loc_85BDD
0x85bc1  ldarg.1
0x85bc2  ldstr    aUpdate// "Update"
0x85bc7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x85bcc  brtrue.s loc_85BE4
0x85bce  ldarg.1
0x85bcf  ldstr    aDelete// "Delete"
0x85bd4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x85bd9  brtrue.s loc_85BEB
0x85bdb  br.s     loc_85BF2
0x85bdd  ldloc.1
0x85bde  newobj   instance void Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.CreateTrigger::.ctor(class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerContext context)
0x85be3  ret
0x85be4  ldloc.1
0x85be5  newobj   instance void Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.UpdateTrigger::.ctor(class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerContext context)
0x85bea  ret
0x85beb  ldloc.1
0x85bec  newobj   instance void Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.DeleteTrigger::.ctor(class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerContext context)
0x85bf1  ret
0x85bf2  ldnull
0x85bf3  ret
```
