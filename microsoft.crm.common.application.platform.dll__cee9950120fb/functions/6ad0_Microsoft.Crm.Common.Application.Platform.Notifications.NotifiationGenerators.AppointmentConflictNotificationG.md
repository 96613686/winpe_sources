# Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.AppointmentConflictNotificationGenerator::AddRequiredColumns

- ea: `0x6ad0`
- end: `0x6aed`
- name: `Microsoft.Crm.Common.Application.Platform.Notifications.NotifiationGenerators.AppointmentConflictNotificationGenerator::AddRequiredColumns`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x6ad9`: `scheduledstart`
- `0x6ae1`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x6ad0  ldarg.2
0x6ad1  ldc.i4.2
0x6ad2  newarr   [mscorlib]System.String
0x6ad7  dup
0x6ad8  ldc.i4.0
0x6ad9  ldstr    aScheduledstart// "scheduledstart"
0x6ade  stelem.ref
0x6adf  dup
0x6ae0  ldc.i4.1
0x6ae1  ldstr    aScheduledend// "scheduledend"
0x6ae6  stelem.ref
0x6ae7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6aec  ret
```
