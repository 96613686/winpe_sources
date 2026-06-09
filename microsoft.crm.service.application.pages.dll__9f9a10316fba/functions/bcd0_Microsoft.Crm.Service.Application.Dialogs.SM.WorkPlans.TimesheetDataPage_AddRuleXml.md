# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AddRuleXml

- ea: `0xbcd0`
- end: `0xbde3`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::AddRuleXml`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xbb70`

## callees

- `0xbcd0`
- `0xbef0`

## pseudocode

```c

```

## disassembly

```asm
0xbcd0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xbcd5  stloc.0
0xbcd6  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0xbcdb  stloc.3
0xbcdc  ldloca.s 3
0xbcde  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0xbce3  stloc.1
0xbce4  ldloca.s 1
0xbce6  ldarg.1
0xbce7  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0xbcec  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0xbcf1  stloc.2
0xbcf2  ldloc.0
0xbcf3  ldstr    aRule// "<rule>"
0xbcf8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbcfd  pop
0xbcfe  ldloc.0
0xbcff  ldstr    aType// "type"
0xbd04  ldstr    aBreaktimetype// "BreakTimeType"
0xbd09  ldarg.1
0xbd0a  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0xbd0f  brtrue.s loc_BD18
0xbd11  ldstr    aEffort// "effort"
0xbd16  br.s     loc_BD1D
0xbd18  ldstr    aBreak// "break"
0xbd1d  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::XmlNodeBuilder(string, string)
0xbd22  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbd27  pop
0xbd28  ldloc.0
0xbd29  ldstr    aStart// "start"
0xbd2e  ldloca.s 2
0xbd30  ldstr    aS// "s"
0xbd35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbd3a  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xbd3f  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::XmlNodeBuilder(string, string)
0xbd44  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbd49  pop
0xbd4a  ldloc.0
0xbd4b  ldstr    aDuration// "duration"
0xbd50  ldarg.1
0xbd51  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0xbd56  stloc.s  4
0xbd58  ldloca.s 4
0xbd5a  constrained. [mscorlib]System.TimeSpan
0xbd60  callvirt instance string [mscorlib]System.Object::ToString()
0xbd65  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::XmlNodeBuilder(string, string)
0xbd6a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbd6f  pop
0xbd70  ldstr    aResourcecapaci// "ResourceCapacityTimeType"
0xbd75  ldarg.1
0xbd76  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0xbd7b  brfalse.s loc_BDD0
0xbd7d  ldarg.1
0xbd7e  ldstr    aEffort// "effort"
0xbd83  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbd88  brfalse.s loc_BDD0
0xbd8a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xbd8f  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbd94  callvirt instance object [mscorlib]System.Globalization.NumberFormatInfo::Clone()
0xbd99  castclass [mscorlib]System.Globalization.NumberFormatInfo
0xbd9e  stloc.s  5
0xbda0  ldloc.s  5
0xbda2  ldc.i4.5
0xbda3  callvirt instance void [mscorlib]System.Globalization.NumberFormatInfo::set_NumberDecimalDigits(int32)
0xbda8  ldloc.0
0xbda9  ldstr    aEffort// "effort"
0xbdae  ldarg.0
0xbdaf  ldarg.1
0xbdb0  call     instance float64 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.TimesheetDataPage::GetEffort(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity calendarRule)
0xbdb5  stloc.s  6
0xbdb7  ldloca.s 6
0xbdb9  ldstr    aG// "g"
0xbdbe  ldloc.s  5
0xbdc0  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0xbdc5  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::XmlNodeBuilder(string, string)
0xbdca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbdcf  pop
0xbdd0  ldloc.0
0xbdd1  ldstr    aRule_0// "</rule>"
0xbdd6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xbddb  pop
0xbddc  ldloc.0
0xbddd  callvirt instance string [mscorlib]System.Object::ToString()
0xbde2  ret
```
