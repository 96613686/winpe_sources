# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CreateOpportunityCards

- ea: `0x390`
- end: `0x40d`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CreateOpportunityCards`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x150`

## callees

- `0x390`
- `0x11c10`
- `0x11c20`

## string_xrefs

- `0x3d2`: `CreateNoActivityCards`
- `0x3dd`: `AsyncHandler::ActionCardAsyncOperation::CreateNoActivityCards`
- `0x3e2`: `Total Opportunity cards created on UTC: {0} is {1}`

## pseudocode

```c

```

## disassembly

```asm
0x390  ldc.i4.0
0x391  stloc.0
0x392  ldarg.1
0x393  ldarg.2
0x394  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IOpportunityActionCardHandler::GetOpportunityCardsConfiguration(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x399  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>::GetEnumerator()
0x39e  stloc.1
0x39f  br.s     loc_3B3
0x3a1  ldloca.s 1
0x3a3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>::get_Current()
0x3a8  stloc.2
0x3a9  ldloc.0
0x3aa  ldarg.1
0x3ab  ldloc.2
0x3ac  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IOpportunityActionCardHandler::CreateOpportunityActionCards(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig actionCardConfig)
0x3b1  add
0x3b2  stloc.0
0x3b3  ldloca.s 1
0x3b5  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>::MoveNext()
0x3ba  brtrue.s loc_3A1
0x3bc  leave.s  loc_3CC
0x3be  ldloca.s 1
0x3c0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>
0x3c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3cb  endfinally
0x3cc  ldarg.0
0x3cd  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x3d2  ldstr    aCreatenoactivi// "CreateNoActivityCards"
0x3d7  ldarg.0
0x3d8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x3dd  ldstr    aAsynchandlerAc// "AsyncHandler::ActionCardAsyncOperation:"...
0x3e2  ldstr    aTotalOpportuni// "Total Opportunity cards created on UTC:"...
0x3e7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3ec  box      [mscorlib]System.DateTime
0x3f1  ldloc.0
0x3f2  box      [mscorlib]System.Int32
0x3f7  call     string [mscorlib]System.String::Format(string, object, object)
0x3fc  ldsfld   string [mscorlib]System.String::Empty
0x401  ldarg.0
0x402  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x407  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x40c  ret
```
