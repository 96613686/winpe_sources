# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId

- ea: `0xbfb0`
- end: `0xbfe3`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId`
- size: `51`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b90`
- `0xa450`
- `0xaf70`
- `0xb0e0`
- `0xb570`
- `0xc240`

## callees

- `0xbfb0`

## pseudocode

```c

```

## disassembly

```asm
0xbfb0  ldarg.0
0xbfb1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_resourceId
0xbfb6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbfbb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbfc0  brtrue.s loc_BFDD
0xbfc2  ldarg.0
0xbfc3  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_resourceId
0xbfc8  ldstr    aB// "B"
0xbfcd  call     instance string [mscorlib]System.Guid::ToString(string)
0xbfd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbfd7  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xbfdc  ret
0xbfdd  ldsfld   string [mscorlib]System.String::Empty
0xbfe2  ret
```
