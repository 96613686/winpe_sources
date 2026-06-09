# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetRelevantActivitiesBetweenTimeframe

- ea: `0x10cd0`
- end: `0x10f27`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetRelevantActivitiesBetweenTimeframe`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10b30`

## callees

- `0x10cd0`
- `0x13170`

## string_xrefs

- `0x10d4d`: `scheduledstart`
- `0x10d55`: `scheduledend`
- `0x10de9`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x10cd0  ldarg.0
0x10cd1  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_cardsTrace
0x10cd6  ldstr    aGetrelevantact// "GetRelevantActivitiesBetweenTimeframe"
0x10cdb  ldarg.0
0x10cdc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_organizationId
0x10ce1  ldstr    aAsynchandlerAc_6// "AsyncHandler::ActivityCardHandler::GetR"...
0x10ce6  ldstr    aStartdate0AndE// "StartDate: {0} and EndDate: {1} for Act"...
0x10ceb  ldarg.1
0x10cec  box      [mscorlib]System.DateTime
0x10cf1  ldarg.2
0x10cf2  box      [mscorlib]System.DateTime
0x10cf7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10cfc  box      [mscorlib]System.DateTime
0x10d01  call     string [mscorlib]System.String::Format(string, object, object, object)
0x10d06  ldsfld   string [mscorlib]System.String::Empty
0x10d0b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10d10  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x10d15  ldc.i4.8
0x10d16  newarr   [mscorlib]System.String
0x10d1b  dup
0x10d1c  ldc.i4.0
0x10d1d  ldstr    aActivityid// "activityid"
0x10d22  stelem.ref
0x10d23  dup
0x10d24  ldc.i4.1
0x10d25  ldstr    aActivitytypeco// "activitytypecode"
0x10d2a  stelem.ref
0x10d2b  dup
0x10d2c  ldc.i4.2
0x10d2d  ldstr    aOwnerid// "ownerid"
0x10d32  stelem.ref
0x10d33  dup
0x10d34  ldc.i4.3
0x10d35  ldstr    aRegardingobjec// "regardingobjectid"
0x10d3a  stelem.ref
0x10d3b  dup
0x10d3c  ldc.i4.4
0x10d3d  ldstr    aSubject// "subject"
0x10d42  stelem.ref
0x10d43  dup
0x10d44  ldc.i4.5
0x10d45  ldstr    aDescription// "description"
0x10d4a  stelem.ref
0x10d4b  dup
0x10d4c  ldc.i4.6
0x10d4d  ldstr    aScheduledstart// "scheduledstart"
0x10d52  stelem.ref
0x10d53  dup
0x10d54  ldc.i4.7
0x10d55  ldstr    aScheduledend// "scheduledend"
0x10d5a  stelem.ref
0x10d5b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x10d60  stloc.0
0x10d61  ldc.i4.s 0xA
0x10d63  newarr   [mscorlib]System.Object
0x10d68  dup
0x10d69  ldc.i4.0
0x10d6a  ldc.i4.s 0xB
0x10d6c  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10d71  stelem.ref
0x10d72  dup
0x10d73  ldc.i4.1
0x10d74  ldc.i4.s 0xD
0x10d76  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10d7b  stelem.ref
0x10d7c  dup
0x10d7d  ldc.i4.2
0x10d7e  ldc.i4.s 0xC
0x10d80  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10d85  stelem.ref
0x10d86  dup
0x10d87  ldc.i4.3
0x10d88  ldc.i4.s 0xE
0x10d8a  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10d8f  stelem.ref
0x10d90  dup
0x10d91  ldc.i4.4
0x10d92  ldc.i4.s 0x15
0x10d94  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10d99  stelem.ref
0x10d9a  dup
0x10d9b  ldc.i4.5
0x10d9c  ldc.i4.8
0x10d9d  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10da2  stelem.ref
0x10da3  dup
0x10da4  ldc.i4.6
0x10da5  ldc.i4.6
0x10da6  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10dab  stelem.ref
0x10dac  dup
0x10dad  ldc.i4.7
0x10dae  ldc.i4.s 0xF
0x10db0  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10db5  stelem.ref
0x10db6  dup
0x10db7  ldc.i4.8
0x10db8  ldc.i4.7
0x10db9  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10dbe  stelem.ref
0x10dbf  dup
0x10dc0  ldc.i4.s 9
0x10dc2  ldc.i4.s 0x64
0x10dc4  box      Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType
0x10dc9  stelem.ref
0x10dca  stloc.1
0x10dcb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x10dd0  dup
0x10dd1  ldstr    aActivitypointe// "activitypointer"
0x10dd6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x10ddb  dup
0x10ddc  ldloc.0
0x10ddd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x10de2  stloc.2
0x10de3  ldloc.2
0x10de4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x10de9  ldstr    aScheduledend// "scheduledend"
0x10dee  ldc.i4.s 0xA
0x10df0  ldc.i4.2
0x10df1  newarr   [mscorlib]System.String
0x10df6  dup
0x10df7  ldc.i4.0
0x10df8  ldarga.s 1
0x10dfa  call     instance string [mscorlib]System.DateTime::ToString()
0x10dff  stelem.ref
0x10e00  dup
0x10e01  ldc.i4.1
0x10e02  ldarga.s 2
0x10e04  call     instance string [mscorlib]System.DateTime::ToString()
0x10e09  stelem.ref
0x10e0a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10e0f  ldloc.2
0x10e10  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x10e15  ldstr    aStatecode// "statecode"
0x10e1a  ldc.i4.1
0x10e1b  ldc.i4.1
0x10e1c  newarr   [mscorlib]System.Object
0x10e21  dup
0x10e22  ldc.i4.0
0x10e23  ldc.i4.2
0x10e24  box      [mscorlib]System.Int32
0x10e29  stelem.ref
0x10e2a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10e2f  ldloc.2
0x10e30  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x10e35  ldstr    aStatecode// "statecode"
0x10e3a  ldc.i4.1
0x10e3b  ldc.i4.1
0x10e3c  newarr   [mscorlib]System.Object
0x10e41  dup
0x10e42  ldc.i4.0
0x10e43  ldc.i4.1
0x10e44  box      [mscorlib]System.Int32
0x10e49  stelem.ref
0x10e4a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10e4f  ldloc.2
0x10e50  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x10e55  ldstr    aActivitytypeco// "activitytypecode"
0x10e5a  ldc.i4.s 9
0x10e5c  call     class [mscorlib]System.Collections.Generic.List`1<object> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityTypeCodesToIgnore::get_Codes()
0x10e61  call     T0x2B000026
0x10e66  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10e6b  ldloc.2
0x10e6c  ldstr    aActioncard// "actioncard"
0x10e71  ldstr    aActivityid// "activityid"
0x10e76  ldstr    aRegardingobjec// "regardingobjectid"
0x10e7b  ldc.i4.1
0x10e7c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x10e81  dup
0x10e82  ldstr    aActivityaction// "ActivityActionCard"
0x10e87  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::set_EntityAlias(string)
0x10e8c  dup
0x10e8d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x10e92  ldstr    aCardtype// "cardtype"
0x10e97  ldc.i4.8
0x10e98  ldloc.1
0x10e99  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10e9e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x10ea3  ldstr    aState// "state"
0x10ea8  ldc.i4.1
0x10ea9  ldc.i4.1
0x10eaa  newarr   [mscorlib]System.Object
0x10eaf  dup
0x10eb0  ldc.i4.0
0x10eb1  ldc.i4.2
0x10eb2  box      [mscorlib]System.Int32
0x10eb7  stelem.ref
0x10eb8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10ebd  ldloc.2
0x10ebe  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x10ec3  ldstr    aActivityaction// "ActivityActionCard"
0x10ec8  ldstr    aRegardingobjec// "regardingobjectid"
0x10ecd  ldc.i4.s 0xC
0x10ecf  ldc.i4.0
0x10ed0  newarr   [mscorlib]System.Object
0x10ed5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x10eda  ldarg.0
0x10edb  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_crmService
0x10ee0  ldloc.2
0x10ee1  call     T0x2B000027
0x10ee6  stloc.3
0x10ee7  leave.s  loc_10F25
0x10ee9  stloc.s  4
0x10eeb  ldarg.0
0x10eec  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_cardsTrace
0x10ef1  ldarg.0
0x10ef2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_organizationId
0x10ef7  ldstr    aAsynchandlerAc_7// "AsyncHandler::ActionCardHandler::GetAct"...
0x10efc  ldc.i4.6
0x10efd  ldstr    aGfailedToRelav// "GFailed to relavant activity cards data"...
0x10f02  ldloc.s  4
0x10f04  callvirt instance string [mscorlib]System.Object::ToString()
0x10f09  call     string [mscorlib]System.String::Format(string, object)
0x10f0e  ldsfld   string [mscorlib]System.String::Empty
0x10f13  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10f18  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x10f1d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x10f22  stloc.3
0x10f23  leave.s  loc_10F25
0x10f25  ldloc.3
0x10f26  ret
```
