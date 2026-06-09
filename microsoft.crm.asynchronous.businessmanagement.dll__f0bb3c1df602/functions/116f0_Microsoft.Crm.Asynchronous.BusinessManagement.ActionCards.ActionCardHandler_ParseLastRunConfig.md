# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::ParseLastRunConfig

- ea: `0x116f0`
- end: `0x11735`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::ParseLastRunConfig`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x150`
- `0x630`

## callees

- `0x116f0`

## string_xrefs

- `0x116fc`: `Unable to parse the last async run configuration Critical Error`
- `0x11712`: `AsyncHandler::ActionCardHandler::ProcessRunConfig`
- `0x11718`: `failed to parse the last run config from async this is crictical error config data {0}`

## pseudocode

```c

```

## disassembly

```asm
0x116f0  ldnull
0x116f1  stloc.0
0x116f2  ldarg.1
0x116f3  ldloca.s 0
0x116f5  call     T0x2B000028
0x116fa  brtrue.s loc_11733
0x116fc  ldstr    aUnableToParseT// "Unable to parse the last async run conf"...
0x11701  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x11706  ldarg.0
0x11707  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_cardsTrace
0x1170c  ldarg.0
0x1170d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_organizationId
0x11712  ldstr    aAsynchandlerAc_10// "AsyncHandler::ActionCardHandler::Proces"...
0x11717  ldc.i4.2
0x11718  ldstr    aFailedToParseT// "failed to parse the last run config fro"...
0x1171d  ldarg.1
0x1171e  call     string [mscorlib]System.String::Format(string, object)
0x11723  ldsfld   string [mscorlib]System.String::Empty
0x11728  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1172d  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x11732  throw
0x11733  ldloc.0
0x11734  ret
```
