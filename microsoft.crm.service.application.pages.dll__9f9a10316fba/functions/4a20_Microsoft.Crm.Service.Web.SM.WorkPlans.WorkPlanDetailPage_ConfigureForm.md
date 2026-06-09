# Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::ConfigureForm

- ea: `0x4a20`
- end: `0x4b5a`
- name: `Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::ConfigureForm`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4a20`

## pseudocode

```c

```

## disassembly

```asm
0x4a20  ldarg.0
0x4a21  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x4a26  ldarg.0
0x4a27  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x4a2c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x4a31  ldarg.0
0x4a32  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4a37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4a3c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4a41  ldc.i4   0xFA3
0x4a46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4a4b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4a50  call     instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x4a55  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x4a5a  ldstr    aHolidayschedul// "holidayschedulecalendarid"
0x4a5f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x4a64  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x4a69  ldarg.0
0x4a6a  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4a6f  ldc.i4   0xFA3
0x4a74  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultType(int32)
0x4a79  ldarg.0
0x4a7a  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4a7f  ldc.i4.1
0x4a80  newarr   [mscorlib]System.Int32
0x4a85  dup
0x4a86  ldc.i4.0
0x4a87  ldc.i4   0xFA3
0x4a8c  stelem.i4
0x4a8d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x4a92  ldarg.0
0x4a93  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4a98  ldstr    a349efd53C08148// "349efd53-c081-487a-9a9f-680d0b36c36b"
0x4a9d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4aa2  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultViewId(valuetype [mscorlib]System.Guid)
0x4aa7  ldarg.0
0x4aa8  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4aad  ldc.i4.1
0x4aae  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultViewReadOnly(bool)
0x4ab3  ldarg.0
0x4ab4  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4ab9  ldc.i4.1
0x4aba  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DisableViewPicker(bool)
0x4abf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4ac4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4ac9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4ace  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ad3  ldstr    aCalendar// "calendar"
0x4ad8  ldc.i4.1
0x4ad9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4ade  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x4ae3  ldstr    aHolidayschedul// "holidayschedulecalendarid"
0x4ae8  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x4aed  brfalse.s loc_4B59
0x4aef  ldarg.0
0x4af0  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4af5  ldstr    aHolidayschedul// "holidayschedulecalendarid"
0x4afa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4aff  brfalse.s loc_4B59
0x4b01  ldarg.0
0x4b02  ldc.i4.1
0x4b03  stfld    bool Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_holidaySchedule
0x4b08  ldarg.0
0x4b09  ldarg.0
0x4b0a  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::_calendar
0x4b0f  ldstr    aHolidayschedul// "holidayschedulecalendarid"
0x4b14  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x4b19  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x4b1e  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::holidaySchedule
0x4b23  ldarg.0
0x4b24  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::crmCalendarLookup
0x4b29  ldarg.0
0x4b2a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::holidaySchedule
0x4b2f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x4b34  ldarg.0
0x4b35  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::holidaySchedule
0x4b3a  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x4b3f  ldarg.0
0x4b40  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue Microsoft.Crm.Service.Web.SM.WorkPlans.WorkPlanDetailPage::holidaySchedule
0x4b45  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0x4b4a  callvirt instance string [mscorlib]System.Object::ToString()
0x4b4f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor(string, int32, string)
0x4b54  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x4b59  ret
```
