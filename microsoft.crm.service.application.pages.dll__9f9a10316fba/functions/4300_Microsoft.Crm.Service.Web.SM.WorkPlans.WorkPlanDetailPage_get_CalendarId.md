# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_CalendarId

- ea: `0x4300`
- end: `0x4333`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::get_CalendarId`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x43e0`
- `0x4b90`
- `0x57c0`

## callees

- `0x4300`

## pseudocode

```c

```

## disassembly

```asm
0x4300  ldarg.0
0x4301  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarId
0x4306  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x430b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4310  brtrue.s loc_432D
0x4312  ldarg.0
0x4313  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendarId
0x4318  ldstr    aB// "B"
0x431d  call     instance string [mscorlib]System.Guid::ToString(string)
0x4322  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4327  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x432c  ret
0x432d  ldsfld   string [mscorlib]System.String::Empty
0x4332  ret
```
