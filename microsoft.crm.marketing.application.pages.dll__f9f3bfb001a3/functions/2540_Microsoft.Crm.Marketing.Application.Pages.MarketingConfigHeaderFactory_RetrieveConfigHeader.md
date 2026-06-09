# Microsoft.Crm.Marketing.Application.Pages.MarketingConfigHeaderFactory::RetrieveConfigHeader

- ea: `0x2540`
- end: `0x257c`
- name: `Microsoft.Crm.Marketing.Application.Pages.MarketingConfigHeaderFactory::RetrieveConfigHeader`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xef0`
- `0x1170`
- `0x11f0`
- `0x2540`

## pseudocode

```c

```

## disassembly

```asm
0x2540  ldarg.1
0x2541  ldc.i4   0x1130
0x2546  sub
0x2547  switch   loc_2560, loc_255A, loc_2566
0x2558  br.s     loc_256C
0x255a  newobj   instance void Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignResponseConfigHeader::.ctor()
0x255f  ret
0x2560  newobj   instance void Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignConfigHeader::.ctor()
0x2565  ret
0x2566  newobj   instance void Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::.ctor()
0x256b  ret
0x256c  ldstr    aUnsupportedTyp// "Unsupported type code."
0x2571  ldstr    aTypecode// "typeCode"
0x2576  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x257b  throw
```
