# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RegisterPlugIns

- ea: `0x5470`
- end: `0x54c5`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RegisterPlugIns`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x52b0`

## callees

- `0x51a0`
- `0x5470`

## string_xrefs

- `0x548e`: `create`
- `0x54ba`: `create`

## pseudocode

```c

```

## disassembly

```asm
0x5470  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConvertRulePluginRegistrationHelper::.ctor()
0x5475  stloc.0
0x5476  ldarg.2
0x5477  ldc.i4.1
0x5478  bne.un.s loc_5499
0x547a  ldarg.1
0x547b  ldc.i4   0x1078
0x5480  beq.s    loc_54C4
0x5482  ldarg.1
0x5483  ldc.i4   0x106A
0x5488  beq.s    loc_54C4
0x548a  ldloc.0
0x548b  ldarg.s  6
0x548d  ldarg.1
0x548e  ldstr    aCreate// "create"
0x5493  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConvertRulePluginRegistrationHelper::RegisterConvertRuleRelatedPlugin(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, string)
0x5498  ret
0x5499  ldarg.1
0x549a  ldc.i4   0x1078
0x549f  beq.s    loc_54C4
0x54a1  ldarg.1
0x54a2  ldc.i4   0x106A
0x54a7  beq.s    loc_54C4
0x54a9  ldarg.0
0x54aa  ldarg.s  6
0x54ac  ldarg.s  5
0x54ae  ldarg.1
0x54af  call     instance bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::CanDeregisterConvertRuleRelatedPlugin(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid convertRuleId, int32 objectTypeCode)
0x54b4  brfalse.s loc_54C4
0x54b6  ldloc.0
0x54b7  ldarg.s  6
0x54b9  ldarg.1
0x54ba  ldstr    aCreate// "create"
0x54bf  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConvertRulePluginRegistrationHelper::DeregisterConvertRuleRelatedPlugin(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32, string)
0x54c4  ret
```
