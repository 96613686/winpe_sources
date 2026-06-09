# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::CreateOpportunityActionCards

- ea: `0x12310`
- end: `0x124d9`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::CreateOpportunityActionCards`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x12310`
- `0x124e0`
- `0x126b0`
- `0x128f0`
- `0x12940`
- `0x12990`
- `0x129c0`
- `0x12a50`
- `0x13590`
- `0x13630`
- `0x13650`
- `0x13670`

## string_xrefs

- `0x123eb`: `AsyncHandler::OpportunityActionCardHandler::CreateOpportunityActionCards`
- `0x12446`: `AsyncHandler::OpportunityActionCardHandler::CreateOpportunityActionCards`
- `0x1248b`: `AsyncHandler::OpportunityActionCardHandler::CreateOpportunityActionCards`
- `0x1243b`: `CreateOpportunityCards`
- `0x12480`: `CreateOpportunityCards`
- `0x1244b`: `Total opportunities action cards created: {0} and failed are: {1} at UTC: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x12310  ldc.i4.0
0x12311  stloc.0
0x12312  ldc.i4.0
0x12313  stloc.1
0x12314  ldarg.0
0x12315  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x1231a  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_timePerParse
0x1231f  ldarg.0
0x12320  ldarg.1
0x12321  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::GetRelavantOpportunities(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig actionCardConfig)
0x12326  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x1232b  stloc.2
0x1232c  br       loc_12413
0x12331  ldloc.2
0x12332  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x12337  stloc.3
0x12338  ldloc.3
0x12339  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity parentEntity)
0x1233e  stloc.s  4
0x12340  ldloc.3
0x12341  ldstr    aEstimatedclose// "estimatedclosedate"
0x12346  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1234b  unbox.any [mscorlib]System.DateTime
0x12350  stloc.s  5
0x12352  ldloc.s  4
0x12354  ldarg.1
0x12355  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_AssociatedActionCardTypeId()
0x1235a  ldc.i4.0
0x1235b  ldarg.1
0x1235c  callvirt instance valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_Priority()
0x12361  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetCardTypeInformation(valuetype [mscorlib]System.Guid cardTypeId, bool visibility, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority)
0x12366  ldloc.s  4
0x12368  ldloca.s 5
0x1236a  ldarg.1
0x1236b  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_DaysToStartCard()
0x12370  conv.r8
0x12371  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x12376  ldloca.s 5
0x12378  ldarg.1
0x12379  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_DaysToEndCard()
0x1237e  conv.r8
0x1237f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x12384  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetActionCardDateRange(valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0x12389  ldloc.s  4
0x1238b  ldloc.3
0x1238c  ldstr    aName// "name"
0x12391  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x12396  castclass [mscorlib]System.String
0x1239b  ldc.i4.3
0x1239c  ldloc.3
0x1239d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::ToEntityReference()
0x123a2  ldloc.s  5
0x123a4  ldarg.1
0x123a5  call     string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::GetReferenceTokensForOpportunityActionCard(string name, int32 entityTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference regarding, valuetype [mscorlib]System.DateTime closingDate, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig opptyCardConfig)
0x123aa  callvirt instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::SetTokenIformation(string token)
0x123af  ldarg.0
0x123b0  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_crmService
0x123b5  ldloc.s  4
0x123b7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCard::get_Entity()
0x123bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x123c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x123c6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x123cb  brfalse.s loc_123D3
0x123cd  ldloc.0
0x123ce  ldc.i4.1
0x123cf  add
0x123d0  stloc.0
0x123d1  br.s     loc_123D7
0x123d3  ldloc.1
0x123d4  ldc.i4.1
0x123d5  add
0x123d6  stloc.1
0x123d7  leave.s  loc_12413
0x123d9  stloc.s  6
0x123db  ldloc.1
0x123dc  ldc.i4.1
0x123dd  add
0x123de  stloc.1
0x123df  ldarg.0
0x123e0  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_cardsTrace
0x123e5  ldarg.0
0x123e6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_organizationId
0x123eb  ldstr    aAsynchandlerOp// "AsyncHandler::OpportunityActionCardHand"...
0x123f0  ldc.i4.5
0x123f1  ldstr    aErrorWhileCrea// "Error while creating opportunity action"...
0x123f6  ldloc.s  6
0x123f8  callvirt instance string [mscorlib]System.Object::ToString()
0x123fd  call     string [mscorlib]System.String::Format(string, object)
0x12402  ldsfld   string [mscorlib]System.String::Empty
0x12407  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1240c  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x12411  leave.s  loc_12413
0x12413  ldloc.2
0x12414  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12419  brtrue   loc_12331
0x1241e  leave.s  loc_1242A
0x12420  ldloc.2
0x12421  brfalse.s loc_12429
0x12423  ldloc.2
0x12424  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12429  endfinally
0x1242a  ldarg.0
0x1242b  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_timePerParse
0x12430  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x12435  ldarg.0
0x12436  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_cardsTrace
0x1243b  ldstr    aCreateopportun// "CreateOpportunityCards"
0x12440  ldarg.0
0x12441  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_organizationId
0x12446  ldstr    aAsynchandlerOp// "AsyncHandler::OpportunityActionCardHand"...
0x1244b  ldstr    aTotalOpportuni_0// "Total opportunities action cards create"...
0x12450  ldloc.0
0x12451  box      [mscorlib]System.Int32
0x12456  ldloc.1
0x12457  box      [mscorlib]System.Int32
0x1245c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x12461  box      [mscorlib]System.DateTime
0x12466  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1246b  ldsfld   string [mscorlib]System.String::Empty
0x12470  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12475  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x1247a  ldarg.0
0x1247b  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_cardsTrace
0x12480  ldstr    aCreateopportun// "CreateOpportunityCards"
0x12485  ldarg.0
0x12486  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_organizationId
0x1248b  ldstr    aAsynchandlerOp// "AsyncHandler::OpportunityActionCardHand"...
0x12490  ldarg.0
0x12491  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_timePerParse
0x12496  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x1249b  ldstr    aOpportunityCar// "opportunity Card Creation on {0} took {"...
0x124a0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x124a5  stloc.s  7
0x124a7  ldloca.s 7
0x124a9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x124ae  box      [mscorlib]System.DateTime
0x124b3  ldarg.0
0x124b4  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_timePerParse
0x124b9  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x124be  box      [mscorlib]System.TimeSpan
0x124c3  call     string [mscorlib]System.String::Format(string, object, object)
0x124c8  ldsfld   string [mscorlib]System.String::Empty
0x124cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x124d2  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardTimeTaken(string, valuetype [mscorlib]System.Guid, string, int64, string, string, valuetype [mscorlib]System.Guid)
0x124d7  ldloc.0
0x124d8  ret
```
