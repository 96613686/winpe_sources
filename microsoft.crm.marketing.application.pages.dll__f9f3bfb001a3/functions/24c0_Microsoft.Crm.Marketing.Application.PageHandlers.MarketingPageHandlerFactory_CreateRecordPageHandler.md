# Microsoft.Crm.Marketing.Application.PageHandlers.MarketingPageHandlerFactory::CreateRecordPageHandler

- ea: `0x24c0`
- end: `0x24fc`
- name: `Microsoft.Crm.Marketing.Application.PageHandlers.MarketingPageHandlerFactory::CreateRecordPageHandler`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1970`
- `0x2280`
- `0x2480`
- `0x24c0`

## pseudocode

```c

```

## disassembly

```asm
0x24c0  ldarg.2
0x24c1  ldc.i4   0x1130
0x24c6  sub
0x24c7  switch   loc_24DA, loc_24E6, loc_24E0
0x24d8  br.s     loc_24EC
0x24da  newobj   instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::.ctor()
0x24df  ret
0x24e0  newobj   instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::.ctor()
0x24e5  ret
0x24e6  newobj   instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::.ctor()
0x24eb  ret
0x24ec  ldstr    aUnsupportedEnt// "Unsupported Entity code."
0x24f1  ldstr    aEntitytypecode_0// "entityTypeCode"
0x24f6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x24fb  throw
```
