# Microsoft.Crm.ObjectModel.GenericActivityServiceBase::CreateOwnerAndRegardingParties

- ea: `0x5d950`
- end: `0x5db05`
- name: `Microsoft.Crm.ObjectModel.GenericActivityServiceBase::CreateOwnerAndRegardingParties`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d920`

## callees

- `0x5d950`
- `0x5e2b0`
- `0x5e2c0`
- `0x5e2d0`
- `0x1efa10`

## string_xrefs

- `0x5d950`: `ActivityPartyService`
- `0x5d9d6`: `scheduledstart`
- `0x5d9dc`: `scheduledstart`
- `0x5dad0`: `scheduledstart`
- `0x5dad6`: `scheduledstart`
- `0x5d9ec`: `scheduledend`
- `0x5d9f2`: `scheduledend`
- `0x5dae6`: `scheduledend`
- `0x5daec`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x5d950  ldstr    aActivitypartys// "ActivityPartyService"
0x5d955  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::BusinessProcessReflectionUtiltity(string)
0x5d95a  castclass Microsoft.Crm.ObjectModel.Utility.IActivityPartyService
0x5d95f  stloc.0
0x5d960  ldarg.3
0x5d961  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5d966  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty::.ctor(valuetype [mscorlib]System.Guid)
0x5d96b  stloc.1
0x5d96c  ldloc.1
0x5d96d  ldstr    aActivitypartyi// "activitypartyid"
0x5d972  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5d977  box      [mscorlib]System.Guid
0x5d97c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d981  ldloc.1
0x5d982  ldstr    aActivityid_0// "activityid"
0x5d987  ldarg.1
0x5d988  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5d98d  box      [mscorlib]System.Guid
0x5d992  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d997  ldloc.1
0x5d998  ldstr    aPartyid// "partyid"
0x5d99d  ldarg.2
0x5d99e  ldstr    aOwnerid// "ownerid"
0x5d9a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d9a8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d9ad  ldloc.1
0x5d9ae  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x5d9b3  ldarg.2
0x5d9b4  ldstr    aOwneridtype// "owneridtype"
0x5d9b9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d9be  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d9c3  ldloc.1
0x5d9c4  ldstr    aParticipationt// "participationtypemask"
0x5d9c9  ldc.i4.s 9
0x5d9cb  box      [mscorlib]System.Int32
0x5d9d0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d9d5  ldloc.1
0x5d9d6  ldstr    aScheduledstart// "scheduledstart"
0x5d9db  ldarg.2
0x5d9dc  ldstr    aScheduledstart// "scheduledstart"
0x5d9e1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d9e6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d9eb  ldloc.1
0x5d9ec  ldstr    aScheduledend// "scheduledend"
0x5d9f1  ldarg.2
0x5d9f2  ldstr    aScheduledend// "scheduledend"
0x5d9f7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d9fc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5da01  ldloc.0
0x5da02  ldloc.1
0x5da03  ldarg.3
0x5da04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5da09  pop
0x5da0a  ldarg.2
0x5da0b  ldarg.0
0x5da0c  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingIdField()
0x5da11  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5da16  brtrue   loc_5DB04
0x5da1b  ldarg.3
0x5da1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5da21  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty::.ctor(valuetype [mscorlib]System.Guid)
0x5da26  stloc.2
0x5da27  ldloc.2
0x5da28  ldstr    aActivitypartyi// "activitypartyid"
0x5da2d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5da32  box      [mscorlib]System.Guid
0x5da37  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5da3c  ldloc.2
0x5da3d  ldstr    aPartyid// "partyid"
0x5da42  ldarg.2
0x5da43  ldarg.0
0x5da44  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingIdField()
0x5da49  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5da4e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5da53  ldarg.0
0x5da54  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingTypeField()
0x5da59  brfalse.s loc_5DA92
0x5da5b  ldarg.2
0x5da5c  ldarg.0
0x5da5d  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingTypeField()
0x5da62  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5da67  stloc.3
0x5da68  ldloc.3
0x5da69  brfalse.s loc_5DA87
0x5da6b  ldloc.3
0x5da6c  unbox.any [mscorlib]System.Int32
0x5da71  stloc.s  4
0x5da73  ldloc.2
0x5da74  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x5da79  ldloc.s  4
0x5da7b  box      [mscorlib]System.Int32
0x5da80  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5da85  br.s     loc_5DAA8
0x5da87  ldstr    aWhenCreatingAn// "When creating an activity, regarding ob"...
0x5da8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5da91  throw
0x5da92  ldloc.2
0x5da93  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x5da98  ldarg.0
0x5da99  callvirt instance int32 Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingType()
0x5da9e  box      [mscorlib]System.Int32
0x5daa3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5daa8  ldloc.2
0x5daa9  ldstr    aActivityid_0// "activityid"
0x5daae  ldarg.1
0x5daaf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5dab4  box      [mscorlib]System.Guid
0x5dab9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5dabe  ldloc.2
0x5dabf  ldstr    aParticipationt// "participationtypemask"
0x5dac4  ldc.i4.8
0x5dac5  box      [mscorlib]System.Int32
0x5daca  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5dacf  ldloc.2
0x5dad0  ldstr    aScheduledstart// "scheduledstart"
0x5dad5  ldarg.2
0x5dad6  ldstr    aScheduledstart// "scheduledstart"
0x5dadb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dae0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5dae5  ldloc.2
0x5dae6  ldstr    aScheduledend// "scheduledend"
0x5daeb  ldarg.2
0x5daec  ldstr    aScheduledend// "scheduledend"
0x5daf1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5daf6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5dafb  ldloc.0
0x5dafc  ldloc.2
0x5dafd  ldarg.3
0x5dafe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5db03  pop
0x5db04  ret
```
