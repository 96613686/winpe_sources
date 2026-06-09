# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateBusinessClosureDurationBetweenTwoDates

- ea: `0x14500`
- end: `0x1470f`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateBusinessClosureDurationBetweenTwoDates`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14340`

## callees

- `0x144c0`
- `0x14500`

## pseudocode

```c

```

## disassembly

```asm
0x14500  ldc.r8   0.0
0x14509  stloc.0
0x1450a  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x1450f  brfalse  loc_1470D
0x14514  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x14519  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::get_Count()
0x1451e  ldc.i4.0
0x1451f  ble      loc_1470D
0x14524  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x14529  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::GetEnumerator()
0x1452e  stloc.1
0x1452f  br       loc_146F1
0x14534  ldloca.s 1
0x14536  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::get_Current()
0x1453b  stloc.2
0x1453c  ldloc.2
0x1453d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14542  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x14547  stloc.3
0x14548  ldloca.s 3
0x1454a  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1454f  ldarga.s 1
0x14551  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14556  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1455b  brfalse  loc_145ED
0x14560  ldloc.2
0x14561  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14566  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x1456b  stloc.3
0x1456c  ldloca.s 3
0x1456e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14573  ldarga.s 1
0x14575  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1457a  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1457f  brfalse.s loc_145ED
0x14581  ldloc.2
0x14582  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14587  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x1458c  ldarg.1
0x1458d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x14592  stloc.s  5
0x14594  ldloca.s 5
0x14596  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x1459b  call     float64 [mscorlib]System.Math::Ceiling(float64)
0x145a0  stloc.s  4
0x145a2  ldc.i4.0
0x145a3  stloc.s  6
0x145a5  br.s     loc_145E1
0x145a7  ldarga.s 1
0x145a9  ldloc.s  6
0x145ab  conv.r8
0x145ac  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x145b1  stloc.3
0x145b2  ldloca.s 3
0x145b4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x145b9  stloc.s  7
0x145bb  ldloca.s 7
0x145bd  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x145c2  ldarga.s 2
0x145c4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x145c9  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x145ce  brfalse.s loc_145DB
0x145d0  ldloc.0
0x145d1  ldarg.0
0x145d2  ldloc.s  7
0x145d4  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::TotalMinutesInADay(valuetype [mscorlib]System.DateTime startDate)
0x145d9  add
0x145da  stloc.0
0x145db  ldloc.s  6
0x145dd  ldc.i4.1
0x145de  add
0x145df  stloc.s  6
0x145e1  ldloc.s  6
0x145e3  conv.r8
0x145e4  ldloc.s  4
0x145e6  blt.s    loc_145A7
0x145e8  br       loc_146F1
0x145ed  ldloc.2
0x145ee  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x145f3  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x145f8  stloc.3
0x145f9  ldloca.s 3
0x145fb  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14600  ldarga.s 1
0x14602  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14607  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1460c  brfalse.s loc_1462F
0x1460e  ldloc.2
0x1460f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14614  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x14619  stloc.3
0x1461a  ldloca.s 3
0x1461c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14621  ldarga.s 2
0x14623  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14628  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1462d  brtrue.s loc_14674
0x1462f  ldloc.2
0x14630  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14635  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x1463a  stloc.3
0x1463b  ldloca.s 3
0x1463d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14642  ldarga.s 1
0x14644  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14649  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1464e  brfalse  loc_146F1
0x14653  ldloc.2
0x14654  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x14659  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x1465e  stloc.3
0x1465f  ldloca.s 3
0x14661  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x14666  ldarga.s 2
0x14668  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1466d  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x14672  brfalse.s loc_146F1
0x14674  ldloc.2
0x14675  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_End()
0x1467a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x1467f  ldloc.2
0x14680  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x14685  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x1468a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1468f  stloc.s  5
0x14691  ldloca.s 5
0x14693  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x14698  call     float64 [mscorlib]System.Math::Ceiling(float64)
0x1469d  stloc.s  8
0x1469f  ldc.i4.0
0x146a0  stloc.s  9
0x146a2  br.s     loc_146EA
0x146a4  ldloc.2
0x146a5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo::get_Start()
0x146aa  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_UniversalTime()
0x146af  stloc.3
0x146b0  ldloca.s 3
0x146b2  ldloc.s  9
0x146b4  conv.r8
0x146b5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x146ba  stloc.3
0x146bb  ldloca.s 3
0x146bd  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x146c2  stloc.s  0xA
0x146c4  ldloca.s 0xA
0x146c6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x146cb  ldarga.s 2
0x146cd  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x146d2  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x146d7  brfalse.s loc_146E4
0x146d9  ldloc.0
0x146da  ldarg.0
0x146db  ldloc.s  0xA
0x146dd  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::TotalMinutesInADay(valuetype [mscorlib]System.DateTime startDate)
0x146e2  add
0x146e3  stloc.0
0x146e4  ldloc.s  9
0x146e6  ldc.i4.1
0x146e7  add
0x146e8  stloc.s  9
0x146ea  ldloc.s  9
0x146ec  conv.r8
0x146ed  ldloc.s  8
0x146ef  blt.s    loc_146A4
0x146f1  ldloca.s 1
0x146f3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>::MoveNext()
0x146f8  brtrue   loc_14534
0x146fd  leave.s  loc_1470D
0x146ff  ldloca.s 1
0x14701  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo>
0x14707  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1470c  endfinally
0x1470d  ldloc.0
0x1470e  ret
```
