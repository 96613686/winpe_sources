# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_ResourceId

- ea: `0xbff0`
- end: `0xc015`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_ResourceId`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d10`
- `0xa450`
- `0xb0e0`

## callees

- `0xbff0`

## pseudocode

```c

```

## disassembly

```asm
0xbff0  ldarg.1
0xbff1  brfalse.s loc_C009
0xbff3  ldarg.1
0xbff4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbff9  ldc.i4.0
0xbffa  ble.s    loc_C009
0xbffc  ldarg.0
0xbffd  ldarg.1
0xbffe  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xc003  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_resourceId
0xc008  ret
0xc009  ldarg.0
0xc00a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc00f  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_resourceId
0xc014  ret
```
