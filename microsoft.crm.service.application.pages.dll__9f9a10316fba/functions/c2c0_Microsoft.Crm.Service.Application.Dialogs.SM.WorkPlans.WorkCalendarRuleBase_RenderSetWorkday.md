# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RenderSetWorkday

- ea: `0xc2c0`
- end: `0xc3b4`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RenderSetWorkday`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xc2c0`
- `0xc3c0`
- `0xc510`

## pseudocode

```c

```

## disassembly

```asm
0xc2c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc2c5  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xc2ca  stloc.0
0xc2cb  ldloc.0
0xc2cc  ldstr    aWorkdaystartNe_0// "_workdayStart=new Date(\"1/1/80 "
0xc2d1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc2d6  ldloc.0
0xc2d7  ldarg.0
0xc2d8  ldarg.0
0xc2d9  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_workingHoursRule
0xc2de  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xc2e3  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RenderTimeSpanAsTime(valuetype [mscorlib]System.TimeSpan span)
0xc2e8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc2ed  ldarg.0
0xc2ee  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::CalculateDaysInWorkingHours()
0xc2f3  ldc.i4.1
0xc2f4  ble.s    loc_C35A
0xc2f6  ldloc.0
0xc2f7  ldstr    aWorkdayendNewD// "\"); _workdayEnd=new Date(\"1/"
0xc2fc  ldarg.0
0xc2fd  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::CalculateDaysInWorkingHours()
0xc302  box      [mscorlib]System.Int32
0xc307  ldstr    a80// "/80 "
0xc30c  call     string [mscorlib]System.String::Concat(object, object, object)
0xc311  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc316  ldarg.0
0xc317  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_workingHoursRule
0xc31c  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xc321  stloc.2
0xc322  ldloca.s 2
0xc324  ldarg.0
0xc325  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_workingHoursRule
0xc32a  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xc32f  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Add(valuetype [mscorlib]System.TimeSpan)
0xc334  stloc.1
0xc335  ldloca.s 1
0xc337  ldarg.0
0xc338  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::CalculateDaysInWorkingHours()
0xc33d  ldc.i4.1
0xc33e  sub
0xc33f  conv.r8
0xc340  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromDays(float64)
0xc345  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Subtract(valuetype [mscorlib]System.TimeSpan)
0xc34a  pop
0xc34b  ldloc.0
0xc34c  ldarg.0
0xc34d  ldloc.1
0xc34e  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RenderTimeSpanAsTime(valuetype [mscorlib]System.TimeSpan span)
0xc353  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc358  br.s     loc_C38F
0xc35a  ldloc.0
0xc35b  ldstr    aWorkdayendNewD_0// "\"); _workdayEnd=new Date(\"1/1/80 "
0xc360  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc365  ldloc.0
0xc366  ldarg.0
0xc367  ldarg.0
0xc368  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_workingHoursRule
0xc36d  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xc372  stloc.2
0xc373  ldloca.s 2
0xc375  ldarg.0
0xc376  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_workingHoursRule
0xc37b  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xc380  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Add(valuetype [mscorlib]System.TimeSpan)
0xc385  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RenderTimeSpanAsTime(valuetype [mscorlib]System.TimeSpan span)
0xc38a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc38f  ldloc.0
0xc390  ldstr    asc_20A5E// "\");"
0xc395  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xc39a  ldloc.0
0xc39b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.IO.StringWriter::GetStringBuilder()
0xc3a0  callvirt instance string [mscorlib]System.Object::ToString()
0xc3a5  stloc.3
0xc3a6  leave.s  loc_C3B2
0xc3a8  ldloc.0
0xc3a9  brfalse.s loc_C3B1
0xc3ab  ldloc.0
0xc3ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc3b1  endfinally
0xc3b2  ldloc.3
0xc3b3  ret
```
