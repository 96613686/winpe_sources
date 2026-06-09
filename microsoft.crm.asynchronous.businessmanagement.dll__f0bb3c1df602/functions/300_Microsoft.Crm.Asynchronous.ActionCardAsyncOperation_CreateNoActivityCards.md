# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CreateNoActivityCards

- ea: `0x300`
- end: `0x385`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CreateNoActivityCards`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x150`

## callees

- `0x300`
- `0x760`
- `0x11be0`
- `0x11bf0`

## string_xrefs

- `0x34a`: `CreateNoActivityCards`
- `0x355`: `AsyncHandler::ActionCardAsyncOperation::CreateNoActivityCards`
- `0x35a`: `Total No Activity cards created on UTC: {0} is {1}`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldc.i4.0
0x301  stloc.0
0x302  ldarg.0
0x303  call     instance bool Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::IsNonBaseActionCardAsyncFeatureEnabled()
0x308  brfalse.s loc_384
0x30a  ldarg.1
0x30b  ldarg.2
0x30c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig> Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.INoActivityCardHandler::GetNoActivityCardsConfiguration(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x311  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::GetEnumerator()
0x316  stloc.1
0x317  br.s     loc_32B
0x319  ldloca.s 1
0x31b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::get_Current()
0x320  stloc.2
0x321  ldloc.0
0x322  ldarg.1
0x323  ldloc.2
0x324  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.INoActivityCardHandler::CreateConfigBasedNoActivityCards(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig actionCardConfig)
0x329  add
0x32a  stloc.0
0x32b  ldloca.s 1
0x32d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>::MoveNext()
0x332  brtrue.s loc_319
0x334  leave.s  loc_344
0x336  ldloca.s 1
0x338  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig>
0x33e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x343  endfinally
0x344  ldarg.0
0x345  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x34a  ldstr    aCreatenoactivi// "CreateNoActivityCards"
0x34f  ldarg.0
0x350  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x355  ldstr    aAsynchandlerAc// "AsyncHandler::ActionCardAsyncOperation:"...
0x35a  ldstr    aTotalNoActivit// "Total No Activity cards created on UTC:"...
0x35f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x364  box      [mscorlib]System.DateTime
0x369  ldloc.0
0x36a  box      [mscorlib]System.Int32
0x36f  call     string [mscorlib]System.String::Format(string, object, object)
0x374  ldsfld   string [mscorlib]System.String::Empty
0x379  ldarg.0
0x37a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x37f  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x384  ret
```
