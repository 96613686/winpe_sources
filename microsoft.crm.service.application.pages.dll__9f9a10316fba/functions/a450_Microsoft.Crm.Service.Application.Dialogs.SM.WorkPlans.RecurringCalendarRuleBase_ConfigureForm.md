# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::ConfigureForm

- ea: `0xa450`
- end: `0xa617`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::ConfigureForm`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa450`
- `0xa7e0`
- `0xbf90`
- `0xbfb0`
- `0xbff0`
- `0xc020`
- `0xc060`
- `0xc090`
- `0xc0d0`
- `0xc110`
- `0xc140`
- `0xc150`
- `0xc450`
- `0xc460`
- `0xc470`
- `0xc490`
- `0xc4c0`

## pseudocode

```c

```

## disassembly

```asm
0xa450  ldarg.0
0xa451  ldarg.0
0xa452  ldstr    aResourceid// "resourceId"
0xa457  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xa45c  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_ResourceId(string value)
0xa461  ldarg.0
0xa462  ldarg.0
0xa463  ldstr    aCalendarid// "calendarId"
0xa468  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xa46d  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0xa472  ldarg.0
0xa473  ldarg.0
0xa474  ldstr    aInnercalendari// "innerCalendarId"
0xa479  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignQueryStringGuid(string parameter)
0xa47e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_innerCalendarId
0xa483  ldarg.0
0xa484  ldarg.0
0xa485  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xa48a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xa48f  ldstr    aId_0// "Id"
0xa494  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa499  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarRuleId(string value)
0xa49e  ldarg.0
0xa49f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xa4a4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xa4a9  ldstr    aCtype// "cType"
0xa4ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa4b3  brfalse.s loc_A4D5
0xa4b5  ldarg.0
0xa4b6  ldarg.0
0xa4b7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xa4bc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xa4c1  ldstr    aCtype// "cType"
0xa4c6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa4cb  callvirt instance string [mscorlib]System.Object::ToString()
0xa4d0  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarType(string value)
0xa4d5  ldarg.0
0xa4d6  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0xa4db  brfalse.s loc_A509
0xa4dd  ldarg.0
0xa4de  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0xa4e3  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa4e8  ldc.i4.0
0xa4e9  ble.s    loc_A509
0xa4eb  ldarg.0
0xa4ec  ldarg.0
0xa4ed  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0xa4f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa4f7  ldarg.0
0xa4f8  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ObjectTypeCode()
0xa4fd  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::FindOrCreateResourceCalendar(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32)
0xa502  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0xa507  br.s     loc_A564
0xa509  ldarg.0
0xa50a  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId()
0xa50f  brfalse.s loc_A51E
0xa511  ldarg.0
0xa512  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId()
0xa517  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa51c  brtrue.s loc_A564
0xa51e  ldarg.0
0xa51f  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarType()
0xa524  stloc.0
0xa525  ldloc.0
0xa526  ldstr    aBc// "bc"
0xa52b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa530  brtrue.s loc_A541
0xa532  ldloc.0
0xa533  ldstr    aHs// "hs"
0xa538  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa53d  brtrue.s loc_A553
0xa53f  br.s     loc_A564
0xa541  ldarg.0
0xa542  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa547  call     string [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::GetOrgCalendarId(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa54c  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0xa551  br.s     loc_A564
0xa553  ldarg.0
0xa554  ldarg.0
0xa555  ldstr    aHolidaycalenda// "holidayCalendarId"
0xa55a  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::AssignStringQueryStringGuid(string parameter)
0xa55f  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_CalendarId(string value)
0xa564  ldarg.0
0xa565  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId()
0xa56a  brfalse.s loc_A5C8
0xa56c  ldarg.0
0xa56d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_innerCalendarId
0xa572  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa577  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa57c  brfalse.s loc_A5C8
0xa57e  ldarg.0
0xa57f  ldarg.0
0xa580  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::RetrieveWorkingHoursRule()
0xa585  call     instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::set_WorkingHoursRule(class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule value)
0xa58a  ldarg.0
0xa58b  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xa590  brfalse.s loc_A5BA
0xa592  ldarg.0
0xa593  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xa598  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa59d  ldc.i4.0
0xa59e  ble.s    loc_A5BA
0xa5a0  ldarg.0
0xa5a1  ldc.i4.1
0xa5a2  stfld    bool Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_editMode
0xa5a7  ldarg.0
0xa5a8  ldarg.0
0xa5a9  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::RetrieveRecurrenceRule()
0xa5ae  stfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_recurringRule
0xa5b3  ldarg.0
0xa5b4  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::EditCalendarRule()
0xa5b9  ret
0xa5ba  ldarg.0
0xa5bb  ldc.i4.0
0xa5bc  stfld    bool Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_editMode
0xa5c1  ldarg.0
0xa5c2  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::NewCalendarRule()
0xa5c7  ret
0xa5c8  ldarg.0
0xa5c9  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xa5ce  brfalse.s loc_A609
0xa5d0  ldarg.0
0xa5d1  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarRuleId()
0xa5d6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa5db  ldc.i4.0
0xa5dc  ble.s    loc_A609
0xa5de  ldarg.0
0xa5df  ldarg.0
0xa5e0  call     instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::RetrieveRecurrenceRule()
0xa5e5  stfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_recurringRule
0xa5ea  ldarg.0
0xa5eb  ldarg.0
0xa5ec  ldfld    class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_recurringRule
0xa5f1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_InnerCalendarId()
0xa5f6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_innerCalendarId
0xa5fb  ldarg.0
0xa5fc  ldc.i4.1
0xa5fd  stfld    bool Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_editMode
0xa602  ldarg.0
0xa603  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::EditCalendarRule()
0xa608  ret
0xa609  ldarg.0
0xa60a  ldc.i4.0
0xa60b  stfld    bool Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.RecurringCalendarRuleBase::_editMode
0xa610  ldarg.0
0xa611  callvirt instance void Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::NewCalendarRule()
0xa616  ret
```
