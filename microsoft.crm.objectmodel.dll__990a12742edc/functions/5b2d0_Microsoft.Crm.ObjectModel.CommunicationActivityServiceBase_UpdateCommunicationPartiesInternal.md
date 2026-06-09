# Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::UpdateCommunicationPartiesInternal

- ea: `0x5b2d0`
- end: `0x5ba1b`
- name: `Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::UpdateCommunicationPartiesInternal`
- size: `1867`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5a8f0`

## callees

- `0x5b200`
- `0x5b2d0`
- `0x5ba20`
- `0x5bf70`
- `0x5bfb0`
- `0x5c150`
- `0x5c160`
- `0x5c250`
- `0x5c2e0`
- `0x5e300`
- `0x5e320`
- `0x5e340`
- `0x5e3c0`
- `0x5e3d0`
- `0x5e720`
- `0x1efa10`
- `0x1efa20`
- `0x1efa40`

## string_xrefs

- `0x5b351`: `ActivityPartyService`
- `0x5b374`: `scheduledstart`
- `0x5b3c2`: `scheduledstart`
- `0x5b42a`: `scheduledstart`
- `0x5b6c5`: `scheduledstart`
- `0x5b786`: `scheduledstart`
- `0x5b9ad`: `scheduledstart`
- `0x5b381`: `scheduledend`
- `0x5b3d4`: `scheduledend`
- `0x5b438`: `scheduledend`
- `0x5b6d3`: `scheduledend`
- `0x5b794`: `scheduledend`
- `0x5b9bb`: `scheduledend`
- `0x5b470`: `ispartydeleted`
- `0x5b47e`: `ispartydeleted`
- `0x5b5b3`: `Participation Type Mask was found to be empty in an Activity Party during update.`

## pseudocode

```c

```

## disassembly

```asm
0x5b2d0  ldarg.0
0x5b2d1  ldfld    class Microsoft.Crm.ObjectModel.RecurringSeriesContext Microsoft.Crm.ObjectModel.GenericActivityServiceBase::seriesContext
0x5b2d6  callvirt instance bool Microsoft.Crm.ObjectModel.RecurringSeriesContext::IgnoreActivityPartyProcessing()
0x5b2db  brtrue.s loc_5B32F
0x5b2dd  ldarg.s  4
0x5b2df  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x5b2e4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5b2e9  ldstr    aSeriescontext// "seriescontext"
0x5b2ee  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5b2f3  brfalse.s loc_5B330
0x5b2f5  ldarg.s  4
0x5b2f7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x5b2fc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5b301  ldstr    aSeriescontext// "seriescontext"
0x5b306  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5b30b  brfalse.s loc_5B330
0x5b30d  ldarg.s  4
0x5b30f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x5b314  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5b319  ldstr    aSeriescontext// "seriescontext"
0x5b31e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5b323  castclass Microsoft.Crm.ObjectModel.RecurringSeriesContext
0x5b328  callvirt instance bool Microsoft.Crm.ObjectModel.RecurringSeriesContext::IgnoreActivityPartyProcessing()
0x5b32d  brfalse.s loc_5B330
0x5b32f  ret
0x5b330  ldarg.3
0x5b331  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5b336  newobj   instance void Microsoft.Crm.ObjectModel.ScheduleNotifications::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x5b33b  stloc.0
0x5b33c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5b341  stloc.1
0x5b342  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5b347  stloc.2
0x5b348  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5b34d  stloc.3
0x5b34e  ldnull
0x5b34f  stloc.s  4
0x5b351  ldstr    aActivitypartys// "ActivityPartyService"
0x5b356  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::BusinessProcessReflectionUtiltity(string)
0x5b35b  castclass Microsoft.Crm.ObjectModel.Utility.IActivityPartyService
0x5b360  stloc.s  5
0x5b362  ldarg.0
0x5b363  ldarg.3
0x5b364  ldarg.1
0x5b365  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5b36a  ldloc.s  5
0x5b36c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::RetrieveActivityParties(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid activityId, class Microsoft.Crm.ObjectModel.Utility.IActivityPartyService activityPartySvc)
0x5b371  stloc.s  6
0x5b373  ldarg.2
0x5b374  ldstr    aScheduledstart// "scheduledstart"
0x5b379  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b37e  stloc.s  7
0x5b380  ldarg.2
0x5b381  ldstr    aScheduledend// "scheduledend"
0x5b386  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b38b  stloc.s  8
0x5b38d  ldc.i4.0
0x5b38e  stloc.s  9
0x5b390  ldloc.s  7
0x5b392  brtrue.s loc_5B398
0x5b394  ldloc.s  8
0x5b396  brfalse.s loc_5B39B
0x5b398  ldc.i4.1
0x5b399  stloc.s  9
0x5b39b  ldloc.s  7
0x5b39d  brfalse.s loc_5B3A3
0x5b39f  ldloc.s  8
0x5b3a1  brtrue.s loc_5B3E0
0x5b3a3  ldloc.s  6
0x5b3a5  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5b3aa  ldc.i4.0
0x5b3ab  ble.s    loc_5B3E0
0x5b3ad  ldloc.s  6
0x5b3af  ldc.i4.0
0x5b3b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5b3b5  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty
0x5b3ba  stloc.s  0xA
0x5b3bc  ldloc.s  7
0x5b3be  brtrue.s loc_5B3CE
0x5b3c0  ldloc.s  0xA
0x5b3c2  ldstr    aScheduledstart// "scheduledstart"
0x5b3c7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b3cc  stloc.s  7
0x5b3ce  ldloc.s  8
0x5b3d0  brtrue.s loc_5B3E0
0x5b3d2  ldloc.s  0xA
0x5b3d4  ldstr    aScheduledend// "scheduledend"
0x5b3d9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b3de  stloc.s  8
0x5b3e0  ldloc.s  6
0x5b3e2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5b3e7  stloc.s  0xB
0x5b3e9  br       loc_5B4A1
0x5b3ee  ldloc.s  0xB
0x5b3f0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b3f5  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty
0x5b3fa  stloc.s  0xC
0x5b3fc  ldloc.s  9
0x5b3fe  brfalse  loc_5B4A1
0x5b403  ldarg.3
0x5b404  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5b409  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty::.ctor(valuetype [mscorlib]System.Guid)
0x5b40e  stloc.s  0xD
0x5b410  ldloc.s  0xD
0x5b412  ldstr    aActivitypartyi// "activitypartyid"
0x5b417  ldloc.s  0xC
0x5b419  ldstr    aActivitypartyi// "activitypartyid"
0x5b41e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b423  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b428  ldloc.s  0xD
0x5b42a  ldstr    aScheduledstart// "scheduledstart"
0x5b42f  ldloc.s  7
0x5b431  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b436  ldloc.s  0xD
0x5b438  ldstr    aScheduledend// "scheduledend"
0x5b43d  ldloc.s  8
0x5b43f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b444  ldloc.s  0xD
0x5b446  ldstr    aParticipationt// "participationtypemask"
0x5b44b  ldloc.s  0xC
0x5b44d  ldstr    aParticipationt// "participationtypemask"
0x5b452  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b457  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b45c  ldloc.s  5
0x5b45e  ldloc.s  0xD
0x5b460  ldarg.3
0x5b461  callvirt instance void Microsoft.Crm.ObjectModel.Utility.IActivityPartyService::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b466  ldarg.0
0x5b467  callvirt instance bool Microsoft.Crm.ObjectModel.GenericActivityServiceBase::get_IsSchedulable()
0x5b46c  brfalse.s loc_5B4A1
0x5b46e  ldloc.s  0xC
0x5b470  ldstr    aIspartydeleted// "ispartydeleted"
0x5b475  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5b47a  brtrue.s loc_5B48F
0x5b47c  ldloc.s  0xC
0x5b47e  ldstr    aIspartydeleted// "ispartydeleted"
0x5b483  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b488  unbox.any [mscorlib]System.Boolean
0x5b48d  brtrue.s loc_5B4A1
0x5b48f  ldloc.0
0x5b490  ldloc.s  0xC
0x5b492  ldstr    aPartyid// "partyid"
0x5b497  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b49c  callvirt instance void Microsoft.Crm.ObjectModel.ScheduleNotifications::AddParty(object partyId)
0x5b4a1  ldloc.s  0xB
0x5b4a3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5b4a8  brtrue   loc_5B3EE
0x5b4ad  leave.s  loc_5B4C4
0x5b4af  ldloc.s  0xB
0x5b4b1  isinst   [mscorlib]System.IDisposable
0x5b4b6  stloc.s  0xE
0x5b4b8  ldloc.s  0xE
0x5b4ba  brfalse.s loc_5B4C3
0x5b4bc  ldloc.s  0xE
0x5b4be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b4c3  endfinally
0x5b4c4  ldarg.2
0x5b4c5  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x5b4ca  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x5b4cf  stloc.s  0xB
0x5b4d1  br       loc_5B841
0x5b4d6  ldloc.s  0xB
0x5b4d8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b4dd  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem
0x5b4e2  stloc.s  0xF
0x5b4e4  ldloc.s  0xF
0x5b4e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x5b4eb  brfalse  loc_5B841
0x5b4f0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty>::.ctor()
0x5b4f5  stloc.s  0x10
0x5b4f7  ldloc.s  0xF
0x5b4f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x5b4fe  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5b503  stloc.s  0x11
0x5b505  br.s     loc_5B553
0x5b507  ldloc.s  0x11
0x5b509  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b50e  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty
0x5b513  stloc.s  0x12
0x5b515  ldloc.s  0x12
0x5b517  ldstr    aActivitypartyi// "activitypartyid"
0x5b51c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5b521  brfalse.s loc_5B539
0x5b523  ldloc.s  0x12
0x5b525  ldstr    aActivitypartyi// "activitypartyid"
0x5b52a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x5b52f  box      [mscorlib]System.Guid
0x5b534  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b539  ldloc.s  0x10
0x5b53b  ldloc.s  0x12
0x5b53d  ldstr    aActivitypartyi// "activitypartyid"
0x5b542  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b547  unbox.any [mscorlib]System.Guid
0x5b54c  ldloc.s  0x12
0x5b54e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty>::Add(var<u1>, !!T0)
0x5b553  ldloc.s  0x11
0x5b555  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5b55a  brtrue.s loc_5B507
0x5b55c  leave.s  loc_5B573
0x5b55e  ldloc.s  0x11
0x5b560  isinst   [mscorlib]System.IDisposable
0x5b565  stloc.s  0xE
0x5b567  ldloc.s  0xE
0x5b569  brfalse.s loc_5B572
0x5b56b  ldloc.s  0xE
0x5b56d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b572  endfinally
0x5b573  ldloc.s  6
0x5b575  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5b57a  stloc.s  0x11
0x5b57c  br       loc_5B7B4
0x5b581  ldloc.s  0x11
0x5b583  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b588  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty
0x5b58d  stloc.s  0x13
0x5b58f  ldloc.s  0x13
0x5b591  ldstr    aParticipationt// "participationtypemask"
0x5b596  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5b59b  brfalse.s loc_5B5C3
0x5b59d  ldnull
0x5b59e  ldarg.3
0x5b59f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5b5a4  ldc.i4.s 0x14
0x5b5a6  ldstr    a0_0// "{0}"
0x5b5ab  ldc.i4.1
0x5b5ac  newarr   [mscorlib]System.Object
0x5b5b1  dup
0x5b5b2  ldc.i4.0
0x5b5b3  ldstr    aParticipationT// "Participation Type Mask was found to be"...
0x5b5b8  stelem.ref
0x5b5b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5b5be  br       loc_5B7B4
0x5b5c3  ldc.i4.0
0x5b5c4  stloc.s  0x14
0x5b5c6  ldc.i4.1
0x5b5c7  stloc.s  0x15
0x5b5c9  ldnull
0x5b5ca  stloc.s  0x16
0x5b5cc  ldloc.s  0x13
0x5b5ce  ldstr    aActivitypartyi// "activitypartyid"
0x5b5d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b5d8  unbox.any [mscorlib]System.Guid
0x5b5dd  stloc.s  0x17
0x5b5df  ldloc.s  0x10
0x5b5e1  ldloc.s  0x17
0x5b5e3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty>::ContainsKey(var<u1>)
0x5b5e8  brfalse.s loc_5B626
0x5b5ea  ldloc.s  0x10
0x5b5ec  ldloc.s  0x17
0x5b5ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty>::get_Item(void)
0x5b5f3  stloc.s  0x16
0x5b5f5  ldloc.3
0x5b5f6  ldloc.s  0x13
0x5b5f8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5b5fd  pop
0x5b5fe  ldloc.s  0x16
0x5b600  ldstr    aParticipationt// "participationtypemask"
0x5b605  ldloc.s  0xF
0x5b607  callvirt instance valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ParticipationType [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0x5b60c  box      [mscorlib]System.Int32
0x5b611  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5b616  ldc.i4.1
0x5b617  stloc.s  0x14
0x5b619  ldloc.s  0x16
0x5b61b  ldloc.s  0x13
0x5b61d  call     bool Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::IsUpdateNecessary(class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty newParty, class [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty oldParty)
0x5b622  stloc.s  0x15
0x5b624  br.s     loc_5B643
0x5b626  ldloc.s  0x13
0x5b628  ldstr    aParticipationt// "participationtypemask"
0x5b62d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b632  unbox.any [mscorlib]System.Int32
0x5b637  ldloc.s  0xF
0x5b639  callvirt instance valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ParticipationType [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0x5b63e  bne.un   loc_5B7B4
0x5b643  ldloc.s  0x14
0x5b645  brtrue.s loc_5B655
0x5b647  ldloc.2
0x5b648  ldloc.s  0x13
0x5b64a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5b64f  pop
0x5b650  br       loc_5B7B4
0x5b655  ldloc.s  0x16
0x5b657  ldstr    aPartyid// "partyid"
0x5b65c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5b661  brtrue.s loc_5B6BF
0x5b663  ldloc.s  0x13
0x5b665  ldstr    aPartyid// "partyid"
0x5b66a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5b66f  brtrue.s loc_5B6BF
0x5b671  ldloc.s  0x16
0x5b673  ldstr    aPartyid// "partyid"
0x5b678  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b67d  unbox.any [mscorlib]System.Guid
0x5b682  ldloc.s  0x13
0x5b684  ldstr    aPartyid// "partyid"
0x5b689  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b68e  unbox.any [mscorlib]System.Guid
0x5b693  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5b698  brfalse.s loc_5B6BF
  ... truncated ...
```
