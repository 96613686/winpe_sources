# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::GetReferenceTokensForOpportunityActionCard

- ea: `0x126b0`
- end: `0x127ca`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::GetReferenceTokensForOpportunityActionCard`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x12310`

## callees

- `0x126b0`
- `0x135b0`
- `0x13690`
- `0x136b0`
- `0x136d0`

## pseudocode

```c

```

## disassembly

```asm
0x126b0  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::.ctor()
0x126b5  dup
0x126b6  ldarg.2
0x126b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x126bc  stloc.s  5
0x126be  ldloca.s 5
0x126c0  constrained. [mscorlib]System.Guid
0x126c6  callvirt instance string [mscorlib]System.Object::ToString()
0x126cb  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Id(string)
0x126d0  dup
0x126d1  ldarg.0
0x126d2  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Name(string)
0x126d7  dup
0x126d8  ldarg.1
0x126d9  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_TypeCode(int32)
0x126de  dup
0x126df  ldc.i4.2
0x126e0  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Type(valuetype [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ParamType)
0x126e5  stloc.0
0x126e6  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::.ctor()
0x126eb  dup
0x126ec  ldnull
0x126ed  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Id(string)
0x126f2  dup
0x126f3  ldarga.s 3
0x126f5  ldstr    aMmmmDdYyyy// "MMMM dd, yyyy"
0x126fa  call     instance string [mscorlib]System.DateTime::ToString(string)
0x126ff  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Name(string)
0x12704  dup
0x12705  ldc.i4.0
0x12706  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_TypeCode(int32)
0x1270b  dup
0x1270c  ldc.i4.1
0x1270d  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Type(valuetype [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ParamType)
0x12712  stloc.1
0x12713  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x12718  stloc.2
0x12719  ldloc.2
0x1271a  ldarg.s  4
0x1271c  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_TitleResourceId()
0x12721  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x12726  ldloc.2
0x12727  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x1272c  ldloc.0
0x1272d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x12732  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x12737  stloc.3
0x12738  ldloc.3
0x12739  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x1273e  ldloc.1
0x1273f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x12744  ldloc.3
0x12745  ldarg.s  4
0x12747  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_BodyResourceId()
0x1274c  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x12751  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x12756  stloc.s  4
0x12758  ldloc.s  4
0x1275a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x1275f  ldloc.0
0x12760  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x12765  ldarg.s  4
0x12767  callvirt instance valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_CardType()
0x1276c  ldc.i4.s 0x14
0x1276e  bne.un.s loc_1277D
0x12770  ldloc.s  4
0x12772  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x12777  ldloc.1
0x12778  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x1277d  ldloc.s  4
0x1277f  ldarg.s  4
0x12781  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::get_MiniCardResourceId()
0x12786  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x1278b  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::.ctor()
0x12790  dup
0x12791  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x12796  ldstr    aTitle// "title"
0x1279b  ldloc.2
0x1279c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x127a1  dup
0x127a2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x127a7  ldstr    aBody// "body"
0x127ac  ldloc.3
0x127ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x127b2  dup
0x127b3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x127b8  ldstr    aMinicardtext// "minicardtext"
0x127bd  ldloc.s  4
0x127bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x127c4  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x127c9  ret
```
