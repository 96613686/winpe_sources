# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::TryCreateNoActivityActionCard

- ea: `0x12000`
- end: `0x120e8`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::TryCreateNoActivityActionCard`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x11c70`

## callees

- `0x12000`
- `0x121a0`
- `0x128f0`
- `0x12940`
- `0x12990`
- `0x129c0`
- `0x12a50`
- `0x133c0`
- `0x13400`
- `0x13440`
- `0x13480`

## string_xrefs

- `0x120aa`: `AsyncHandler::NoActivityCardHandler::TryCreateNoActivityActionCard`

## pseudocode

```c

```

## disassembly

```asm
0x12000  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x12005  stloc.2
0x12006  ldloca.s 2
0x12008  ldc.r8   7.0
0x12011  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x12016  stloc.2
0x12017  ldloca.s 2
0x12019  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1201e  stloc.0
0x1201f  ldloca.s 0
0x12021  ldc.r8   90.0
0x1202a  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x1202f  stloc.1
0x12030  ldarg.1
0x12031  callvirt instance class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_GetEntitySubject()
0x12036  ldarg.2
0x12037  callvirt instance var<u1> class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, string>::Invoke(void)
0x1203c  stloc.3
0x1203d  ldarg.2
0x1203e  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity parentEntity)
0x12043  stloc.s  4
0x12045  ldloc.s  4
0x12047  ldarg.1
0x12048  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_AssociatedActionCardTypeId()
0x1204d  ldc.i4.0
0x1204e  ldc.i4   0x258
0x12053  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetCardTypeInformation(valuetype [mscorlib]System.Guid cardTypeId, bool visibility, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority)
0x12058  ldloc.s  4
0x1205a  ldloc.0
0x1205b  ldloc.1
0x1205c  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetActionCardDateRange(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0x12061  ldloc.s  4
0x12063  ldarg.0
0x12064  ldarg.2
0x12065  ldarg.1
0x12066  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityTypeCode()
0x1206b  ldloc.3
0x1206c  ldarg.1
0x1206d  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_CardBodyResourceId()
0x12072  call     instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetReferenceTokenForNonActivityCard(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, int32 typeCode, string entitySubject, string bodyResourceId)
0x12077  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetTokenIformation(string token)
0x1207c  ldarg.0
0x1207d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_crmService
0x12082  ldloc.s  4
0x12084  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::get_Entity()
0x12089  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x1208e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12093  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12098  stloc.s  5
0x1209a  leave.s  loc_120E5
0x1209c  stloc.s  6
0x1209e  ldarg.0
0x1209f  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_cardsTrace
0x120a4  ldarg.0
0x120a5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_organizationId
0x120aa  ldstr    aAsynchandlerNo_0// "AsyncHandler::NoActivityCardHandler::Tr"...
0x120af  ldc.i4.4
0x120b0  ldstr    aFailedToGenera_0// " failed to generate card for the entity"...
0x120b5  ldarg.2
0x120b6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x120bb  ldarg.2
0x120bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x120c1  box      [mscorlib]System.Guid
0x120c6  ldloc.s  6
0x120c8  callvirt instance string [mscorlib]System.Object::ToString()
0x120cd  call     string [mscorlib]System.String::Format(string, object, object, object)
0x120d2  ldsfld   string [mscorlib]System.String::Empty
0x120d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x120dc  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x120e1  leave.s  loc_120E3
0x120e3  ldc.i4.0
0x120e4  ret
0x120e5  ldloc.s  5
0x120e7  ret
```
