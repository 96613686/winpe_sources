# Microsoft.Crm.Marketing.Application.PageHandlers.MarketingPageHandlerFactory::CreateAreaPageHandler

- ea: `0x2500`
- end: `0x252e`
- name: `Microsoft.Crm.Marketing.Application.PageHandlers.MarketingPageHandlerFactory::CreateAreaPageHandler`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1580`
- `0x1b30`
- `0x2500`

## pseudocode

```c

```

## disassembly

```asm
0x2500  ldarg.2
0x2501  ldc.i4   0x1130
0x2506  beq.s    loc_2512
0x2508  ldarg.2
0x2509  ldc.i4   0x1132
0x250e  beq.s    loc_2518
0x2510  br.s     loc_251E
0x2512  newobj   instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignAreaPageHandler::.ctor()
0x2517  ret
0x2518  newobj   instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityAreaPageHandler::.ctor()
0x251d  ret
0x251e  ldstr    aUnsupportedEnt// "Unsupported Entity code."
0x2523  ldstr    aEntitytypecode_0// "entityTypeCode"
0x2528  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x252d  throw
```
