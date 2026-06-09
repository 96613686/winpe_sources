# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateBreakMinutesInADay

- ea: `0x14da0`
- end: `0x150aa`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateBreakMinutesInADay`
- size: `778`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14340`
- `0x15370`

## callees

- `0x14da0`
- `0x1b090`

## pseudocode

```c

```

## disassembly

```asm
0x14da0  newobj   instance void <>c__DisplayClass17_0::.ctor()
0x14da5  stloc.0
0x14da6  ldloc.0
0x14da7  ldarg.2
0x14da8  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14dad  ldc.r8   0.0
0x14db6  stloc.1
0x14db7  ldc.r8   0.0
0x14dc0  stloc.2
0x14dc1  ldarg.1
0x14dc2  ldloc.0
0x14dc3  ldftn    instance bool <>c__DisplayClass17_0::<CalculateBreakMinutesInADay>b__0(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x14dc9  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x14dce  call     T0x2B000009
0x14dd3  call     T0x2B00000A
0x14dd8  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__17_1
0x14ddd  dup
0x14dde  brtrue.s loc_14DF7
0x14de0  pop
0x14de1  ldsfld   class <>c <>c::<>9
0x14de6  ldftn    instance bool <>c::<CalculateBreakMinutesInADay>b__17_1(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x14dec  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool>::.ctor(object, native int)
0x14df1  dup
0x14df2  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, bool> <>c::<>9__17_1
0x14df7  call     T0x2B000009
0x14dfc  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, valuetype [mscorlib]System.DateTime> <>c::<>9__17_2
0x14e01  dup
0x14e02  brtrue.s loc_14E1B
0x14e04  pop
0x14e05  ldsfld   class <>c <>c::<>9
0x14e0a  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<CalculateBreakMinutesInADay>b__17_2(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo value)
0x14e10  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x14e15  dup
0x14e16  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo, valuetype [mscorlib]System.DateTime> <>c::<>9__17_2
0x14e1b  call     T0x2B00000C
0x14e20  call     T0x2B00000A
0x14e25  stloc.3
0x14e26  ldc.i4.0
0x14e27  stloc.s  4
0x14e29  br       loc_1509E
0x14e2e  ldloc.3
0x14e2f  ldloc.s  4
0x14e31  ldelem.ref
0x14e32  stloc.s  5
0x14e34  ldloc.0
0x14e35  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14e3a  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14e3f  ldloc.s  5
0x14e41  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14e46  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14e4b  stloc.s  6
0x14e4d  ldloca.s 6
0x14e4f  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14e54  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14e59  brfalse  loc_14F3A
0x14e5e  ldloc.0
0x14e5f  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14e64  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14e69  ldloc.s  5
0x14e6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14e70  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14e75  stloc.s  6
0x14e77  ldloca.s 6
0x14e79  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14e7e  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14e83  brfalse  loc_14F3A
0x14e88  ldarg.s  4
0x14e8a  brtrue.s loc_14EC7
0x14e8c  ldloc.s  5
0x14e8e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14e93  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14e98  stloc.s  6
0x14e9a  ldloca.s 6
0x14e9c  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14ea1  ldloc.0
0x14ea2  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14ea7  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14eac  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14eb1  stloc.s  7
0x14eb3  ldloca.s 7
0x14eb5  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x14eba  stloc.2
0x14ebb  ldarga.s 3
0x14ebd  ldloc.2
0x14ebe  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x14ec3  starg.s  3
0x14ec5  br.s     loc_14F31
0x14ec7  ldarga.s 3
0x14ec9  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14ece  ldloc.s  5
0x14ed0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14ed5  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14eda  stloc.s  6
0x14edc  ldloca.s 6
0x14ede  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14ee3  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14ee8  brfalse.s loc_14F02
0x14eea  ldarg.3
0x14eeb  ldloc.0
0x14eec  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14ef1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x14ef6  stloc.s  7
0x14ef8  ldloca.s 7
0x14efa  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x14eff  stloc.2
0x14f00  br.s     loc_14F31
0x14f02  ldloc.s  5
0x14f04  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14f09  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14f0e  stloc.s  6
0x14f10  ldloca.s 6
0x14f12  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f17  ldloc.0
0x14f18  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14f1d  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f22  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14f27  stloc.s  7
0x14f29  ldloca.s 7
0x14f2b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x14f30  stloc.2
0x14f31  ldloc.1
0x14f32  ldloc.2
0x14f33  add
0x14f34  stloc.1
0x14f35  br       loc_15098
0x14f3a  ldloc.s  5
0x14f3c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14f41  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14f46  stloc.s  6
0x14f48  ldloca.s 6
0x14f4a  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f4f  ldloc.0
0x14f50  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass17_0::startDate
0x14f55  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f5a  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14f5f  brfalse.s loc_14FD7
0x14f61  ldloc.s  5
0x14f63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14f68  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14f6d  stloc.s  6
0x14f6f  ldloca.s 6
0x14f71  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f76  ldarga.s 3
0x14f78  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f7d  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14f82  brfalse.s loc_14FD7
0x14f84  ldloc.s  5
0x14f86  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14f8b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14f90  stloc.s  6
0x14f92  ldloca.s 6
0x14f94  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14f99  ldloc.s  5
0x14f9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14fa0  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14fa5  stloc.s  6
0x14fa7  ldloca.s 6
0x14fa9  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14fae  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14fb3  stloc.s  7
0x14fb5  ldloca.s 7
0x14fb7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x14fbc  stloc.2
0x14fbd  ldloc.1
0x14fbe  ldloc.2
0x14fbf  add
0x14fc0  stloc.1
0x14fc1  ldarg.s  4
0x14fc3  brtrue   loc_15098
0x14fc8  ldarga.s 3
0x14fca  ldloc.2
0x14fcb  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x14fd0  starg.s  3
0x14fd2  br       loc_15098
0x14fd7  ldarga.s 3
0x14fd9  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14fde  ldloc.s  5
0x14fe0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14fe5  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x14fea  stloc.s  6
0x14fec  ldloca.s 6
0x14fee  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x14ff3  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x14ff8  brfalse  loc_15098
0x14ffd  ldarga.s 3
0x14fff  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x15004  ldloc.s  5
0x15006  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x1500b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x15010  stloc.s  6
0x15012  ldloca.s 6
0x15014  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x15019  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1501e  brfalse.s loc_15098
0x15020  ldarg.s  4
0x15022  brtrue.s loc_15069
0x15024  ldloc.s  5
0x15026  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x1502b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x15030  stloc.s  6
0x15032  ldloca.s 6
0x15034  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x15039  ldloc.s  5
0x1503b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x15040  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x15045  stloc.s  6
0x15047  ldloca.s 6
0x15049  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x1504e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x15053  stloc.s  7
0x15055  ldloca.s 7
0x15057  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x1505c  stloc.2
0x1505d  ldarga.s 3
0x1505f  ldloc.2
0x15060  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x15065  starg.s  3
0x15067  br.s     loc_15094
0x15069  ldarga.s 3
0x1506b  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x15070  ldloc.s  5
0x15072  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x15077  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UserTime()
0x1507c  stloc.s  6
0x1507e  ldloca.s 6
0x15080  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x15085  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1508a  stloc.s  7
0x1508c  ldloca.s 7
0x1508e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x15093  stloc.2
0x15094  ldloc.1
0x15095  ldloc.2
0x15096  add
0x15097  stloc.1
0x15098  ldloc.s  4
0x1509a  ldc.i4.1
0x1509b  add
0x1509c  stloc.s  4
0x1509e  ldloc.s  4
0x150a0  ldloc.3
0x150a1  ldlen
0x150a2  conv.i4
0x150a3  blt      loc_14E2E
0x150a8  ldloc.1
0x150a9  ret
```
