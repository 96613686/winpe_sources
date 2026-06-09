# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText_0

- ea: `0x4f00`
- end: `0x4fc1`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText_0`
- size: `193`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4ef0`
- `0x4fd0`
- `0x5090`

## callees

- `0x4f00`
- `0x56d0`

## pseudocode

```c

```

## disassembly

```asm
0x4f00  ldarg.1
0x4f01  brfalse  loc_4FB0
0x4f06  ldstr    aNotworkingtime// "NotWorkingTimeType"
0x4f0b  ldarg.1
0x4f0c  call     bool [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::CompareCalendarRuleTimeType(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase)
0x4f11  brtrue   loc_4FB0
0x4f16  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4f1b  stloc.0
0x4f1c  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x4f21  stloc.s  4
0x4f23  ldloca.s 4
0x4f25  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x4f2a  stloc.s  4
0x4f2c  ldloca.s 4
0x4f2e  ldarg.1
0x4f2f  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Offset()
0x4f34  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x4f39  stloc.1
0x4f3a  ldloca.s 1
0x4f3c  ldarg.1
0x4f3d  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Duration()
0x4f42  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x4f47  stloc.2
0x4f48  ldloca.s 2
0x4f4a  ldloc.1
0x4f4b  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x4f50  pop
0x4f51  ldloc.0
0x4f52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4f57  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4f5c  stloc.3
0x4f5d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x4f62  ldstr    a0123// "{0} - {1} ({2} {3})"
0x4f67  ldc.i4.4
0x4f68  newarr   [mscorlib]System.Object
0x4f6d  dup
0x4f6e  ldc.i4.0
0x4f6f  ldloc.1
0x4f70  ldloc.0
0x4f71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x4f76  ldloc.3
0x4f77  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatTime(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4f7c  stelem.ref
0x4f7d  dup
0x4f7e  ldc.i4.1
0x4f7f  ldloc.2
0x4f80  ldloc.0
0x4f81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x4f86  ldloc.3
0x4f87  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::FormatTime(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4f8c  stelem.ref
0x4f8d  dup
0x4f8e  ldc.i4.2
0x4f8f  ldloc.1
0x4f90  ldloc.2
0x4f91  call     string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::CalculateDuration(valuetype [mscorlib]System.DateTime start, valuetype [mscorlib]System.DateTime end)
0x4f96  stelem.ref
0x4f97  dup
0x4f98  ldc.i4.3
0x4f99  ldarg.0
0x4f9a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4f9f  ldstr    aSmHours// "SM_Hours"
0x4fa4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4fa9  stelem.ref
0x4faa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4faf  ret
0x4fb0  ldarg.0
0x4fb1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4fb6  ldstr    aSmSetWorkingHo// "SM_Set_Working_Hours"
0x4fbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4fc0  ret
```
