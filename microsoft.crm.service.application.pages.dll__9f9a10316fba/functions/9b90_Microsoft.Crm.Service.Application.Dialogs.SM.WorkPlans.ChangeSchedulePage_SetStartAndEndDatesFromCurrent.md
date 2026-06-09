# Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::SetStartAndEndDatesFromCurrent

- ea: `0x9b90`
- end: `0x9ced`
- name: `Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::SetStartAndEndDatesFromCurrent`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x9a80`

## callees

- `0x9b90`
- `0xbf90`
- `0xbfb0`
- `0xc020`

## pseudocode

```c

```

## disassembly

```asm
0x9b90  ldarg.0
0x9b91  ldarg.0
0x9b92  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9b97  ldstr    aSmNoEndDate// "SM_No_End_Date"
0x9b9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ba1  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_endDate
0x9ba6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9bab  stloc.0
0x9bac  ldarg.0
0x9bad  call     instance int32 Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ObjectTypeCode()
0x9bb2  ldc.i4   0x47E
0x9bb7  bne.un.s loc_9C0C
0x9bb9  ldarg.0
0x9bba  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0x9bbf  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9bc4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9bc9  ldc.i4.1
0x9bca  newarr   [mscorlib]System.String
0x9bcf  dup
0x9bd0  ldc.i4.0
0x9bd1  ldstr    aCalendarid_1// "calendarid"
0x9bd6  stelem.ref
0x9bd7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveBookableResource(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, string[])
0x9bdc  stloc.3
0x9bdd  ldloc.3
0x9bde  ldstr    aCalendarid_1// "calendarid"
0x9be3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x9be8  brfalse.s loc_9C3F
0x9bea  ldloc.3
0x9beb  ldstr    aCalendarid_1// "calendarid"
0x9bf0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x9bf5  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x9bfa  stloc.s  4
0x9bfc  ldloca.s 0
0x9bfe  ldloc.s  4
0x9c00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x9c05  call     instance void [mscorlib]System.Guid::.ctor(string)
0x9c0a  br.s     loc_9C3F
0x9c0c  ldarg.0
0x9c0d  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_ResourceId()
0x9c12  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c17  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9c1c  ldc.i4.1
0x9c1d  newarr   [mscorlib]System.String
0x9c22  dup
0x9c23  ldc.i4.0
0x9c24  ldstr    aCalendarid_1// "calendarid"
0x9c29  stelem.ref
0x9c2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveResource(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, string[])
0x9c2f  ldstr    aCalendarid_1// "calendarid"
0x9c34  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x9c39  unbox.any [mscorlib]System.Guid
0x9c3e  stloc.0
0x9c3f  ldloc.0
0x9c40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9c45  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9c4a  ldarg.0
0x9c4b  call     instance string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.WorkCalendarRuleBase::get_CalendarId()
0x9c50  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c55  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9c5a  call     class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.SMWorkPlans::RetrieveCalendar(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9c5f  stloc.1
0x9c60  ldloc.1
0x9c61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x9c66  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c6b  callvirt instance class [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.Calendar::FindCalendarRuleByInnerCalendarId(valuetype [mscorlib]System.Guid)
0x9c70  stloc.2
0x9c71  ldloc.2
0x9c72  brfalse.s loc_9CE2
0x9c74  ldloc.2
0x9c75  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_EffectiveIntervalEnd()
0x9c7a  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x9c7f  stloc.s  5
0x9c81  ldloca.s 5
0x9c83  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x9c88  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x9c8d  brfalse.s loc_9CB8
0x9c8f  ldarg.0
0x9c90  ldloc.2
0x9c91  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_EffectiveIntervalEnd()
0x9c96  stloc.s  5
0x9c98  ldloca.s 5
0x9c9a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9c9f  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x9ca4  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x9ca9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9cae  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x9cb3  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_endDate
0x9cb8  ldarg.0
0x9cb9  ldloc.2
0x9cba  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.CalendarRule::get_Start()
0x9cbf  stloc.s  5
0x9cc1  ldloca.s 5
0x9cc3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9cc8  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x9ccd  callvirt instance string [mscorlib]System.Globalization.DateTimeFormatInfo::get_ShortDatePattern()
0x9cd2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x9cd7  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x9cdc  stfld    string Microsoft.Crm.Service.Application.Dialogs.SM.WorkPlans.ChangeSchedulePage::_startDate
0x9ce1  ret
0x9ce2  ldstr    aWorkplanRecurr// "Workplan recurring rule was not found."
0x9ce7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9cec  throw
```
