# Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::GenerateCalendarBlocks

- ea: `0x82f0`
- end: `0x89d8`
- name: `Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::GenerateCalendarBlocks`
- size: `1768`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b40`
- `0x8fe0`
- `0x9250`

## callees

- `0x8290`
- `0x82f0`

## string_xrefs

- `0x8381`: `scheduledstart`
- `0x8393`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x82f0  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray::.ctor()
0x82f5  stloc.0
0x82f6  ldarg.0
0x82f7  brfalse  loc_859B
0x82fc  ldarg.0
0x82fd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x8302  stloc.1
0x8303  br       loc_8584
0x8308  ldloc.1
0x8309  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x830e  stloc.2
0x830f  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::.ctor()
0x8314  stloc.3
0x8315  ldloc.3
0x8316  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x831b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_Id(valuetype [mscorlib]System.Guid)
0x8320  ldsfld   string [mscorlib]System.String::Empty
0x8325  stloc.s  4
0x8327  ldloc.2
0x8328  ldstr    aSubject// "subject"
0x832d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8332  brfalse.s loc_8346
0x8334  ldloc.2
0x8335  ldstr    aSubject// "subject"
0x833a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x833f  castclass [mscorlib]System.String
0x8344  stloc.s  4
0x8346  ldloc.3
0x8347  ldloc.2
0x8348  ldstr    aActivityid// "activityid"
0x834d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8352  unbox.any [mscorlib]System.Guid
0x8357  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_ObjectId(valuetype [mscorlib]System.Guid)
0x835c  ldloc.3
0x835d  ldloc.2
0x835e  ldstr    aActivitytypeco// "activitytypecode"
0x8363  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8368  unbox.any [mscorlib]System.Int32
0x836d  stloc.s  0xA
0x836f  ldloca.s 0xA
0x8371  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8376  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x837b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_Type(string)
0x8380  ldloc.2
0x8381  ldstr    aScheduledstart// "scheduledstart"
0x8386  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x838b  unbox.any [mscorlib]System.DateTime
0x8390  stloc.s  5
0x8392  ldloc.2
0x8393  ldstr    aScheduledend// "scheduledend"
0x8398  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x839d  unbox.any [mscorlib]System.DateTime
0x83a2  stloc.s  6
0x83a4  ldloc.3
0x83a5  ldc.i4.0
0x83a6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_InstanceType(int32)
0x83ab  ldloc.2
0x83ac  ldstr    aInstancetypeco// "instancetypecode"
0x83b1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x83b6  brfalse.s loc_83CE
0x83b8  ldloc.3
0x83b9  ldloc.2
0x83ba  ldstr    aInstancetypeco// "instancetypecode"
0x83bf  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x83c4  unbox.any [mscorlib]System.Int32
0x83c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_InstanceType(int32)
0x83ce  ldloc.3
0x83cf  ldloc.2
0x83d0  call     bool Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::IsAllDayEvent(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity activity)
0x83d5  brtrue.s loc_83E2
0x83d7  ldloc.s  5
0x83d9  ldloc.s  6
0x83db  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsSpanningMidnight(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x83e0  br.s     loc_83E3
0x83e2  ldc.i4.1
0x83e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_IsAllDay(bool)
0x83e8  ldnull
0x83e9  stloc.s  7
0x83eb  ldloc.s  6
0x83ed  ldloc.s  5
0x83ef  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x83f4  stloc.s  8
0x83f6  ldloc.s  5
0x83f8  ldloc.s  8
0x83fa  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsAllDayEvent(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x83ff  brfalse.s loc_8428
0x8401  ldloc.s  8
0x8403  ldc.r8   1.0
0x840c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromDays(float64)
0x8411  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x8416  brfalse.s loc_8428
0x8418  ldloc.s  4
0x841a  stloc.s  7
0x841c  ldloc.3
0x841d  ldc.i4.1
0x841e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_IsAllDay(bool)
0x8423  br       loc_853F
0x8428  ldloc.s  5
0x842a  ldloc.s  6
0x842c  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::IsSpanningMidnight(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x8431  brfalse  loc_84DD
0x8436  ldloc.3
0x8437  ldc.i4.1
0x8438  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_IsAllDay(bool)
0x843d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8442  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8447  ldstr    aCalendarCrossD// "Calendar_Cross_Day_Item"
0x844c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8451  ldc.i4.5
0x8452  newarr   [mscorlib]System.Object
0x8457  dup
0x8458  ldc.i4.0
0x8459  ldloca.s 5
0x845b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8460  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x8465  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x846a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x846f  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x8474  stelem.ref
0x8475  dup
0x8476  ldc.i4.1
0x8477  ldloca.s 5
0x8479  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x847e  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x8483  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortTimePattern()
0x8488  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x848d  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x8492  stelem.ref
0x8493  dup
0x8494  ldc.i4.2
0x8495  ldloca.s 6
0x8497  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x849c  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x84a1  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x84a6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x84ab  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x84b0  stelem.ref
0x84b1  dup
0x84b2  ldc.i4.3
0x84b3  ldloca.s 6
0x84b5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x84ba  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x84bf  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortTimePattern()
0x84c4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x84c9  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x84ce  stelem.ref
0x84cf  dup
0x84d0  ldc.i4.4
0x84d1  ldloc.s  4
0x84d3  stelem.ref
0x84d4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x84d9  stloc.s  7
0x84db  br.s     loc_853F
0x84dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x84e7  ldstr    aCalendarIntraD// "Calendar_Intra_Day_Item"
0x84ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84f1  ldc.i4.3
0x84f2  newarr   [mscorlib]System.Object
0x84f7  dup
0x84f8  ldc.i4.0
0x84f9  ldloca.s 5
0x84fb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8500  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x8505  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortTimePattern()
0x850a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x850f  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x8514  stelem.ref
0x8515  dup
0x8516  ldc.i4.1
0x8517  ldloca.s 6
0x8519  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x851e  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x8523  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortTimePattern()
0x8528  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x852d  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x8532  stelem.ref
0x8533  dup
0x8534  ldc.i4.2
0x8535  ldloc.s  4
0x8537  stelem.ref
0x8538  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x853d  stloc.s  7
0x853f  ldloc.3
0x8540  ldloc.s  7
0x8542  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_Title(string)
0x8547  ldloc.3
0x8548  ldloc.s  7
0x854a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_ToolTip(string)
0x854f  ldloc.3
0x8550  ldstr    aImgsIco16// "/_imgs/ico_16_"
0x8555  ldloc.3
0x8556  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::get_Type()
0x855b  ldstr    aGif// ".gif"
0x8560  call     string [mscorlib]System.String::Concat(string, string, string)
0x8565  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_IconLink(string)
0x856a  ldloca.s 9
0x856c  ldloc.s  5
0x856e  ldloc.s  6
0x8570  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x8575  ldloc.3
0x8576  call     instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::.ctor(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.ITimeMetadata)
0x857b  ldloc.0
0x857c  ldloc.s  9
0x857e  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.SortedTimeBlockArray::Add(valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock)
0x8583  pop
0x8584  ldloc.1
0x8585  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x858a  brtrue   loc_8308
0x858f  leave.s  loc_859B
0x8591  ldloc.1
0x8592  brfalse.s loc_859A
0x8594  ldloc.1
0x8595  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x859a  endfinally
0x859b  ldarg.1
0x859c  brfalse  loc_89D6
0x85a1  ldarg.1
0x85a2  stloc.s  0xB
0x85a4  ldc.i4.0
0x85a5  stloc.s  0xA
0x85a7  br       loc_89CB
0x85ac  ldloc.s  0xB
0x85ae  ldloc.s  0xA
0x85b0  ldelem   [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock
0x85b5  stloc.s  0xC
0x85b7  ldloca.s 0xC
0x85b9  call     instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.ITimeMetadata [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeBlock::get_Metadata()
0x85be  castclass [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata
0x85c3  stloc.s  0xD
0x85c5  ldstr    aVacationtimety// "VacationTimeType"
0x85ca  ldloc.s  0xD
0x85cc  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareTimeMetadataTimeType(string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata)
0x85d1  brtrue.s loc_85E4
0x85d3  ldstr    aHolidaytimetyp// "HolidayTimeType"
0x85d8  ldloc.s  0xD
0x85da  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareTimeMetadataTimeType(string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata)
0x85df  brfalse  loc_89C5
0x85e4  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::.ctor()
0x85e9  stloc.s  0xE
0x85eb  ldloc.s  0xD
0x85ed  ldstr    aSourceid// "SourceId"
0x85f2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x85f7  unbox.any [mscorlib]System.Guid
0x85fc  stloc.s  0xF
0x85fe  ldloc.s  0xE
0x8600  ldloc.s  0xF
0x8602  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_Id(valuetype [mscorlib]System.Guid)
0x8607  ldarg.2
0x8608  ldloc.s  0xD
0x860a  ldstr    aCalendarid_0// "CalendarId"
0x860f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x8614  unbox.any [mscorlib]System.Guid
0x8619  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindCalendarRuleByInnerCalendarId(valuetype [mscorlib]System.Guid)
0x861e  stloc.s  0x10
0x8620  ldstr    aVacationtimety// "VacationTimeType"
0x8625  ldloc.s  0xD
0x8627  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareTimeMetadataTimeType(string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata)
0x862c  brfalse.s loc_863E
0x862e  ldloc.s  0xE
0x8630  ldloc.s  0x10
0x8632  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_CalendarRuleId()
0x8637  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_ObjectId(valuetype [mscorlib]System.Guid)
0x863c  br.s     loc_8647
0x863e  ldloc.s  0xE
0x8640  ldloc.s  0xF
0x8642  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CalendarRowData::set_ObjectId(valuetype [mscorlib]System.Guid)
0x8647  ldnull
0x8648  stloc.s  0x11
0x864a  ldstr    aVacationtimety// "VacationTimeType"
0x864f  ldloc.s  0xD
0x8651  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareTimeMetadataTimeType(string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata)
0x8656  brtrue.s loc_8669
0x8658  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x865d  ldstr    aCalendarRuleHo// "Calendar_Rule_Holiday"
0x8662  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8667  br.s     loc_8678
0x8669  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x866e  ldstr    aCalendarRuleTi// "Calendar_Rule_Time_Off"
0x8673  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8678  stloc.s  0x12
0x867a  ldnull
0x867b  stloc.s  0x13
0x867d  ldstr    aHolidaytimetyp// "HolidayTimeType"
0x8682  ldloc.s  0xD
0x8684  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareTimeMetadataTimeType(string, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeMetadata)
0x8689  brfalse.s loc_86C2
0x868b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8690  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::GetOrgCalendar(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8695  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x869a  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x869f  stloc.s  0x15
0x86a1  ldloc.s  0x15
0x86a3  ldloc.s  0xD
0x86a5  ldstr    aSourceid_0// "sourceid"
0x86aa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x86af  unbox.any [mscorlib]System.Guid
0x86b4  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindCalendarRuleById(valuetype [mscorlib]System.Guid)
0x86b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_DisplayName()
0x86be  stloc.s  0x13
  ... truncated ...
```
