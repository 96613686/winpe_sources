# Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateMinutesSpent

- ea: `0x15180`
- end: `0x15362`
- name: `Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::CalculateMinutesSpent`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x132b0`

## callees

- `0x14710`
- `0x14990`
- `0x150b0`
- `0x15180`
- `0x15370`
- `0x153e0`

## string_xrefs

- `0x151b6`: `CustomerService`

## pseudocode

```c

```

## disassembly

```asm
0x15180  ldc.r8   0.0
0x15189  stloc.0
0x1518a  ldarg.2
0x1518b  ldarg.1
0x1518c  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15191  brfalse  loc_15360
0x15196  ldarg.3
0x15197  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1519c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x151a1  brfalse.s loc_151B6
0x151a3  ldarg.2
0x151a4  ldarg.1
0x151a5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x151aa  stloc.s  5
0x151ac  ldloca.s 5
0x151ae  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x151b3  stloc.0
0x151b4  ldloc.0
0x151b5  ret
0x151b6  ldstr    aCustomerservic// "CustomerService"
0x151bb  ldarg.3
0x151bc  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCacheKey::.ctor(string, valuetype [mscorlib]System.Guid)
0x151c1  stloc.1
0x151c2  ldarg.0
0x151c3  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCache::Instance()
0x151c8  ldloc.1
0x151c9  ldarg.s  4
0x151cb  ldc.i4.0
0x151cc  callvirt instance var<u1> class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingOrgCache`2<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingCacheKey, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData>::LookupEntry(void, var<u1>, !!T0)
0x151d1  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x151d6  ldarg.0
0x151d7  ldarg.0
0x151d8  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x151dd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_TimeTrackingTimeInfo()
0x151e2  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x151e7  ldnull
0x151e8  stsfld   class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo> Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_holidayClosureList
0x151ed  ldarg.0
0x151ee  ldarg.s  4
0x151f0  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext
0x151f5  ldarg.3
0x151f6  call     instance void Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::PopulateHolidayClosureRequests(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid calendarId)
0x151fb  ldarg.1
0x151fc  ldarg.0
0x151fd  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x15202  callvirt instance class [mscorlib]System.TimeZoneInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_CalendarTimeZone()
0x15207  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTime(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x1520c  stloc.2
0x1520d  ldarg.2
0x1520e  ldarg.0
0x1520f  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x15214  callvirt instance class [mscorlib]System.TimeZoneInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_CalendarTimeZone()
0x15219  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTime(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x1521e  stloc.3
0x1521f  ldarg.0
0x15220  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x15225  callvirt instance class [mscorlib]System.TimeZoneInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_CalendarTimeZone()
0x1522a  callvirt instance bool [mscorlib]System.TimeZoneInfo::get_SupportsDaylightSavingTime()
0x1522f  brfalse.s loc_1529E
0x15231  ldarg.0
0x15232  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x15237  callvirt instance class [mscorlib]System.TimeZoneInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_CalendarTimeZone()
0x1523c  ldarg.1
0x1523d  callvirt instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeZoneInfo::GetUtcOffset(valuetype [mscorlib]System.DateTime)
0x15242  stloc.s  5
0x15244  ldloca.s 5
0x15246  call     instance int32 [mscorlib]System.TimeSpan::get_Hours()
0x1524b  ldarg.0
0x1524c  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x15251  callvirt instance class [mscorlib]System.TimeZoneInfo [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_CalendarTimeZone()
0x15256  ldarg.2
0x15257  callvirt instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeZoneInfo::GetUtcOffset(valuetype [mscorlib]System.DateTime)
0x1525c  stloc.s  5
0x1525e  ldloca.s 5
0x15260  call     instance int32 [mscorlib]System.TimeSpan::get_Hours()
0x15265  beq.s    loc_1529E
0x15267  ldarg.0
0x15268  ldarg.0
0x15269  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x1526e  ldloc.2
0x1526f  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x15274  ldarg.0
0x15275  ldarg.0
0x15276  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x1527b  ldloc.3
0x1527c  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x15281  stloc.s  6
0x15283  ldloc.2
0x15284  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15289  brfalse.s loc_1529E
0x1528b  ldloc.s  6
0x1528d  ldloc.3
0x1528e  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15293  brfalse.s loc_1529E
0x15295  ldarg.0
0x15296  ldloc.2
0x15297  ldloc.3
0x15298  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetDstAdjustedTime(valuetype [mscorlib]System.DateTime startTimeinCalendarzone, valuetype [mscorlib]System.DateTime endTimeinCalendarzone)
0x1529d  stloc.3
0x1529e  ldloca.s 3
0x152a0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x152a5  ldloca.s 2
0x152a7  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x152ac  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x152b1  stloc.s  5
0x152b3  ldloca.s 5
0x152b5  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x152ba  stloc.s  4
0x152bc  ldc.i4.0
0x152bd  stloc.s  7
0x152bf  br       loc_15357
0x152c4  ldloca.s 2
0x152c6  ldloc.s  7
0x152c8  conv.r8
0x152c9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x152ce  stloc.s  9
0x152d0  ldloca.s 9
0x152d2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x152d7  stloc.s  8
0x152d9  ldloc.s  7
0x152db  brtrue.s loc_152E0
0x152dd  ldloc.2
0x152de  stloc.s  8
0x152e0  ldarg.0
0x152e1  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_trackingData
0x152e6  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.DayOfWeek, float64> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.TimeTrackingData::get_AvailableMinutesInaDay()
0x152eb  ldloca.s 8
0x152ed  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x152f2  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.DayOfWeek, float64>::get_Item(void)
0x152f7  conv.r8
0x152f8  ldc.r8   0.0
0x15301  ble.un.s loc_15351
0x15303  ldarg.0
0x15304  ldloc.s  8
0x15306  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetBusinessClosureDuration(valuetype [mscorlib]System.DateTime startDate)
0x1530b  ldc.r8   0.0
0x15314  bne.un.s loc_15351
0x15316  ldarg.0
0x15317  ldarg.0
0x15318  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::_weeklyTimeInfo
0x1531d  ldloc.s  8
0x1531f  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::AdjustStartTimingOfASlaDate(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeInfo[] timeInfo, valuetype [mscorlib]System.DateTime startDate)
0x15324  stloc.s  0xA
0x15326  ldloca.s 0xA
0x15328  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1532d  ldloca.s 8
0x1532f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x15334  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15339  brtrue.s loc_15351
0x1533b  ldloc.3
0x1533c  ldloc.s  0xA
0x1533e  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15343  brfalse.s loc_15351
0x15345  ldloc.0
0x15346  ldarg.0
0x15347  ldloc.s  0xA
0x15349  ldloc.3
0x1534a  call     instance float64 Microsoft.Crm.Service.ObjectModel.TimeTrackingCalculation::GetAvailableMinutes(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0x1534f  add
0x15350  stloc.0
0x15351  ldloc.s  7
0x15353  ldc.i4.1
0x15354  add
0x15355  stloc.s  7
0x15357  ldloc.s  7
0x15359  ldloc.s  4
0x1535b  ble      loc_152C4
0x15360  ldloc.0
0x15361  ret
```
