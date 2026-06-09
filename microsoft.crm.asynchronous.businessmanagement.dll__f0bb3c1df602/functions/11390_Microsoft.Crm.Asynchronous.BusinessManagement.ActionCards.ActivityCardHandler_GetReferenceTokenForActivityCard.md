# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetReferenceTokenForActivityCard

- ea: `0x11390`
- end: `0x1140a`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetReferenceTokenForActivityCard`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10f30`

## callees

- `0x11390`
- `0x11410`
- `0x11450`

## pseudocode

```c

```

## disassembly

```asm
0x11390  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::.ctor()
0x11395  stloc.0
0x11396  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x1139b  stloc.1
0x1139c  ldloc.1
0x1139d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x113a2  ldarg.0
0x113a3  ldarg.1
0x113a4  ldarg.2
0x113a5  call     instance class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetClickableSubjectForRefTokens(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity activity, int32 typeCode)
0x113aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x113af  ldloc.1
0x113b0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x113b5  ldarg.0
0x113b6  ldarg.1
0x113b7  ldarg.2
0x113b8  ldarg.s  4
0x113ba  call     instance class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::GetClickableDateForRefTokens(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity activity, int32 typeCode, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType)
0x113bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x113c4  ldarg.s  4
0x113c6  ldc.i4.6
0x113c7  bne.un.s loc_113EB
0x113c9  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x113ce  stloc.2
0x113cf  ldloc.2
0x113d0  ldstr    aActioncardRece_0// "ActionCard.RecentMeetingCard.Body"
0x113d5  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x113da  ldloc.0
0x113db  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x113e0  ldstr    aBody// "body"
0x113e5  ldloc.2
0x113e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x113eb  ldloc.1
0x113ec  ldarg.3
0x113ed  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x113f2  ldloc.0
0x113f3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x113f8  ldstr    aMinicardtext// "minicardtext"
0x113fd  ldloc.1
0x113fe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x11403  ldloc.0
0x11404  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x11409  ret
```
