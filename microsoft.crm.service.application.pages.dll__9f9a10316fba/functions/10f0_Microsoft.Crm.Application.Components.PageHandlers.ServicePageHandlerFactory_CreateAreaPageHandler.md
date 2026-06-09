# Microsoft.Crm.Application.Components.PageHandlers.ServicePageHandlerFactory::CreateAreaPageHandler

- ea: `0x10f0`
- end: `0x111e`
- name: `Microsoft.Crm.Application.Components.PageHandlers.ServicePageHandlerFactory::CreateAreaPageHandler`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10f0`
- `0xe990`

## pseudocode

```c

```

## disassembly

```asm
0x10f0  ldarg.2
0x10f1  ldc.i4   0xFA9
0x10f6  beq.s    loc_1102
0x10f8  ldarg.2
0x10f9  ldc.i4   0x2618
0x10fe  beq.s    loc_1108
0x1100  br.s     loc_110E
0x1102  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SiteAreaPageHandler::.ctor()
0x1107  ret
0x1108  newobj   instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::.ctor()
0x110d  ret
0x110e  ldstr    aUnsupportedEnt// "Unsupported Entity code."
0x1113  ldstr    aEntitytypecode// "entityTypeCode"
0x1118  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x111d  throw
```
