# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetActivityCardConfigurations

- ea: `0x11040`
- end: `0x11386`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetActivityCardConfigurations`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x10b30`

## callees

- `0x11040`
- `0x12d80`
- `0x12da0`
- `0x12e60`
- `0x12e80`
- `0x130f0`

## string_xrefs

- `0x1132d`: `ActionCard.TaskDueTodayCard.MiniCardText`

## pseudocode

```c

```

## disassembly

```asm
0x11040  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::.ctor()
0x11045  stloc.0
0x11046  ldarg.1
0x11047  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x1104c  stloc.1
0x1104d  ldloc.1
0x1104e  ldc.i4   0x1069
0x11053  sub
0x11054  switch   loc_1109A, loc_11181, loc_1133E, loc_111CC, loc_1133E, loc_1133E, loc_11217
0x11075  ldloc.1
0x11076  ldc.i4   0x1072
0x1107b  sub
0x1107c  switch   loc_11262, loc_1133E, loc_112F7, loc_1133E, loc_112AC
0x11095  br       loc_1133E
0x1109a  ldloc.0
0x1109b  ldarg.1
0x1109c  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x110a1  ldarg.1
0x110a2  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x110a7  ldc.i4   0x190
0x110ac  ldc.i4.0
0x110ad  ldarg.1
0x110ae  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledStart()
0x110b3  stloc.2
0x110b4  ldloca.s 2
0x110b6  ldc.r8   -12.0
0x110bf  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x110c4  ldarg.1
0x110c5  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x110ca  ldc.i4.s 0x15
0x110cc  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::MeetingToday
0x110d1  ldstr    aActioncardMeet// "ActionCard.MeetingToday.MiniCardText"
0x110d6  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x110db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x110e0  ldloc.0
0x110e1  ldarg.1
0x110e2  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x110e7  ldarg.1
0x110e8  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x110ed  ldc.i4   0x3E8
0x110f2  ldc.i4.0
0x110f3  ldarg.1
0x110f4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x110f9  stloc.2
0x110fa  ldloca.s 2
0x110fc  ldc.r8   -5.0
0x11105  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x1110a  ldarg.1
0x1110b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11110  stloc.2
0x11111  ldloca.s 2
0x11113  ldc.r8   30.0
0x1111c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x11121  ldc.i4.6
0x11122  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::RecentMeeting
0x11127  ldstr    aActioncardRece// "ActionCard.RecentMeetingCard.MiniCardTe"...
0x1112c  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x11131  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x11136  ldloc.0
0x11137  ldarg.1
0x11138  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x1113d  ldarg.1
0x1113e  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x11143  ldc.i4   0x3E8
0x11148  ldc.i4.1
0x11149  ldarg.1
0x1114a  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledStart()
0x1114f  stloc.2
0x11150  ldloca.s 2
0x11152  ldc.r8   -30.0
0x1115b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x11160  ldarg.1
0x11161  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledStart()
0x11166  ldc.i4.s 0x64
0x11168  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::UpcomingMeeting
0x1116d  ldstr    aActioncardOthe// "ActionCard.OtherActivityCard.MiniCardTe"...
0x11172  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x11177  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x1117c  br       loc_11384
0x11181  ldloc.0
0x11182  ldarg.1
0x11183  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x11188  ldarg.1
0x11189  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x1118e  ldc.i4   0x190
0x11193  ldc.i4.1
0x11194  ldarg.1
0x11195  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x1119a  stloc.2
0x1119b  ldloca.s 2
0x1119d  ldc.r8   -12.0
0x111a6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x111ab  ldarg.1
0x111ac  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x111b1  ldc.i4.s 0xD
0x111b3  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::EmailDueToday
0x111b8  ldstr    aActioncardOthe// "ActionCard.OtherActivityCard.MiniCardTe"...
0x111bd  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x111c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x111c7  br       loc_11384
0x111cc  ldloc.0
0x111cd  ldarg.1
0x111ce  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x111d3  ldarg.1
0x111d4  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x111d9  ldc.i4   0x190
0x111de  ldc.i4.1
0x111df  ldarg.1
0x111e0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x111e5  stloc.2
0x111e6  ldloca.s 2
0x111e8  ldc.r8   -12.0
0x111f1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x111f6  ldarg.1
0x111f7  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x111fc  ldc.i4.s 0xC
0x111fe  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::FaxDueToday
0x11203  ldstr    aActioncardOthe// "ActionCard.OtherActivityCard.MiniCardTe"...
0x11208  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x1120d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x11212  br       loc_11384
0x11217  ldloc.0
0x11218  ldarg.1
0x11219  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x1121e  ldarg.1
0x1121f  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x11224  ldc.i4   0x190
0x11229  ldc.i4.1
0x1122a  ldarg.1
0x1122b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11230  stloc.2
0x11231  ldloca.s 2
0x11233  ldc.r8   -12.0
0x1123c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x11241  ldarg.1
0x11242  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11247  ldc.i4.s 0xE
0x11249  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::LetterDueToday
0x1124e  ldstr    aActioncardOthe// "ActionCard.OtherActivityCard.MiniCardTe"...
0x11253  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x11258  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x1125d  br       loc_11384
0x11262  ldloc.0
0x11263  ldarg.1
0x11264  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x11269  ldarg.1
0x1126a  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x1126f  ldc.i4   0x190
0x11274  ldc.i4.1
0x11275  ldarg.1
0x11276  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x1127b  stloc.2
0x1127c  ldloca.s 2
0x1127e  ldc.r8   -12.0
0x11287  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x1128c  ldarg.1
0x1128d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11292  ldc.i4.8
0x11293  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::PhoneCallDueToday
0x11298  ldstr    aActioncardPhon// "ActionCard.PhoneCallDueTodayCard.MiniCa"...
0x1129d  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x112a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x112a7  br       loc_11384
0x112ac  ldloc.0
0x112ad  ldarg.1
0x112ae  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x112b3  ldarg.1
0x112b4  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x112b9  ldc.i4   0x190
0x112be  ldc.i4.1
0x112bf  ldarg.1
0x112c0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x112c5  stloc.2
0x112c6  ldloca.s 2
0x112c8  ldc.r8   -12.0
0x112d1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x112d6  ldarg.1
0x112d7  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x112dc  ldc.i4.s 0xF
0x112de  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::ServiceAppointmentDueToday
0x112e3  ldstr    aActioncardOthe// "ActionCard.OtherActivityCard.MiniCardTe"...
0x112e8  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x112ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x112f2  br       loc_11384
0x112f7  ldloc.0
0x112f8  ldarg.1
0x112f9  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x112fe  ldarg.1
0x112ff  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x11304  ldc.i4   0x190
0x11309  ldc.i4.1
0x1130a  ldarg.1
0x1130b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11310  stloc.2
0x11311  ldloca.s 2
0x11313  ldc.r8   -12.0
0x1131c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x11321  ldarg.1
0x11322  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11327  ldc.i4.7
0x11328  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::TaskDueToday
0x1132d  ldstr    aActioncardTask// "ActionCard.TaskDueTodayCard.MiniCardTex"...
0x11332  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x11337  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x1133c  br.s     loc_11384
0x1133e  ldloc.0
0x1133f  ldarg.1
0x11340  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_TypeCode()
0x11345  ldarg.1
0x11346  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_LogicalName()
0x1134b  ldc.i4   0x190
0x11350  ldc.i4.1
0x11351  ldarg.1
0x11352  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x11357  stloc.2
0x11358  ldloca.s 2
0x1135a  ldc.r8   -12.0
0x11363  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x11368  ldarg.1
0x11369  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x1136e  ldc.i4.s 0xB
0x11370  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::CustomActivityDueToday
0x11375  ldstr    aActioncardOthe// "ActionCard.OtherActivityCard.MiniCardTe"...
0x1137a  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::.ctor(int32 entityTypeCode, string entityLogicalName, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, bool visibility, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, valuetype [mscorlib]System.Guid associatedActionCardTypeId, [opt] string cardBodyResourceId)
0x1137f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::Add(var<u1>)
0x11384  ldloc.0
0x11385  ret
```
