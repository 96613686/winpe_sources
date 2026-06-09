# Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseTerms

- ea: `0x11310`
- end: `0x11350`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseTerms`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10bc0`
- `0x111d0`

## callees

- `0x11310`
- `0x11820`

## pseudocode

```c

```

## disassembly

```asm
0x11310  ldarg.1
0x11311  brfalse.s loc_1134F
0x11313  ldarg.1
0x11314  ldstr    aAllocationtype// "allocationtypecode"
0x11319  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1131e  unbox.any [mscorlib]System.Int32
0x11323  brtrue.s loc_1134F
0x11325  ldarg.1
0x11326  ldstr    aDecreaseremain// "decreaseremainingon"
0x1132b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11330  unbox.any [mscorlib]System.Int32
0x11335  ldc.i4.1
0x11336  bne.un.s loc_1134F
0x11338  ldarg.1
0x11339  ldarg.2
0x1133a  ldsfld   valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::One
0x1133f  ldstr    aRemainingterms// "remainingterms"
0x11344  ldarg.3
0x11345  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1134a  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, string terms, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1134f  ret
```
