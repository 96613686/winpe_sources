# Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::ConfigureFormHandler

- ea: `0xcfb0`
- end: `0xd0a6`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::ConfigureFormHandler`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xcfb0`
- `0xd0b0`
- `0xd150`

## pseudocode

```c

```

## disassembly

```asm
0xcfb0  ldarg.0
0xcfb1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xcfb6  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0xcfbb  ldarg.0
0xcfbc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xcfc1  ldarg.0
0xcfc2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xcfc7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xcfcc  dup
0xcfcd  ldstr    aRouteoption// "routeoption"
0xcfd2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xcfd7  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl
0xcfdc  stloc.0
0xcfdd  ldloc.0
0xcfde  ldarg.0
0xcfdf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcfe4  ldstr    aRoutingruleite// "RoutingRuleItemForm.RouteOption.Queue"
0xcfe9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcfee  ldc.i4.0
0xcfef  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl::AddItem(string, int32)
0xcff4  ldloc.0
0xcff5  ldarg.0
0xcff6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0xcffb  ldstr    aRoutingruleite_0// "RoutingRuleItemForm.RouteOption.UserOrT"...
0xd000  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd005  ldc.i4.1
0xd006  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RadioControl::AddItem(string, int32)
0xd00b  dup
0xd00c  ldstr    aRoutedqueueid// "routedqueueid"
0xd011  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd016  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl
0xd01b  stloc.1
0xd01c  ldstr    aAssignobjectid// "assignobjectid"
0xd021  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd026  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl
0xd02b  stloc.2
0xd02c  ldloc.1
0xd02d  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0xd032  brtrue.s loc_D03C
0xd034  ldloc.2
0xd035  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0xd03a  brfalse.s loc_D044
0xd03c  ldloc.1
0xd03d  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0xd042  brfalse.s loc_D052
0xd044  ldloc.0
0xd045  ldc.i4.0
0xd046  box      [mscorlib]System.Int32
0xd04b  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd050  br.s     loc_D05E
0xd052  ldloc.0
0xd053  ldc.i4.1
0xd054  box      [mscorlib]System.Int32
0xd059  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd05e  ldarg.0
0xd05f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd064  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm
0xd069  stloc.3
0xd06a  ldc.i4.0
0xd06b  stloc.s  4
0xd06d  ldarg.0
0xd06e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd073  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd078  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd07d  brtrue.s loc_D092
0xd07f  ldarg.0
0xd080  ldarg.0
0xd081  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd086  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd08b  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::RetrieveRoutingRuleStateCode(string routingRuleItemId)
0xd090  stloc.s  4
0xd092  ldarg.0
0xd093  ldloc.3
0xd094  ldstr    a2e8694889a6344// "{2e869488-9a63-446e-a8e0-ef0aaf298018}"
0xd099  ldstr    aAppconditionbu_1// "appConditionBuilder"
0xd09e  ldloc.s  4
0xd0a0  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.RoutingRuleItemRecordPageHandler::SetSectionCondition(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string ControlId, bool controlDisabled)
0xd0a5  ret
```
