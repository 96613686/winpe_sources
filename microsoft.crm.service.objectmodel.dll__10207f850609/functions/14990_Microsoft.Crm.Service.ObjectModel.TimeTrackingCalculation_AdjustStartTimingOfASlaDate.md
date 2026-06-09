# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate

- ea: `0x14990`
- end: `0x14b4e`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14340`
- `0x15180`

## callees

- `0x14990`
- `0x14b50`
- `0x1aee0`

## pseudocode

```c

```

## disassembly

```asm
0x14990  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x14995  stloc.0
0x14996  ldloc.0
0x14997  ldarg.2
0x14998  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x1499d  ldarg.1
0x1499e  ldloc.0
0x1499f  ldftn    instance bool <>c__DisplayClass14_0::<AdjustStartTimingOfASlaDate>b__0(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x149a5  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x149aa  call     T0x2B000009
0x149af  call     T0x2B00000A
0x149b4  stloc.1
0x149b5  ldloc.1
0x149b6  ldlen
0x149b7  brfalse  loc_14B34
0x149bc  ldloc.1
0x149bd  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__14_1
0x149c2  dup
0x149c3  brtrue.s loc_149DC
0x149c5  pop
0x149c6  ldsfld   class <>c <>c::<>9
0x149cb  ldftn    instance bool <>c::<AdjustStartTimingOfASlaDate>b__14_1(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x149d1  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x149d6  dup
0x149d7  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__14_1
0x149dc  call     T0x2B000009
0x149e1  call     T0x2B00000B
0x149e6  stloc.2
0x149e7  ldloc.0
0x149e8  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x149ed  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x149f2  ldloc.2
0x149f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x149f8  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x149fd  stloc.3
0x149fe  ldloca.s 3
0x14a00  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14a05  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14a0a  brfalse  loc_14A95
0x14a0f  ldloc.0
0x14a10  ldloc.0
0x14a11  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14a16  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x14a1b  ldloc.0
0x14a1c  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14a21  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x14a26  ldloc.0
0x14a27  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14a2c  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x14a31  ldloc.2
0x14a32  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14a37  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14a3c  stloc.3
0x14a3d  ldloca.s 3
0x14a3f  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14a44  stloc.s  4
0x14a46  ldloca.s 4
0x14a48  call     instance int32 [mscorlib]System.TimeSpan::get_Hours()
0x14a4d  ldloc.2
0x14a4e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14a53  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14a58  stloc.3
0x14a59  ldloca.s 3
0x14a5b  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14a60  stloc.s  4
0x14a62  ldloca.s 4
0x14a64  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0x14a69  ldloc.2
0x14a6a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14a6f  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14a74  stloc.3
0x14a75  ldloca.s 3
0x14a77  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14a7c  stloc.s  4
0x14a7e  ldloca.s 4
0x14a80  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0x14a85  ldc.i4.0
0x14a86  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTimeKind)
0x14a8b  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14a90  br       loc_14B47
0x14a95  ldloc.0
0x14a96  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14a9b  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14aa0  ldloc.2
0x14aa1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14aa6  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14aab  stloc.3
0x14aac  ldloca.s 3
0x14aae  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14ab3  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14ab8  brfalse.s loc_14ADA
0x14aba  ldloc.0
0x14abb  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14ac0  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x14ac5  ldloc.2
0x14ac6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14acb  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14ad0  stloc.3
0x14ad1  ldloca.s 3
0x14ad3  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x14ad8  beq.s    loc_14B1F
0x14ada  ldloc.0
0x14adb  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14ae0  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x14ae5  ldloc.2
0x14ae6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14aeb  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14af0  stloc.3
0x14af1  ldloca.s 3
0x14af3  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x14af8  beq.s    loc_14B47
0x14afa  ldloc.2
0x14afb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14b00  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14b05  stloc.3
0x14b06  ldloca.s 3
0x14b08  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14b0d  ldloc.0
0x14b0e  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14b13  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14b18  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14b1d  brfalse.s loc_14B47
0x14b1f  ldloc.0
0x14b20  ldarg.0
0x14b21  ldarg.1
0x14b22  ldloc.0
0x14b23  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14b28  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::RetrieveNextAvailableDateTime(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x14b2d  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14b32  br.s     loc_14B47
0x14b34  ldloc.0
0x14b35  ldarg.0
0x14b36  ldarg.1
0x14b37  ldloc.0
0x14b38  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14b3d  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::RetrieveNextAvailableDateTime(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x14b42  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14b47  ldloc.0
0x14b48  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass14_0::startDate
0x14b4d  ret
```
