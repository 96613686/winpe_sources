# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderAltWorkingHoursText

- ea: `0x5090`
- end: `0x50b7`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderAltWorkingHoursText`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x4f00`
- `0x5090`
- `0x5540`

## pseudocode

```c

```

## disassembly

```asm
0x5090  ldarg.0
0x5091  ldarg.1
0x5092  call     instance bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::IsDayInRule(int32 checkIndex)
0x5097  brfalse.s loc_50AA
0x5099  ldarg.0
0x509a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x509f  ldstr    aSmNotWorkingCh// "SM_Not_Working_Check"
0x50a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x50a9  ret
0x50aa  ldarg.0
0x50ab  ldarg.0
0x50ac  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_workingHoursRule
0x50b1  call     instance string Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::RenderWorkingHoursText(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule workingHoursRule)
0x50b6  ret
```
