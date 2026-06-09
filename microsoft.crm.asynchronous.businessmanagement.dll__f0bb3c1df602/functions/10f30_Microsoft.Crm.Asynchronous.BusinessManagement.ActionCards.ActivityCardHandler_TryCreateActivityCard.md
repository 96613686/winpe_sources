# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::TryCreateActivityCard

- ea: `0x10f30`
- end: `0x11036`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::TryCreateActivityCard`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10b30`

## callees

- `0x10f30`
- `0x11390`
- `0x114b0`
- `0x11bc0`
- `0x128f0`
- `0x12940`
- `0x12990`
- `0x129c0`
- `0x129e0`
- `0x12a10`
- `0x12a30`
- `0x12a50`
- `0x12de0`
- `0x12e40`
- `0x12ea0`
- `0x12fd0`
- `0x12ff0`
- `0x13010`
- `0x13030`
- `0x13050`
- `0x13070`
- `0x13090`
- `0x130d0`

## string_xrefs

- `0x10fff`: `AsyncHandler::ActionCardHandler::CreateActionCard`
- `0x11005`: `Create Activity Card failed for the activity : {0}.\n Error Details: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x10f30  ldarg.1
0x10f31  ldarg.0
0x10f32  ldfld    class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_actionCardHandler
0x10f37  ldarg.1
0x10f38  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x10f3d  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler::GetEntityTypeCode(string entityLogicalName)
0x10f42  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activity, int32 activityTypeCode)
0x10f47  stloc.0
0x10f48  ldarg.1
0x10f49  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity parentEntity)
0x10f4e  stloc.1
0x10f4f  ldloc.1
0x10f50  ldarg.2
0x10f51  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_AssociatedActionCardTypeId()
0x10f56  ldarg.2
0x10f57  callvirt instance bool Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_Visibility()
0x10f5c  ldarg.2
0x10f5d  callvirt instance valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_Priority()
0x10f62  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetCardTypeInformation(valuetype [mscorlib]System.Guid cardTypeId, bool visibility, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority)
0x10f67  ldloc.1
0x10f68  ldarg.2
0x10f69  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_StartDate()
0x10f6e  ldarg.2
0x10f6f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_EndDate()
0x10f74  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetActionCardDateRange(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0x10f79  ldloc.1
0x10f7a  ldarg.0
0x10f7b  ldloc.0
0x10f7c  ldarg.2
0x10f7d  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_EntityTypeCode()
0x10f82  ldarg.2
0x10f83  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_CardBodyResourceId()
0x10f88  ldarg.2
0x10f89  callvirt instance valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_CardType()
0x10f8e  call     instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetReferenceTokenForActivityCard(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity activity, int32 typeCode, string bodyResourceId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x10f93  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetTokenIformation(string token)
0x10f98  ldloc.1
0x10f99  ldloc.0
0x10f9a  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_Subject()
0x10f9f  ldloc.0
0x10fa0  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_Description()
0x10fa5  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetTitleAndDescription(string title, string description)
0x10faa  ldloc.1
0x10fab  ldarg.0
0x10fac  ldloc.0
0x10fad  ldarg.2
0x10fae  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig::get_EntityTypeCode()
0x10fb3  call     instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetDataForActivityCards(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity activity, int32 entityTypeCode)
0x10fb8  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetDataInformation(string data)
0x10fbd  ldarg.1
0x10fbe  ldstr    aRegardingobjec// "regardingobjectid"
0x10fc3  callvirt T0x2B000013
0x10fc8  stloc.2
0x10fc9  ldloc.2
0x10fca  brfalse.s loc_10FD3
0x10fcc  ldloc.1
0x10fcd  ldloc.2
0x10fce  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetParentRegardingObjId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference parentRegardingObject)
0x10fd3  ldarg.0
0x10fd4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_crmService
0x10fd9  ldloc.1
0x10fda  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::get_Entity()
0x10fdf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x10fe4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10fe9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10fee  stloc.3
0x10fef  leave.s  loc_11034
0x10ff1  stloc.s  4
0x10ff3  ldarg.0
0x10ff4  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_cardsTrace
0x10ff9  ldarg.0
0x10ffa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_organizationId
0x10fff  ldstr    aAsynchandlerAc_8// "AsyncHandler::ActionCardHandler::Create"...
0x11004  ldc.i4.6
0x11005  ldstr    aCreateActivity// "Create Activity Card failed for the act"...
0x1100a  ldarg.1
0x1100b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x11010  box      [mscorlib]System.Guid
0x11015  ldloc.s  4
0x11017  callvirt instance string [mscorlib]System.Object::ToString()
0x1101c  call     string [mscorlib]System.String::Format(string, object, object)
0x11021  ldsfld   string [mscorlib]System.String::Empty
0x11026  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1102b  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x11030  leave.s  loc_11032
0x11032  ldc.i4.0
0x11033  ret
0x11034  ldloc.3
0x11035  ret
```
