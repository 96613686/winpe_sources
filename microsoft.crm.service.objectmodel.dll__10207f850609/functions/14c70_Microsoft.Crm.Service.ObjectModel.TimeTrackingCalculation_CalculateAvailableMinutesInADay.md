# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateAvailableMinutesInADay

- ea: `0x14c70`
- end: `0x14d97`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateAvailableMinutesInADay`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14340`
- `0x15370`

## callees

- `0x14c70`
- `0x1b030`

## pseudocode

```c

```

## disassembly

```asm
0x14c70  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x14c75  stloc.0
0x14c76  ldloc.0
0x14c77  ldarg.2
0x14c78  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass16_0::startDate
0x14c7d  ldc.r8   0.0
0x14c86  stloc.1
0x14c87  ldarg.1
0x14c88  ldloc.0
0x14c89  ldftn    instance bool <>c__DisplayClass16_0::<CalculateAvailableMinutesInADay>b__0(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x14c8f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x14c94  call     T0x2B000009
0x14c99  call     T0x2B00000A
0x14c9e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__16_1
0x14ca3  dup
0x14ca4  brtrue.s loc_14CBD
0x14ca6  pop
0x14ca7  ldsfld   class <>c <>c::<>9
0x14cac  ldftn    instance bool <>c::<CalculateAvailableMinutesInADay>b__16_1(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x14cb2  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x14cb7  dup
0x14cb8  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__16_1
0x14cbd  call     T0x2B000009
0x14cc2  call     T0x2B00000A
0x14cc7  ldarg.0
0x14cc8  ldarg.0
0x14cc9  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x14cce  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.DayOfWeek, float64> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_AvailableMinutesInaDay()
0x14cd3  ldloc.0
0x14cd4  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass16_0::startDate
0x14cd9  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x14cde  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.DayOfWeek, float64>::get_Item(void)
0x14ce3  conv.r8
0x14ce4  stfld    float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::totalMinutesInADay
0x14ce9  stloc.2
0x14cea  ldc.i4.0
0x14ceb  stloc.3
0x14cec  br       loc_14D8C
0x14cf1  ldloc.2
0x14cf2  ldloc.3
0x14cf3  ldelem.ref
0x14cf4  stloc.s  4
0x14cf6  ldloc.0
0x14cf7  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass16_0::startDate
0x14cfc  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14d01  ldloc.s  4
0x14d03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14d08  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14d0d  stloc.s  5
0x14d0f  ldloca.s 5
0x14d11  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14d16  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14d1b  brfalse.s loc_14D57
0x14d1d  ldloc.1
0x14d1e  ldarg.0
0x14d1f  ldfld    float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::totalMinutesInADay
0x14d24  ldloc.0
0x14d25  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass16_0::startDate
0x14d2a  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14d2f  ldloc.s  4
0x14d31  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14d36  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14d3b  stloc.s  5
0x14d3d  ldloca.s 5
0x14d3f  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14d44  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14d49  stloc.s  6
0x14d4b  ldloca.s 6
0x14d4d  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x14d52  sub
0x14d53  add
0x14d54  stloc.1
0x14d55  br.s     loc_14D88
0x14d57  ldloc.1
0x14d58  ldloc.s  4
0x14d5a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14d5f  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14d64  stloc.s  5
0x14d66  ldloca.s 5
0x14d68  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14d6d  ldloc.0
0x14d6e  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass16_0::startDate
0x14d73  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14d78  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14d7d  stloc.s  6
0x14d7f  ldloca.s 6
0x14d81  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x14d86  add
0x14d87  stloc.1
0x14d88  ldloc.3
0x14d89  ldc.i4.1
0x14d8a  add
0x14d8b  stloc.3
0x14d8c  ldloc.3
0x14d8d  ldloc.2
0x14d8e  ldlen
0x14d8f  conv.i4
0x14d90  blt      loc_14CF1
0x14d95  ldloc.1
0x14d96  ret
```
