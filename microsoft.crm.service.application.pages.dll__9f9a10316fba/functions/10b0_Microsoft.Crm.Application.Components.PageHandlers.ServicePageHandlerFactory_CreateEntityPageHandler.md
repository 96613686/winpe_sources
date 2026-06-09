# Microsoft.Crm.Application.Components.PageHandlers.ServicePageHandlerFactory::CreateEntityPageHandler

- ea: `0x10b0`
- end: `0x10e4`
- name: `Microsoft.Crm.Application.Components.PageHandlers.ServicePageHandlerFactory::CreateEntityPageHandler`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x10b0`
- `0xcf70`
- `0xdca0`
- `0xe110`

## pseudocode

```c

```

## disassembly

```asm
0x10b0  ldarg.2
0x10b1  ldc.i4.s 0x70
0x10b3  beq.s    loc_10C8
0x10b5  ldarg.2
0x10b6  ldc.i4.s 0x7F
0x10b8  beq.s    loc_10CE
0x10ba  ldarg.2
0x10bb  ldc.i4   0xFA3
0x10c0  bne.un.s loc_10D4
0x10c2  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.CalendarEntityPageHandler::.ctor()
0x10c7  ret
0x10c8  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.CaseEntityPageHandler::.ctor()
0x10cd  ret
0x10ce  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticlesEntityPageHandler::.ctor()
0x10d3  ret
0x10d4  ldstr    aUnsupportedEnt// "Unsupported Entity code."
0x10d9  ldstr    aEntitytypecode// "entityTypeCode"
0x10de  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x10e3  throw
```
