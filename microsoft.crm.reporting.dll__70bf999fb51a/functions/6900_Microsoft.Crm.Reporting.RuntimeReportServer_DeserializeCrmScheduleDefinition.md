# Microsoft.Crm.Reporting.RuntimeReportServer::DeserializeCrmScheduleDefinition

- ea: `0x6900`
- end: `0x6bb6`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::DeserializeCrmScheduleDefinition`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6340`

## callees

- `0x6750`
- `0x6900`

## pseudocode

```c

```

## disassembly

```asm
0x6900  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::.ctor()
0x6905  stloc.0
0x6906  ldarg.0
0x6907  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x690c  stloc.1
0x690d  ldtoken  Microsoft.Crm.Reporting.CrmScheduleDefinition
0x6912  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6917  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x691c  ldloc.1
0x691d  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x6922  castclass Microsoft.Crm.Reporting.CrmScheduleDefinition
0x6927  stloc.2
0x6928  ldloc.0
0x6929  ldnull
0x692a  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.RecurrencePattern)
0x692f  ldloc.0
0x6930  ldarg.1
0x6931  ldloc.2
0x6932  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Reporting.CrmScheduleDefinition::StartDateTime
0x6937  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToUniversalTime(valuetype [mscorlib]System.DateTime)
0x693c  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::get_Local()
0x6941  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTimeFromUtc(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x6946  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_StartDateTime(valuetype [mscorlib]System.DateTime)
0x694b  ldloc.0
0x694c  ldloc.2
0x694d  ldfld    bool Microsoft.Crm.Reporting.CrmScheduleDefinition::EndDateSpecified
0x6952  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_EndDateSpecified(bool)
0x6957  ldloc.0
0x6958  callvirt instance bool [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::get_EndDateSpecified()
0x695d  brfalse.s loc_697B
0x695f  ldloc.0
0x6960  ldarg.1
0x6961  ldloc.2
0x6962  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Reporting.CrmScheduleDefinition::EndDate
0x6967  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToUniversalTime(valuetype [mscorlib]System.DateTime)
0x696c  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::get_Local()
0x6971  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTimeFromUtc(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x6976  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_EndDate(valuetype [mscorlib]System.DateTime)
0x697b  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::.ctor()
0x6980  stloc.3
0x6981  ldloc.3
0x6982  ldc.i4.1
0x6983  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_January(bool)
0x6988  ldloc.3
0x6989  ldc.i4.1
0x698a  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_February(bool)
0x698f  ldloc.3
0x6990  ldc.i4.1
0x6991  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_March(bool)
0x6996  ldloc.3
0x6997  ldc.i4.1
0x6998  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_April(bool)
0x699d  ldloc.3
0x699e  ldc.i4.1
0x699f  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_May(bool)
0x69a4  ldloc.3
0x69a5  ldc.i4.1
0x69a6  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_June(bool)
0x69ab  ldloc.3
0x69ac  ldc.i4.1
0x69ad  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_July(bool)
0x69b2  ldloc.3
0x69b3  ldc.i4.1
0x69b4  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_August(bool)
0x69b9  ldloc.3
0x69ba  ldc.i4.1
0x69bb  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_September(bool)
0x69c0  ldloc.3
0x69c1  ldc.i4.1
0x69c2  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_October(bool)
0x69c7  ldloc.3
0x69c8  ldc.i4.1
0x69c9  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_November(bool)
0x69ce  ldloc.3
0x69cf  ldc.i4.1
0x69d0  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector::set_December(bool)
0x69d5  ldloc.2
0x69d6  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x69db  brfalse  loc_6BA8
0x69e0  ldloc.2
0x69e1  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x69e6  isinst   Microsoft.Crm.Reporting.CrmMinuteRecurrence
0x69eb  brfalse.s loc_6A18
0x69ed  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MinuteRecurrence::.ctor()
0x69f2  stloc.s  4
0x69f4  ldloc.s  4
0x69f6  ldloc.2
0x69f7  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x69fc  castclass Microsoft.Crm.Reporting.CrmMinuteRecurrence
0x6a01  ldfld    int32 Microsoft.Crm.Reporting.CrmMinuteRecurrence::MinutesInterval
0x6a06  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MinuteRecurrence::set_MinutesInterval(int32)
0x6a0b  ldloc.0
0x6a0c  ldloc.s  4
0x6a0e  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.RecurrencePattern)
0x6a13  leave    loc_6BB4
0x6a18  ldloc.2
0x6a19  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6a1e  isinst   Microsoft.Crm.Reporting.CrmDailyRecurrence
0x6a23  brfalse.s loc_6A50
0x6a25  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DailyRecurrence::.ctor()
0x6a2a  stloc.s  5
0x6a2c  ldloc.s  5
0x6a2e  ldloc.2
0x6a2f  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6a34  castclass Microsoft.Crm.Reporting.CrmDailyRecurrence
0x6a39  ldfld    int32 Microsoft.Crm.Reporting.CrmDailyRecurrence::DaysInterval
0x6a3e  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DailyRecurrence::set_DaysInterval(int32)
0x6a43  ldloc.0
0x6a44  ldloc.s  5
0x6a46  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.RecurrencePattern)
0x6a4b  leave    loc_6BB4
0x6a50  ldloc.2
0x6a51  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6a56  isinst   Microsoft.Crm.Reporting.CrmWeeklyRecurrence
0x6a5b  brfalse.s loc_6AA7
0x6a5d  ldloc.2
0x6a5e  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6a63  castclass Microsoft.Crm.Reporting.CrmWeeklyRecurrence
0x6a68  stloc.s  6
0x6a6a  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeeklyRecurrence::.ctor()
0x6a6f  stloc.s  7
0x6a71  ldloc.s  7
0x6a73  ldloc.s  6
0x6a75  ldfld    class Microsoft.Crm.Reporting.CrmDaysOfWeekSelector Microsoft.Crm.Reporting.CrmWeeklyRecurrence::DaysOfWeek
0x6a7a  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DaysOfWeekSelector Microsoft.Crm.Reporting.RuntimeReportServer::ConvertCrmDaysOfWeekSelector(class Microsoft.Crm.Reporting.CrmDaysOfWeekSelector cdows)
0x6a7f  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeeklyRecurrence::set_DaysOfWeek(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DaysOfWeekSelector)
0x6a84  ldloc.s  7
0x6a86  ldloc.s  6
0x6a88  ldfld    int32 Microsoft.Crm.Reporting.CrmWeeklyRecurrence::WeeksInterval
0x6a8d  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeeklyRecurrence::set_WeeksInterval(int32)
0x6a92  ldloc.s  7
0x6a94  ldc.i4.1
0x6a95  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeeklyRecurrence::set_WeeksIntervalSpecified(bool)
0x6a9a  ldloc.0
0x6a9b  ldloc.s  7
0x6a9d  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.RecurrencePattern)
0x6aa2  leave    loc_6BB4
0x6aa7  ldloc.2
0x6aa8  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6aad  isinst   Microsoft.Crm.Reporting.CrmMonthlyRecurrence
0x6ab2  brfalse.s loc_6AF1
0x6ab4  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyRecurrence::.ctor()
0x6ab9  stloc.s  8
0x6abb  ldloc.s  8
0x6abd  ldloc.2
0x6abe  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6ac3  castclass Microsoft.Crm.Reporting.CrmMonthlyRecurrence
0x6ac8  ldflda   int32 Microsoft.Crm.Reporting.CrmMonthlyRecurrence::Day
0x6acd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6ad2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6ad7  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyRecurrence::set_Days(string)
0x6adc  ldloc.s  8
0x6ade  ldloc.3
0x6adf  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyRecurrence::set_MonthsOfYear(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector)
0x6ae4  ldloc.0
0x6ae5  ldloc.s  8
0x6ae7  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.RecurrencePattern)
0x6aec  leave    loc_6BB4
0x6af1  ldloc.2
0x6af2  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6af7  isinst   Microsoft.Crm.Reporting.CrmMonthlyDOWRecurrence
0x6afc  brfalse  loc_6BA8
0x6b01  ldloc.2
0x6b02  ldfld    class Microsoft.Crm.Reporting.CrmRecurrencePattern Microsoft.Crm.Reporting.CrmScheduleDefinition::Item
0x6b07  castclass Microsoft.Crm.Reporting.CrmMonthlyDOWRecurrence
0x6b0c  stloc.s  9
0x6b0e  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::.ctor()
0x6b13  stloc.s  0xA
0x6b15  ldloc.s  0xA
0x6b17  ldloc.3
0x6b18  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_MonthsOfYear(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthsOfYearSelector)
0x6b1d  ldloc.s  0xA
0x6b1f  ldloc.s  9
0x6b21  ldfld    class Microsoft.Crm.Reporting.CrmDaysOfWeekSelector Microsoft.Crm.Reporting.CrmMonthlyDOWRecurrence::DaysOfWeek
0x6b26  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DaysOfWeekSelector Microsoft.Crm.Reporting.RuntimeReportServer::ConvertCrmDaysOfWeekSelector(class Microsoft.Crm.Reporting.CrmDaysOfWeekSelector cdows)
0x6b2b  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_DaysOfWeek(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DaysOfWeekSelector)
0x6b30  ldloc.s  0xA
0x6b32  ldc.i4.1
0x6b33  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeekSpecified(bool)
0x6b38  ldloc.s  9
0x6b3a  ldfld    valuetype Microsoft.Crm.Reporting.CrmWeekNumberEnum Microsoft.Crm.Reporting.CrmMonthlyDOWRecurrence::WhichWeek
0x6b3f  stloc.s  0xB
0x6b41  ldloc.s  0xB
0x6b43  switch   loc_6B5E, loc_6B70, loc_6B7A, loc_6B84, loc_6B8E
0x6b5c  br.s     loc_6B98
0x6b5e  ldloc.s  0xA
0x6b60  ldc.i4.0
0x6b61  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeek(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeekNumberEnum)
0x6b66  ldloc.s  0xA
0x6b68  ldc.i4.1
0x6b69  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeekSpecified(bool)
0x6b6e  br.s     loc_6BA0
0x6b70  ldloc.s  0xA
0x6b72  ldc.i4.1
0x6b73  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeek(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeekNumberEnum)
0x6b78  br.s     loc_6BA0
0x6b7a  ldloc.s  0xA
0x6b7c  ldc.i4.2
0x6b7d  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeek(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeekNumberEnum)
0x6b82  br.s     loc_6BA0
0x6b84  ldloc.s  0xA
0x6b86  ldc.i4.3
0x6b87  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeek(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeekNumberEnum)
0x6b8c  br.s     loc_6BA0
0x6b8e  ldloc.s  0xA
0x6b90  ldc.i4.4
0x6b91  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeek(valuetype [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.WeekNumberEnum)
0x6b96  br.s     loc_6BA0
0x6b98  ldloc.s  0xA
0x6b9a  ldc.i4.0
0x6b9b  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.MonthlyDOWRecurrence::set_WhichWeekSpecified(bool)
0x6ba0  ldloc.0
0x6ba1  ldloc.s  0xA
0x6ba3  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.RecurrencePattern)
0x6ba8  leave.s  loc_6BB4
0x6baa  ldloc.1
0x6bab  brfalse.s loc_6BB3
0x6bad  ldloc.1
0x6bae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6bb3  endfinally
0x6bb4  ldloc.0
0x6bb5  ret
```
