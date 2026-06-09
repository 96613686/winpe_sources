# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::ConfigureForm

- ea: `0xc240`
- end: `0xc2b4`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::ConfigureForm`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbf90`
- `0xbfb0`
- `0xc240`
- `0xc450`
- `0xc460`
- `0xc470`

## pseudocode

```c

```

## disassembly

```asm
0xc240  ldarg.0
0xc241  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xc246  ldarg.0
0xc247  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_resourceId
0xc24c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc251  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc256  brfalse.s loc_C26F
0xc258  ldarg.0
0xc259  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0xc25e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc263  ldarg.0
0xc264  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ObjectTypeCode()
0xc269  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::FindOrCreateResourceCalendar(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32)
0xc26e  pop
0xc26f  ldarg.0
0xc270  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarId
0xc275  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc27a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc27f  brfalse.s loc_C2AD
0xc281  ldarg.0
0xc282  ldarg.0
0xc283  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RetrieveWorkingHoursRule()
0xc288  stfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_workingHoursRule
0xc28d  ldarg.0
0xc28e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::_calendarRuleId
0xc293  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc298  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc29d  brfalse.s loc_C2A6
0xc29f  ldarg.0
0xc2a0  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::EditCalendarRule()
0xc2a5  ret
0xc2a6  ldarg.0
0xc2a7  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::NewCalendarRule()
0xc2ac  ret
0xc2ad  ldarg.0
0xc2ae  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::NewCalendarRule()
0xc2b3  ret
```
