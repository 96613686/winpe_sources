# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::CreateActivityCards

- ea: `0x10b30`
- end: `0x10cc4`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::CreateActivityCards`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x150`

## callees

- `0x10b30`
- `0x10cd0`
- `0x10f30`
- `0x11040`
- `0x11580`
- `0x11b90`
- `0x11ba0`
- `0x11bc0`
- `0x12ea0`

## string_xrefs

- `0x10bf2`: `CreateActivityCards`
- `0x10c37`: `CreateActivityCards`
- `0x10bfd`: `AsyncHandler::ActivityCardHandler::CreateActivityCards`
- `0x10c42`: `AsyncHandler::ActivityCardHandler::CreateActivityCards`
- `0x10c02`: `Total activity cards created: {0} and  activity card creation failed for: {1}  at UTC: {2}`
- `0x10c9a`: `AsyncHandler::ActionCardHandler::CreateActivityCards`
- `0x10ca0`: `Failed to create relevant activity cards. \n Error Details: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x10b30  ldc.i4.0
0x10b31  stloc.0
0x10b32  ldc.i4.0
0x10b33  stloc.1
0x10b34  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x10b39  stloc.2
0x10b3a  ldarg.0
0x10b3b  ldarg.0
0x10b3c  ldfld    class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_actionCardHandler
0x10b41  ldarg.1
0x10b42  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler::GetQueryStartTime(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x10b47  ldarg.0
0x10b48  ldfld    class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_actionCardHandler
0x10b4d  ldarg.1
0x10b4e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler::GetQueryEndTime(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x10b53  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetRelevantActivitiesBetweenTimeframe(valuetype [mscorlib]System.DateTime startDay, valuetype [mscorlib]System.DateTime endDay)
0x10b58  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x10b5d  stloc.3
0x10b5e  br.s     loc_10BD2
0x10b60  ldloc.3
0x10b61  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x10b66  stloc.s  4
0x10b68  ldarg.0
0x10b69  ldloc.s  4
0x10b6b  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::SetLogicalName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activityEntity)
0x10b70  ldarg.0
0x10b71  ldfld    class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_actionCardHandler
0x10b76  ldloc.s  4
0x10b78  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x10b7d  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler::GetEntityTypeCode(string entityLogicalName)
0x10b82  stloc.s  5
0x10b84  ldarg.0
0x10b85  ldloc.s  4
0x10b87  ldloc.s  5
0x10b89  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activity, int32 activityTypeCode)
0x10b8e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetActivityCardConfigurations(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity activity)
0x10b93  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::GetEnumerator()
0x10b98  stloc.s  6
0x10b9a  br.s     loc_10BBB
0x10b9c  ldloc.s  6
0x10b9e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig>::get_Current()
0x10ba3  stloc.s  7
0x10ba5  ldarg.0
0x10ba6  ldloc.s  4
0x10ba8  ldloc.s  7
0x10baa  call     instance bool Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::TryCreateActivityCard(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activityEntity, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardConfig cardConfig)
0x10baf  brfalse.s loc_10BB7
0x10bb1  ldloc.0
0x10bb2  ldc.i4.1
0x10bb3  add
0x10bb4  stloc.0
0x10bb5  br.s     loc_10BBB
0x10bb7  ldloc.1
0x10bb8  ldc.i4.1
0x10bb9  add
0x10bba  stloc.1
0x10bbb  ldloc.s  6
0x10bbd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10bc2  brtrue.s loc_10B9C
0x10bc4  leave.s  loc_10BD2
0x10bc6  ldloc.s  6
0x10bc8  brfalse.s loc_10BD1
0x10bca  ldloc.s  6
0x10bcc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10bd1  endfinally
0x10bd2  ldloc.3
0x10bd3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10bd8  brtrue.s loc_10B60
0x10bda  leave.s  loc_10BE6
0x10bdc  ldloc.3
0x10bdd  brfalse.s loc_10BE5
0x10bdf  ldloc.3
0x10be0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10be5  endfinally
0x10be6  ldloc.2
0x10be7  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x10bec  ldarg.0
0x10bed  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_cardsTrace
0x10bf2  ldstr    aCreateactivity// "CreateActivityCards"
0x10bf7  ldarg.0
0x10bf8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_organizationId
0x10bfd  ldstr    aAsynchandlerAc_4// "AsyncHandler::ActivityCardHandler::Crea"...
0x10c02  ldstr    aTotalActivityC// "Total activity cards created: {0} and  "...
0x10c07  ldloc.0
0x10c08  box      [mscorlib]System.Int32
0x10c0d  ldloc.1
0x10c0e  box      [mscorlib]System.Int32
0x10c13  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10c18  box      [mscorlib]System.DateTime
0x10c1d  call     string [mscorlib]System.String::Format(string, object, object, object)
0x10c22  ldsfld   string [mscorlib]System.String::Empty
0x10c27  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10c2c  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x10c31  ldarg.0
0x10c32  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_cardsTrace
0x10c37  ldstr    aCreateactivity// "CreateActivityCards"
0x10c3c  ldarg.0
0x10c3d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_organizationId
0x10c42  ldstr    aAsynchandlerAc_4// "AsyncHandler::ActivityCardHandler::Crea"...
0x10c47  ldloc.2
0x10c48  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x10c4d  ldstr    aActivityCardCr// "Activity Card Creation on {0} took {1}"
0x10c52  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10c57  stloc.s  8
0x10c59  ldloca.s 8
0x10c5b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x10c60  box      [mscorlib]System.DateTime
0x10c65  ldloc.2
0x10c66  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x10c6b  box      [mscorlib]System.TimeSpan
0x10c70  call     string [mscorlib]System.String::Format(string, object, object)
0x10c75  ldsfld   string [mscorlib]System.String::Empty
0x10c7a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10c7f  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardTimeTaken(string, valuetype [mscorlib]System.Guid, string, int64, string, string, valuetype [mscorlib]System.Guid)
0x10c84  leave.s  loc_10CC2
0x10c86  stloc.s  9
0x10c88  ldloc.2
0x10c89  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x10c8e  ldarg.0
0x10c8f  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_cardsTrace
0x10c94  ldarg.0
0x10c95  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::_organizationId
0x10c9a  ldstr    aAsynchandlerAc_5// "AsyncHandler::ActionCardHandler::Create"...
0x10c9f  ldc.i4.6
0x10ca0  ldstr    aFailedToCreate// "Failed to create relevant activity card"...
0x10ca5  ldloc.s  9
0x10ca7  callvirt instance string [mscorlib]System.Object::ToString()
0x10cac  call     string [mscorlib]System.String::Format(string, object)
0x10cb1  ldsfld   string [mscorlib]System.String::Empty
0x10cb6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10cbb  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x10cc0  leave.s  loc_10CC2
0x10cc2  ldloc.0
0x10cc3  ret
```
