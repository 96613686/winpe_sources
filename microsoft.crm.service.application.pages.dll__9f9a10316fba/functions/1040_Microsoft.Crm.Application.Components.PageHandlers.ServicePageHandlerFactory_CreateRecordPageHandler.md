# Microsoft.Crm.Application.Components.PageHandlers.ServicePageHandlerFactory::CreateRecordPageHandler

- ea: `0x1040`
- end: `0x10ad`
- name: `Microsoft.Crm.Application.Components.PageHandlers.ServicePageHandlerFactory::CreateRecordPageHandler`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1040`
- `0xc6a0`
- `0xce30`
- `0xd220`
- `0xdb30`
- `0xdc40`
- `0xe940`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldarg.2
0x1041  ldc.i4   0x1076
0x1046  bgt.s    loc_105F
0x1048  ldarg.2
0x1049  ldc.i4.s 0x7F
0x104b  beq.s    loc_1085
0x104d  ldarg.2
0x104e  ldc.i4   0xFA3
0x1053  beq.s    loc_1079
0x1055  ldarg.2
0x1056  ldc.i4   0x1076
0x105b  beq.s    loc_107F
0x105d  br.s     loc_109D
0x105f  ldarg.2
0x1060  ldc.i4   0x2007
0x1065  beq.s    loc_108B
0x1067  ldarg.2
0x1068  ldc.i4   0x2455
0x106d  beq.s    loc_1091
0x106f  ldarg.2
0x1070  ldc.i4   0x2617
0x1075  beq.s    loc_1097
0x1077  br.s     loc_109D
0x1079  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.CalendarRecordPageHandler::.ctor()
0x107e  ret
0x107f  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ServiceAppointmentRecordPageHandler::.ctor()
0x1084  ret
0x1085  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.KbArticleRecordPageHandler::.ctor()
0x108a  ret
0x108b  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::.ctor()
0x1090  ret
0x1091  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::.ctor()
0x1096  ret
0x1097  newobj   instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::.ctor()
0x109c  ret
0x109d  ldstr    aUnsupportedEnt// "Unsupported Entity code."
0x10a2  ldstr    aEntitytypecode// "entityTypeCode"
0x10a7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x10ac  throw
```
