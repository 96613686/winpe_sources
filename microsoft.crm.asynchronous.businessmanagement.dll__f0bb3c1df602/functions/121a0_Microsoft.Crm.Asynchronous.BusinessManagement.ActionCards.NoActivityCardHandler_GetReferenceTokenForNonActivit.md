# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetReferenceTokenForNonActivityCard

- ea: `0x121a0`
- end: `0x122c7`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetReferenceTokenForNonActivityCard`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x12000`

## callees

- `0x121a0`

## pseudocode

```c

```

## disassembly

```asm
0x121a0  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x121a5  stloc.0
0x121a6  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x121ab  stloc.1
0x121ac  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::.ctor()
0x121b1  stloc.2
0x121b2  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::.ctor()
0x121b7  dup
0x121b8  ldarg.1
0x121b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x121be  stloc.s  5
0x121c0  ldloca.s 5
0x121c2  constrained. [mscorlib]System.Guid
0x121c8  callvirt instance string [mscorlib]System.Object::ToString()
0x121cd  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Id(string)
0x121d2  dup
0x121d3  ldarg.3
0x121d4  dup
0x121d5  brtrue.s loc_121DD
0x121d7  pop
0x121d8  ldsfld   string [mscorlib]System.String::Empty
0x121dd  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Name(string)
0x121e2  dup
0x121e3  ldarg.2
0x121e4  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_TypeCode(int32)
0x121e9  dup
0x121ea  ldc.i4.2
0x121eb  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Type(valuetype [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ParamType)
0x121f0  stloc.3
0x121f1  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::.ctor()
0x121f6  dup
0x121f7  ldnull
0x121f8  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Id(string)
0x121fd  dup
0x121fe  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x12203  stloc.s  6
0x12205  ldloca.s 6
0x12207  ldstr    aS// "s"
0x1220c  call     instance string [mscorlib]System.DateTime::ToString(string)
0x12211  ldstr    aZ// "Z"
0x12216  call     string [mscorlib]System.String::Concat(string, string)
0x1221b  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Name(string)
0x12220  dup
0x12221  ldc.i4.0
0x12222  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_TypeCode(int32)
0x12227  dup
0x12228  ldc.i4.1
0x12229  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter::set_Type(valuetype [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ParamType)
0x1222e  stloc.s  4
0x12230  ldloc.0
0x12231  ldstr    aActioncardNoac_4// "ActionCard.NOActivity.Title"
0x12236  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x1223b  ldloc.0
0x1223c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x12241  ldloc.3
0x12242  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x12247  ldloc.1
0x12248  ldarg.s  4
0x1224a  dup
0x1224b  brtrue.s loc_12253
0x1224d  pop
0x1224e  ldsfld   string [mscorlib]System.String::Empty
0x12253  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x12258  ldloc.1
0x12259  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x1225e  ldloc.s  4
0x12260  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x12265  ldloc.2
0x12266  ldstr    aActioncardNoac_5// "ActionCard.NOActivity.MiniCardText"
0x1226b  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::set_ResourceId(string)
0x12270  ldloc.2
0x12271  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x12276  ldloc.3
0x12277  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x1227c  ldloc.2
0x1227d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token::Params
0x12282  ldloc.s  4
0x12284  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Parameter>::Add(var<u1>)
0x12289  newobj   instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::.ctor()
0x1228e  dup
0x1228f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x12294  ldstr    aTitle// "title"
0x12299  ldloc.0
0x1229a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x1229f  dup
0x122a0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x122a5  ldstr    aBody// "body"
0x122aa  ldloc.1
0x122ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x122b0  dup
0x122b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ReferenceTokens::Tokens
0x122b6  ldstr    aMinicardtext// "minicardtext"
0x122bb  ldloc.2
0x122bc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.Token>::Add(var<u1>, !!T0)
0x122c1  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x122c6  ret
```
