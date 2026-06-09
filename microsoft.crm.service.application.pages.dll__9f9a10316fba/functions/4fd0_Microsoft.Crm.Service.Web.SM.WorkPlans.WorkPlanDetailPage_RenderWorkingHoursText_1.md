# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText_1

- ea: `0x4fd0`
- end: `0x508e`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText_1`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x4f00`
- `0x4fd0`
- `0x54c0`
- `0x5540`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  ldnull
0x4fd1  stloc.0
0x4fd2  ldnull
0x4fd3  stloc.1
0x4fd4  ldarg.0
0x4fd5  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x4fda  brfalse  loc_5067
0x4fdf  ldarg.0
0x4fe0  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x4fe5  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsRecurringRuleVaried(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule recurringRule)
0x4fea  brfalse.s loc_5067
0x4fec  ldarg.0
0x4fed  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4ff2  ldarg.0
0x4ff3  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_recurringRule
0x4ff8  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::GetSubRules(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule)
0x4ffd  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x5002  stloc.2
0x5003  br.s     loc_502D
0x5005  ldloc.2
0x5006  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x500b  castclass [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule
0x5010  stloc.3
0x5011  ldloc.3
0x5012  ldarg.1
0x5013  call     bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule rule, int32 checkIndex)
0x5018  brfalse.s loc_502D
0x501a  ldloc.3
0x501b  stloc.0
0x501c  ldloc.0
0x501d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_InnerCalendarId()
0x5022  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5027  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveWorkingHoursRule(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x502c  stloc.1
0x502d  ldloc.2
0x502e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5033  brtrue.s loc_5005
0x5035  leave.s  loc_504B
0x5037  ldloc.2
0x5038  isinst   [mscorlib]System.IDisposable
0x503d  stloc.s  4
0x503f  ldloc.s  4
0x5041  brfalse.s loc_504A
0x5043  ldloc.s  4
0x5045  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x504a  endfinally
0x504b  ldloc.0
0x504c  brtrue.s loc_505F
0x504e  ldarg.0
0x504f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5054  ldstr    aSmNotWorkingCh// "SM_Not_Working_Check"
0x5059  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x505e  ret
0x505f  ldarg.0
0x5060  ldloc.1
0x5061  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule workingHoursRule)
0x5066  ret
0x5067  ldarg.0
0x5068  ldarg.1
0x5069  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule(int32 checkIndex)
0x506e  brtrue.s loc_5081
0x5070  ldarg.0
0x5071  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5076  ldstr    aSmNotWorkingCh// "SM_Not_Working_Check"
0x507b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5080  ret
0x5081  ldarg.0
0x5082  ldarg.0
0x5083  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x5088  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule workingHoursRule)
0x508d  ret
```
