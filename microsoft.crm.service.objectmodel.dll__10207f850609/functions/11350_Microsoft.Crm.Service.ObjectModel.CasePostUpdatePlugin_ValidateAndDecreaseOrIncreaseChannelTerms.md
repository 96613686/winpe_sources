# Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseChannelTerms

- ea: `0x11350`
- end: `0x11368`
- name: `Microsoft.Crm.Service.ObjectModel.CasePostUpdatePlugin::ValidateAndDecreaseOrIncreaseChannelTerms`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10bc0`
- `0x11370`

## callees

- `0x11350`
- `0x11820`

## pseudocode

```c

```

## disassembly

```asm
0x11350  ldarg.1
0x11351  brfalse.s loc_11367
0x11353  ldarg.1
0x11354  ldarg.2
0x11355  ldarg.3
0x11356  ldstr    aRemainingterms// "remainingterms"
0x1135b  ldarg.s  4
0x1135d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11362  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::DecreaseOrIncreaseTerms(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, bool isIncrease, valuetype [mscorlib]System.Decimal numberOfTerms, string terms, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x11367  ret
```
