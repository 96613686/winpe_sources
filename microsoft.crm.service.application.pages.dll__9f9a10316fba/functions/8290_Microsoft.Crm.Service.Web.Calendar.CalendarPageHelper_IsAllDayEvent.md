# Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::IsAllDayEvent

- ea: `0x8290`
- end: `0x82c3`
- name: `Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::IsAllDayEvent`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x82f0`

## string_xrefs

- `0x8291`: `scheduledstart`
- `0x82a2`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x8290  ldarg.0
0x8291  ldstr    aScheduledstart// "scheduledstart"
0x8296  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x829b  unbox.any [mscorlib]System.DateTime
0x82a0  stloc.0
0x82a1  ldarg.0
0x82a2  ldstr    aScheduledend// "scheduledend"
0x82a7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x82ac  unbox.any [mscorlib]System.DateTime
0x82b1  stloc.1
0x82b2  ldloca.s 1
0x82b4  ldloc.0
0x82b5  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x82ba  stloc.2
0x82bb  ldloc.0
0x82bc  ldloc.2
0x82bd  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsAllDayEvent(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x82c2  ret
```
