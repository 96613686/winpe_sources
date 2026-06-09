# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateTriggerDateTimeInternal

- ea: `0x14340`
- end: `0x144b1`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateTriggerDateTimeInternal`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14300`

## callees

- `0x14340`
- `0x14500`
- `0x14990`
- `0x14c70`
- `0x14da0`
- `0x150b0`

## string_xrefs

- `0x1434c`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0x14340  ldarg.3
0x14341  stloc.0
0x14342  ldc.r8   0.0
0x1434b  stloc.1
0x1434c  ldstr    aCustomerservic// "CustomerService"
0x14351  ldarg.2
0x14352  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCacheKey::.ctor(string, valuetype [mscorlib]System.Guid)
0x14357  stloc.2
0x14358  ldarg.0
0x14359  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCache::Instance()
0x1435e  ldloc.2
0x1435f  ldarg.s  4
0x14361  ldc.i4.0
0x14362  callvirt instance var<u1> class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingOrgCache`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCacheKey, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData>::LookupEntry(void, var<u1>, !!T0)
0x14367  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x1436c  ldarg.1
0x1436d  ldarg.0
0x1436e  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x14373  callvirt instance class [mscorlib]System.TimeZoneInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_CalendarTimeZone()
0x14378  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTime(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x1437d  dup
0x1437e  stloc.s  4
0x14380  stloc.3
0x14381  ldarg.0
0x14382  ldarg.0
0x14383  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x14388  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_TimeTrackingTimeInfo()
0x1438d  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x14392  ldarg.0
0x14393  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x14398  callvirt instance float64 [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_TotalAvailableMinutesInaWeek()
0x1439d  stloc.1
0x1439e  br       loc_1448E
0x143a3  ldarg.0
0x143a4  ldarg.0
0x143a5  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x143aa  ldloc.s  4
0x143ac  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x143b1  stloc.s  4
0x143b3  ldloc.0
0x143b4  ldloc.1
0x143b5  bge.un.s loc_143C8
0x143b7  ldloca.s 4
0x143b9  ldarg.0
0x143ba  ldloc.s  4
0x143bc  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetBusinessClosureDuration(valuetype [mscorlib]System.DateTime startDate)
0x143c1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x143c6  stloc.s  4
0x143c8  ldarg.0
0x143c9  ldarg.0
0x143ca  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x143cf  ldloc.s  4
0x143d1  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x143d6  stloc.s  4
0x143d8  ldloc.0
0x143d9  ldloc.1
0x143da  ble.un.s loc_1440F
0x143dc  ldloca.s 4
0x143de  ldc.r8   10080.0
0x143e7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x143ec  stloc.s  6
0x143ee  ldarg.0
0x143ef  ldloc.s  4
0x143f1  ldloc.s  6
0x143f3  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateBusinessClosureDurationBetweenTwoDates(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0x143f8  stloc.s  7
0x143fa  ldloc.s  7
0x143fc  ldloc.1
0x143fd  blt.un.s loc_14402
0x143ff  ldloc.1
0x14400  stloc.s  7
0x14402  ldloc.0
0x14403  ldloc.1
0x14404  ldloc.s  7
0x14406  sub
0x14407  sub
0x14408  stloc.0
0x14409  ldloc.s  6
0x1440b  stloc.s  4
0x1440d  br.s     loc_1448E
0x1440f  ldarg.0
0x14410  ldarg.0
0x14411  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x14416  ldloc.s  4
0x14418  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateAvailableMinutesInADay(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x1441d  stloc.s  8
0x1441f  ldloc.0
0x14420  ldloc.s  8
0x14422  bgt.s    loc_1442E
0x14424  ldloca.s 4
0x14426  ldloc.0
0x14427  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x1442c  br.s     loc_14437
0x1442e  ldloca.s 4
0x14430  ldloc.s  8
0x14432  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x14437  stloc.s  9
0x14439  ldarg.0
0x1443a  ldarg.0
0x1443b  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x14440  ldloc.s  4
0x14442  ldloc.s  9
0x14444  ldc.i4.0
0x14445  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateBreakMinutesInADay(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, bool isExactDifference)
0x1444a  stloc.s  0xA
0x1444c  ldloc.s  8
0x1444e  ldloc.s  0xA
0x14450  sub
0x14451  stloc.s  8
0x14453  ldloc.0
0x14454  ldloc.s  8
0x14456  sub
0x14457  ldc.r8   0.0
0x14460  ble.un.s loc_14477
0x14462  ldloca.s 4
0x14464  ldloc.s  8
0x14466  ldloc.s  0xA
0x14468  add
0x14469  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x1446e  stloc.s  4
0x14470  ldloc.0
0x14471  ldloc.s  8
0x14473  sub
0x14474  stloc.0
0x14475  br.s     loc_1448E
0x14477  ldloca.s 4
0x14479  ldloc.0
0x1447a  ldloc.s  0xA
0x1447c  add
0x1447d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x14482  stloc.s  4
0x14484  ldc.r8   0.0
0x1448d  stloc.0
0x1448e  ldloc.0
0x1448f  ldc.r8   0.0
0x14498  bgt      loc_143A3
0x1449d  ldloc.s  4
0x1449f  ldloc.3
0x144a0  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x144a5  stloc.s  5
0x144a7  ldarga.s 1
0x144a9  ldloc.s  5
0x144ab  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x144b0  ret
```
