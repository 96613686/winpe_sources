# Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::RetrieveActivitiesForCalendar

- ea: `0x89e0`
- end: `0x8ac2`
- name: `Microsoft.Crm.Service.Web.Calendar.CalendarPageHelper::RetrieveActivitiesForCalendar`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b40`
- `0x8fe0`
- `0x9250`

## string_xrefs

- `0x8a01`: `scheduledstart`
- `0x8a11`: `scheduledend`
- `0x8a21`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x89e0  ldstr    aActivitypointe// "activitypointer"
0x89e5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x89ea  stloc.0
0x89eb  ldloc.0
0x89ec  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x89f1  ldstr    aActivityid// "activityid"
0x89f6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x89fb  ldloc.0
0x89fc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x8a01  ldstr    aScheduledstart// "scheduledstart"
0x8a06  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x8a0b  ldloc.0
0x8a0c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x8a11  ldstr    aScheduledend// "scheduledend"
0x8a16  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x8a1b  ldloc.0
0x8a1c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x8a21  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x8a26  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x8a2b  ldloc.0
0x8a2c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x8a31  ldstr    aSubject// "subject"
0x8a36  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x8a3b  ldloc.0
0x8a3c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x8a41  ldstr    aActivitytypeco// "activitytypecode"
0x8a46  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x8a4b  ldloc.0
0x8a4c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x8a51  ldstr    aInstancetypeco// "instancetypecode"
0x8a56  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x8a5b  ldloc.0
0x8a5c  ldc.i4.0
0x8a5d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_NoLock(bool)
0x8a62  ldloc.0
0x8a63  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x8a68  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x8a6d  ldloc.0
0x8a6e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x8a73  ldstr    aInstancetypeco// "instancetypecode"
0x8a78  ldc.i4.1
0x8a79  ldc.i4.1
0x8a7a  box      [mscorlib]System.Int32
0x8a7f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x8a84  ldloc.0
0x8a85  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x8a8a  ldstr    aActivitytypeco// "activitytypecode"
0x8a8f  ldc.i4.3
0x8a90  ldc.i4   0x2710
0x8a95  box      [mscorlib]System.Int32
0x8a9a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x8a9f  ldc.i4.4
0x8aa0  newarr   [mscorlib]System.Int32
0x8aa5  dup
0x8aa6  ldtoken  valuetype __StaticArrayInitTypeSize=16 <PrivateImplementationDetails>::'10DFD1A61ABBF67DB3CFA637EEAEFA30C4038E77'
0x8aab  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x8ab0  stloc.1
0x8ab1  ldarg.0
0x8ab2  ldloc.1
0x8ab3  ldarg.1
0x8ab4  ldarg.2
0x8ab5  ldc.i4.1
0x8ab6  ldloc.0
0x8ab7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8abc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveByParty(valuetype [mscorlib]System.Guid, int32[], valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, bool, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8ac1  ret
```
