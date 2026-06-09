# Microsoft.Crm.ExchangeRecurrence.TaskRecurrence::GenerateWhen

- ea: `0x469c0`
- end: `0x46a87`
- name: `Microsoft.Crm.ExchangeRecurrence.TaskRecurrence::GenerateWhen`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x42e00`
- `0x43760`
- `0x43770`
- `0x437a0`
- `0x437c0`
- `0x43860`
- `0x46740`
- `0x46840`
- `0x469c0`
- `0x48930`
- `0x48b10`
- `0x48be0`
- `0x49b00`
- `0x49c90`
- `0x49d90`

## string_xrefs

- `0x46a42`: `TaskRecurrence::GenerateWhen. The recurrence range is not allowed in this pattern. Pattern = {0}, Range = {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x469c0  ldarg.0
0x469c1  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrencePattern Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Pattern()
0x469c6  isinst   Microsoft.Crm.ExchangeRecurrence.RegeneratingPattern
0x469cb  brtrue.s loc_469D5
0x469cd  ldarg.0
0x469ce  ldarg.1
0x469cf  call     instance valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString Microsoft.Crm.ExchangeRecurrence.Recurrence::GenerateWhen(bool addTimeZoneInfo)
0x469d4  ret
0x469d5  ldarg.0
0x469d6  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrenceRange Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Range()
0x469db  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.ExchangeRecurrence.RecurrenceRange::get_StartDate()
0x469e0  ldarg.0
0x469e1  call     instance class [mscorlib]System.TimeZoneInfo Microsoft.Crm.ExchangeRecurrence.Recurrence::get_CreatedExTimeZone()
0x469e6  ldarg.0
0x469e7  callvirt instance class [mscorlib]System.TimeZoneInfo Microsoft.Crm.ExchangeRecurrence.Recurrence::get_ReadExTimeZone()
0x469ec  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTime(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo, class [mscorlib]System.TimeZoneInfo)
0x469f1  stloc.0
0x469f2  ldarg.0
0x469f3  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrencePattern Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Pattern()
0x469f8  callvirt instance valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString Microsoft.Crm.ExchangeRecurrence.RecurrencePattern::When()
0x469fd  ldloc.0
0x469fe  call     valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString Microsoft.Crm.ExchangeRecurrence.ClientStrings::WhenRecurringNoEndDateNoTimeInDay(valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString pattern, valuetype [mscorlib]System.DateTime startDate)
0x46a03  stloc.1
0x46a04  ldarg.0
0x46a05  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrenceRange Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Range()
0x46a0a  isinst   Microsoft.Crm.ExchangeRecurrence.NoEndRecurrenceRange
0x46a0f  brtrue.s loc_46A85
0x46a11  ldarg.0
0x46a12  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrenceRange Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Range()
0x46a17  isinst   Microsoft.Crm.ExchangeRecurrence.NumberedRecurrenceRange
0x46a1c  brfalse.s loc_46A3C
0x46a1e  ldloc.1
0x46a1f  ldarg.0
0x46a20  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrenceRange Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Range()
0x46a25  castclass Microsoft.Crm.ExchangeRecurrence.NumberedRecurrenceRange
0x46a2a  callvirt instance int32 Microsoft.Crm.ExchangeRecurrence.NumberedRecurrenceRange::get_NumberOfOccurrences()
0x46a2f  call     valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString Microsoft.Crm.ExchangeRecurrence.ClientStrings::WhenNMoreOccurrences(int32 numberOccurrence)
0x46a34  call     valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString Microsoft.Crm.ExchangeRecurrence.ClientStrings::JointStrings(valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString str1, valuetype Microsoft.Crm.ExchangeRecurrence.LocalizedString str2)
0x46a39  stloc.1
0x46a3a  br.s     loc_46A85
0x46a3c  ldarg.0
0x46a3d  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x46a42  ldstr    aTaskrecurrence// "TaskRecurrence::GenerateWhen. The recur"...
0x46a47  ldc.i4.2
0x46a48  newarr   [mscorlib]System.Object
0x46a4d  dup
0x46a4e  ldc.i4.0
0x46a4f  ldarg.0
0x46a50  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrencePattern Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Pattern()
0x46a55  stelem.ref
0x46a56  dup
0x46a57  ldc.i4.1
0x46a58  ldarg.0
0x46a59  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrenceRange Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Range()
0x46a5e  stelem.ref
0x46a5f  call     void Microsoft.Crm.ExchangeRecurrence.Diagnostics.ExTraceGlobals::TraceError(int32 objectId, string format, object[] args)
0x46a64  ldarg.0
0x46a65  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrencePattern Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Pattern()
0x46a6a  callvirt instance string [mscorlib]System.Object::ToString()
0x46a6f  ldarg.0
0x46a70  call     instance class Microsoft.Crm.ExchangeRecurrence.RecurrenceRange Microsoft.Crm.ExchangeRecurrence.Recurrence::get_Range()
0x46a75  callvirt instance string [mscorlib]System.Object::ToString()
0x46a7a  call     string Microsoft.Crm.ExchangeRecurrence.ServerStrings::TaskRecurrenceNotSupported(string pattern, string range)
0x46a7f  newobj   instance void Microsoft.Crm.ExchangeRecurrence.Diagnostics.CorruptDataException::.ctor(string message)
0x46a84  throw
0x46a85  ldloc.1
0x46a86  ret
```
