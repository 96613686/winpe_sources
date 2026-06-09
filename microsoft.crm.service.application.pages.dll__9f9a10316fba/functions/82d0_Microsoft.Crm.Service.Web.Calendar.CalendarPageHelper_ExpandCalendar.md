# Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::ExpandCalendar

- ea: `0x82d0`
- end: `0x82e5`
- name: `Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::ExpandCalendar`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b40`
- `0x8fe0`
- `0x9250`

## callees

- `0x82d0`

## pseudocode

```c

```

## disassembly

```asm
0x82d0  ldnull
0x82d1  stloc.0
0x82d2  ldarg.2
0x82d3  brfalse.s loc_82E3
0x82d5  ldarg.2
0x82d6  ldarg.0
0x82d7  ldarg.1
0x82d8  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x82dd  callvirt instance valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock[] [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::Expand(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval)
0x82e2  stloc.0
0x82e3  ldloc.0
0x82e4  ret
```
