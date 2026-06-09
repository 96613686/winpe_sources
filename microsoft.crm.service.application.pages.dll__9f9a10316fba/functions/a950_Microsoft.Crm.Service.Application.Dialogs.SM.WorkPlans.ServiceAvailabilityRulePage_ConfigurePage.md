# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::ConfigurePage

- ea: `0xa950`
- end: `0xa9ee`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::ConfigurePage`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xaa10`
- `0xabe0`

## string_xrefs

- `0xa981`: `LOCID_SELECT_SERVICE_TO_RESTRICT`
- `0xa98c`: `Service_Restriction_Select_Service`

## pseudocode

```c

```

## disassembly

```asm
0xa950  ldarg.0
0xa951  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xa956  ldarg.0
0xa957  ldstr    aCalendarrule// "calendarrule"
0xa95c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa961  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa966  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xa96b  ldarg.0
0xa96c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa971  ldstr    aStaticControls_6// "/_static/_controls/startendduration/sta"...
0xa976  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xa97b  ldarg.0
0xa97c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa981  ldstr    aLocidSelectSer// "LOCID_SELECT_SERVICE_TO_RESTRICT"
0xa986  ldarg.0
0xa987  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa98c  ldstr    aServiceRestric// "Service_Restriction_Select_Service"
0xa991  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa996  ldc.i4.0
0xa997  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xa99c  ldarg.0
0xa99d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xa9a2  ldstr    aLocidRuleExcee// "LOCID_RULE_EXCEEDS_WORKING_HOURS"
0xa9a7  ldarg.0
0xa9a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xa9ad  ldstr    aSmRuleExceedsW// "SM_Rule_Exceeds_Working_Hours"
0xa9b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa9b7  ldc.i4.0
0xa9b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xa9bd  ldarg.0
0xa9be  ldarg.0
0xa9bf  ldstr    aId_0// "Id"
0xa9c4  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::AssignStringQueryStringGuid(string parameter)
0xa9c9  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::CalendarRuleId
0xa9ce  ldarg.0
0xa9cf  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::serviceid
0xa9d4  ldc.i4.1
0xa9d5  newarr   [mscorlib]System.Int32
0xa9da  dup
0xa9db  ldc.i4.0
0xa9dc  ldc.i4   0xFA1
0xa9e1  stelem.i4
0xa9e2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0xa9e7  ldarg.0
0xa9e8  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ServiceAvailabilityRulePage::InitDialog()
0xa9ed  ret
```
