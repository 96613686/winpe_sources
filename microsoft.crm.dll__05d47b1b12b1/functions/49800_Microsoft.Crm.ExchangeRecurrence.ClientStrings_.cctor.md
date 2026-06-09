# Microsoft.Crm.ExchangeRecurrence.ClientStrings::.cctor

- ea: `0x49800`
- end: `0x49915`
- name: `Microsoft.Crm.ExchangeRecurrence.ClientStrings::.cctor`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x47ac0`

## string_xrefs

- `0x49811`: `TaskWhenWeeklyRegeneratingPattern`
- `0x49821`: `TaskWhenDailyRegeneratingPattern`
- `0x49831`: `TaskWhenYearlyRegeneratingPattern`
- `0x49876`: `TaskWhenDailyEveryDay`
- `0x498c7`: `TaskWhenEveryOtherDay`
- `0x498d0`: `TaskWhenMonthlyRegeneratingPattern`

## pseudocode

```c

```

## disassembly

```asm
0x49800  ldc.i4.s 0x1B
0x49802  newarr   [mscorlib]System.String
0x49807  dup
0x49808  ldc.i4.0
0x49809  ldstr    aWheneveryday// "WhenEveryDay"
0x4980e  stelem.ref
0x4980f  dup
0x49810  ldc.i4.1
0x49811  ldstr    aTaskwhenweekly// "TaskWhenWeeklyRegeneratingPattern"
0x49816  stelem.ref
0x49817  dup
0x49818  ldc.i4.2
0x49819  ldstr    aWhenfirst// "WhenFirst"
0x4981e  stelem.ref
0x4981f  dup
0x49820  ldc.i4.3
0x49821  ldstr    aTaskwhendailyr// "TaskWhenDailyRegeneratingPattern"
0x49826  stelem.ref
0x49827  dup
0x49828  ldc.i4.4
0x49829  ldstr    aWhenalldays// "WhenAllDays"
0x4982e  stelem.ref
0x4982f  dup
0x49830  ldc.i4.5
0x49831  ldstr    aTaskwhenyearly// "TaskWhenYearlyRegeneratingPattern"
0x49836  stelem.ref
0x49837  dup
0x49838  ldc.i4.6
0x49839  ldstr    aWheneveryweekd// "WhenEveryWeekDay"
0x4983e  stelem.ref
0x4983f  dup
0x49840  ldc.i4.7
0x49841  ldstr    aHebrewlunar// "HebrewLunar"
0x49846  stelem.ref
0x49847  dup
0x49848  ldc.i4.8
0x49849  ldstr    aWhenonemoreocc// "WhenOneMoreOccurrence"
0x4984e  stelem.ref
0x4984f  dup
0x49850  ldc.i4.s 9
0x49852  ldstr    aWhenweekdays// "WhenWeekDays"
0x49857  stelem.ref
0x49858  dup
0x49859  ldc.i4.s 0xA
0x4985b  ldstr    aCalendar// "Calendar"
0x49860  stelem.ref
0x49861  dup
0x49862  ldc.i4.s 0xB
0x49864  ldstr    aWhenoneveryday// "WhenOnEveryDayOfTheWeek"
0x49869  stelem.ref
0x4986a  dup
0x4986b  ldc.i4.s 0xC
0x4986d  ldstr    aCalendarwhenda_0// "CalendarWhenDailyEveryDay"
0x49872  stelem.ref
0x49873  dup
0x49874  ldc.i4.s 0xD
0x49876  ldstr    aTaskwhendailye_0// "TaskWhenDailyEveryDay"
0x4987b  stelem.ref
0x4987c  dup
0x4987d  ldc.i4.s 0xE
0x4987f  ldstr    aChineselunar// "ChineseLunar"
0x49884  stelem.ref
0x49885  dup
0x49886  ldc.i4.s 0xF
0x49888  ldstr    aKoreanlunar// "KoreanLunar"
0x4988d  stelem.ref
0x4988e  dup
0x4988f  ldc.i4.s 0x10
0x49891  ldstr    aWhenonweekdays// "WhenOnWeekDays"
0x49896  stelem.ref
0x49897  dup
0x49898  ldc.i4.s 0x11
0x4989a  ldstr    aWhensecond// "WhenSecond"
0x4989f  stelem.ref
0x498a0  dup
0x498a1  ldc.i4.s 0x12
0x498a3  ldstr    aWhenbothweeken// "WhenBothWeekendDays"
0x498a8  stelem.ref
0x498a9  dup
0x498aa  ldc.i4.s 0x13
0x498ac  ldstr    aWhenthird// "WhenThird"
0x498b1  stelem.ref
0x498b2  dup
0x498b3  ldc.i4.s 0x14
0x498b5  ldstr    aJapaneselunar// "JapaneseLunar"
0x498ba  stelem.ref
0x498bb  dup
0x498bc  ldc.i4.s 0x15
0x498be  ldstr    aWhenfourth// "WhenFourth"
0x498c3  stelem.ref
0x498c4  dup
0x498c5  ldc.i4.s 0x16
0x498c7  ldstr    aTaskwheneveryo// "TaskWhenEveryOtherDay"
0x498cc  stelem.ref
0x498cd  dup
0x498ce  ldc.i4.s 0x17
0x498d0  ldstr    aTaskwhenmonthl_4// "TaskWhenMonthlyRegeneratingPattern"
0x498d5  stelem.ref
0x498d6  dup
0x498d7  ldc.i4.s 0x18
0x498d9  ldstr    aHijri// "Hijri"
0x498de  stelem.ref
0x498df  dup
0x498e0  ldc.i4.s 0x19
0x498e2  ldstr    aCalendarwhenev// "CalendarWhenEveryOtherDay"
0x498e7  stelem.ref
0x498e8  dup
0x498e9  ldc.i4.s 0x1A
0x498eb  ldstr    aWhenlast// "WhenLast"
0x498f0  stelem.ref
0x498f1  stsfld   string[] Microsoft.Crm.ExchangeRecurrence.ClientStrings::stringIDs
0x498f6  ldstr    aMicrosoftCrmEx// "Microsoft.Crm.ExchangeRecurrence.Client"...
0x498fb  ldtoken  Microsoft.Crm.ExchangeRecurrence.ClientStrings
0x49900  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x49905  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4990a  call     class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager::GetResourceManager(string baseName, class [mscorlib]System.Reflection.Assembly assembly)
0x4990f  stsfld   class Microsoft.Crm.ExchangeRecurrence.ExchangeResourceManager Microsoft.Crm.ExchangeRecurrence.ClientStrings::ResourceManager
0x49914  ret
```
