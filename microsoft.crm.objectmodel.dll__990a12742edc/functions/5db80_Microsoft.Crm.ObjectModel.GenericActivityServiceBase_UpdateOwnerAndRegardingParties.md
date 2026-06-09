# Microsoft.Crm.ObjectModel.GenericActivityServiceBase::UpdateOwnerAndRegardingParties

- ea: `0x5db80`
- end: `0x5df9d`
- name: `Microsoft.Crm.ObjectModel.GenericActivityServiceBase::UpdateOwnerAndRegardingParties`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5cd50`

## callees

- `0x5db80`
- `0x5e2b0`
- `0x5e2c0`
- `0x5e2d0`
- `0x1efa10`
- `0x1efa20`
- `0x1efa30`
- `0x1efa40`

## string_xrefs

- `0x5dc47`: `ActivityPartyService`
- `0x5dc1a`: `scheduledstart`
- `0x5dcac`: `scheduledstart`
- `0x5dcf8`: `scheduledstart`
- `0x5ddff`: `scheduledstart`
- `0x5dec9`: `scheduledstart`
- `0x5df77`: `scheduledstart`
- `0x5dc27`: `scheduledend`
- `0x5dcbd`: `scheduledend`
- `0x5dd0a`: `scheduledend`
- `0x5de0d`: `scheduledend`
- `0x5ded7`: `scheduledend`
- `0x5df85`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x5db80  ldc.i4.0
0x5db81  stloc.0
0x5db82  ldc.i4.0
0x5db83  stloc.1
0x5db84  ldc.i4.0
0x5db85  stloc.2
0x5db86  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5db8b  stloc.3
0x5db8c  ldc.i4.0
0x5db8d  stloc.s  4
0x5db8f  ldarg.2
0x5db90  ldstr    aOwnerid// "ownerid"
0x5db95  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5db9a  brfalse.s loc_5DB9E
0x5db9c  ldc.i4.1
0x5db9d  stloc.0
0x5db9e  ldarg.2
0x5db9f  ldarg.0
0x5dba0  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingIdField()
0x5dba5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dbaa  brfalse.s loc_5DC19
0x5dbac  ldc.i4.1
0x5dbad  stloc.1
0x5dbae  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5dbb3  ldarg.2
0x5dbb4  ldarg.0
0x5dbb5  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingIdField()
0x5dbba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dbbf  bne.un.s loc_5DBC9
0x5dbc1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5dbc6  stloc.3
0x5dbc7  br.s     loc_5DC19
0x5dbc9  ldarg.2
0x5dbca  ldarg.0
0x5dbcb  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingIdField()
0x5dbd0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dbd5  unbox.any [mscorlib]System.Guid
0x5dbda  stloc.3
0x5dbdb  ldarg.0
0x5dbdc  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingTypeField()
0x5dbe1  brfalse.s loc_5DC11
0x5dbe3  ldarg.2
0x5dbe4  ldarg.0
0x5dbe5  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingTypeField()
0x5dbea  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dbef  brfalse.s loc_5DC06
0x5dbf1  ldarg.2
0x5dbf2  ldarg.0
0x5dbf3  callvirt instance string Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingTypeField()
0x5dbf8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dbfd  unbox.any [mscorlib]System.Int32
0x5dc02  stloc.s  4
0x5dc04  br.s     loc_5DC19
0x5dc06  ldstr    aWhenUpdatingAn// "When updating an activity, regarding ob"...
0x5dc0b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5dc10  throw
0x5dc11  ldarg.0
0x5dc12  callvirt instance int32 Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_RegardingType()
0x5dc17  stloc.s  4
0x5dc19  ldarg.2
0x5dc1a  ldstr    aScheduledstart// "scheduledstart"
0x5dc1f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dc24  stloc.s  5
0x5dc26  ldarg.2
0x5dc27  ldstr    aScheduledend// "scheduledend"
0x5dc2c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dc31  stloc.s  6
0x5dc33  ldloc.s  5
0x5dc35  brtrue.s loc_5DC3B
0x5dc37  ldloc.s  6
0x5dc39  brfalse.s loc_5DC3D
0x5dc3b  ldc.i4.1
0x5dc3c  stloc.2
0x5dc3d  ldloc.0
0x5dc3e  brtrue.s loc_5DC47
0x5dc40  ldloc.1
0x5dc41  brtrue.s loc_5DC47
0x5dc43  ldloc.2
0x5dc44  brtrue.s loc_5DC47
0x5dc46  ret
0x5dc47  ldstr    aActivitypartys// "ActivityPartyService"
0x5dc4c  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::BusinessProcessReflectionUtiltity(string)
0x5dc51  castclass Microsoft.Crm.ObjectModel.Utility.IActivityPartyService
0x5dc56  stloc.s  7
0x5dc58  ldstr    aActivityparty// "ActivityParty"
0x5dc5d  ldarg.3
0x5dc5e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5dc63  stloc.s  8
0x5dc65  ldloc.s  8
0x5dc67  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5dc6c  ldstr    aActivityid_0// "activityid"
0x5dc71  ldc.i4.0
0x5dc72  ldarg.1
0x5dc73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5dc78  box      [mscorlib]System.Guid
0x5dc7d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5dc82  pop
0x5dc83  ldloc.s  8
0x5dc85  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5dc8a  ldstr    aPartyid// "partyid"
0x5dc8f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5dc94  ldloc.s  8
0x5dc96  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5dc9b  ldstr    aParticipationt// "participationtypemask"
0x5dca0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5dca5  ldloc.s  8
0x5dca7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5dcac  ldstr    aScheduledstart// "scheduledstart"
0x5dcb1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5dcb6  ldloc.s  8
0x5dcb8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5dcbd  ldstr    aScheduledend// "scheduledend"
0x5dcc2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5dcc7  ldloc.s  8
0x5dcc9  ldc.i4.1
0x5dcca  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0x5dccf  ldloc.s  7
0x5dcd1  ldloc.s  8
0x5dcd3  ldarg.3
0x5dcd4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5dcd9  stloc.s  9
0x5dcdb  ldloc.s  5
0x5dcdd  brfalse.s loc_5DCE3
0x5dcdf  ldloc.s  6
0x5dce1  brtrue.s loc_5DD16
0x5dce3  ldloc.s  9
0x5dce5  ldc.i4.0
0x5dce6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5dceb  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty
0x5dcf0  stloc.s  0xA
0x5dcf2  ldloc.s  5
0x5dcf4  brtrue.s loc_5DD04
0x5dcf6  ldloc.s  0xA
0x5dcf8  ldstr    aScheduledstart// "scheduledstart"
0x5dcfd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dd02  stloc.s  5
0x5dd04  ldloc.s  6
0x5dd06  brtrue.s loc_5DD16
0x5dd08  ldloc.s  0xA
0x5dd0a  ldstr    aScheduledend// "scheduledend"
0x5dd0f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dd14  stloc.s  6
0x5dd16  ldloc.s  9
0x5dd18  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5dd1d  stloc.s  0xB
0x5dd1f  br       loc_5DE23
0x5dd24  ldloc.s  0xB
0x5dd26  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5dd2b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5dd30  stloc.s  0xC
0x5dd32  ldloc.s  0xC
0x5dd34  ldstr    aParticipationt// "participationtypemask"
0x5dd39  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dd3e  brtrue.s loc_5DD50
0x5dd40  ldstr    aMissingPartici// "Missing participation type mask found f"...
0x5dd45  ldc.i4   0x80040201
0x5dd4a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5dd4f  throw
0x5dd50  ldloc.0
0x5dd51  brfalse.s loc_5DD90
0x5dd53  ldloc.s  0xC
0x5dd55  ldstr    aParticipationt// "participationtypemask"
0x5dd5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dd5f  unbox.any [mscorlib]System.Int32
0x5dd64  ldc.i4.s 9
0x5dd66  bne.un.s loc_5DD90
0x5dd68  ldloc.s  0xC
0x5dd6a  ldstr    aActivitypartyi// "activitypartyid"
0x5dd6f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dd74  unbox.any [mscorlib]System.Guid
0x5dd79  ldstr    aActivityparty// "ActivityParty"
0x5dd7e  ldarg.3
0x5dd7f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5dd84  stloc.s  0xD
0x5dd86  ldloc.s  7
0x5dd88  ldloc.s  0xD
0x5dd8a  ldarg.3
0x5dd8b  callvirt instance void Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::InternalDelete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5dd90  ldloc.1
0x5dd91  brfalse.s loc_5DDCB
0x5dd93  ldloc.s  0xC
0x5dd95  ldstr    aParticipationt// "participationtypemask"
0x5dd9a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dd9f  unbox.any [mscorlib]System.Int32
0x5dda4  ldc.i4.8
0x5dda5  bne.un.s loc_5DDCB
0x5dda7  ldloc.s  7
0x5dda9  ldloc.s  0xC
0x5ddab  ldstr    aActivitypartyi// "activitypartyid"
0x5ddb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ddb5  unbox.any [mscorlib]System.Guid
0x5ddba  ldstr    aActivityparty// "ActivityParty"
0x5ddbf  ldarg.3
0x5ddc0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5ddc5  ldarg.3
0x5ddc6  callvirt instance void Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::InternalDelete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5ddcb  ldloc.2
0x5ddcc  brfalse.s loc_5DE23
0x5ddce  ldloc.0
0x5ddcf  brtrue.s loc_5DDE6
0x5ddd1  ldloc.s  0xC
0x5ddd3  ldstr    aParticipationt// "participationtypemask"
0x5ddd8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5dddd  unbox.any [mscorlib]System.Int32
0x5dde2  ldc.i4.s 9
0x5dde4  beq.s    loc_5DDFD
0x5dde6  ldloc.1
0x5dde7  brtrue.s loc_5DE23
0x5dde9  ldloc.s  0xC
0x5ddeb  ldstr    aParticipationt// "participationtypemask"
0x5ddf0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ddf5  unbox.any [mscorlib]System.Int32
0x5ddfa  ldc.i4.8
0x5ddfb  bne.un.s loc_5DE23
0x5ddfd  ldloc.s  0xC
0x5ddff  ldstr    aScheduledstart// "scheduledstart"
0x5de04  ldloc.s  5
0x5de06  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5de0b  ldloc.s  0xC
0x5de0d  ldstr    aScheduledend// "scheduledend"
0x5de12  ldloc.s  6
0x5de14  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5de19  ldloc.s  7
0x5de1b  ldloc.s  0xC
0x5de1d  ldarg.3
0x5de1e  callvirt instance void Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5de23  ldloc.s  0xB
0x5de25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5de2a  brtrue   loc_5DD24
0x5de2f  leave.s  loc_5DE46
0x5de31  ldloc.s  0xB
0x5de33  isinst   [mscorlib]System.IDisposable
0x5de38  stloc.s  0xE
0x5de3a  ldloc.s  0xE
0x5de3c  brfalse.s loc_5DE45
0x5de3e  ldloc.s  0xE
0x5de40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5de45  endfinally
0x5de46  ldloc.0
0x5de47  brfalse  loc_5DEEE
0x5de4c  ldarg.3
0x5de4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5de52  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty::.ctor(valuetype [mscorlib]System.Guid)
0x5de57  stloc.s  0xF
0x5de59  ldloc.s  0xF
0x5de5b  ldstr    aActivitypartyi// "activitypartyid"
0x5de60  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5de65  box      [mscorlib]System.Guid
0x5de6a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5de6f  ldloc.s  0xF
0x5de71  ldstr    aActivityid_0// "activityid"
0x5de76  ldarg.1
0x5de77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5de7c  box      [mscorlib]System.Guid
0x5de81  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5de86  ldloc.s  0xF
0x5de88  ldstr    aPartyid// "partyid"
0x5de8d  ldarg.2
0x5de8e  ldstr    aOwnerid// "ownerid"
0x5de93  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5de98  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5de9d  ldloc.s  0xF
0x5de9f  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x5dea4  ldarg.2
0x5dea5  ldstr    aOwneridtype// "owneridtype"
0x5deaa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5deaf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5deb4  ldloc.s  0xF
0x5deb6  ldstr    aParticipationt// "participationtypemask"
0x5debb  ldc.i4.s 9
0x5debd  box      [mscorlib]System.Int32
0x5dec2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5dec7  ldloc.s  0xF
0x5dec9  ldstr    aScheduledstart// "scheduledstart"
0x5dece  ldloc.s  5
0x5ded0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5ded5  ldloc.s  0xF
0x5ded7  ldstr    aScheduledend// "scheduledend"
0x5dedc  ldloc.s  6
0x5dede  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5dee3  ldloc.s  7
0x5dee5  ldloc.s  0xF
0x5dee7  ldarg.3
0x5dee8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5deed  pop
0x5deee  ldloc.1
0x5deef  brfalse  loc_5DF9C
0x5def4  ldloc.3
0x5def5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5defa  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5deff  brfalse  loc_5DF9C
0x5df04  ldarg.3
0x5df05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5df0a  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty::.ctor(valuetype [mscorlib]System.Guid)
0x5df0f  stloc.s  0x10
0x5df11  ldloc.s  0x10
0x5df13  ldstr    aActivitypartyi// "activitypartyid"
0x5df18  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5df1d  box      [mscorlib]System.Guid
0x5df22  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
  ... truncated ...
```
