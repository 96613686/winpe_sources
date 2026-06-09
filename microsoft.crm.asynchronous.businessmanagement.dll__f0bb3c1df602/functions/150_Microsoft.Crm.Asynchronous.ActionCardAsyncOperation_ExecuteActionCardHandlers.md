# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::ExecuteActionCardHandlers

- ea: `0x150`
- end: `0x2fb`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::ExecuteActionCardHandlers`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x50`

## callees

- `0x150`
- `0x300`
- `0x390`
- `0x520`
- `0x850`
- `0x10b00`
- `0x10b30`
- `0x115b0`
- `0x116f0`
- `0x11c40`
- `0x122e0`
- `0x13760`
- `0x13780`

## string_xrefs

- `0x1dd`: `RunConfig`
- `0x1ed`: `ActionCard Run Config settings are Last Runstart time  : {0} and Last RunEnd Time : {1} `
- `0x256`: `ExecuteHandlersCompleted`
- `0x26c`: `Completed processing all Action card Async Handlers at UTC: {0}. Total time taken: {1}`
- `0x29b`: `Completed processing all Action card Async Handlers at UTC: {0}`
- `0x2cc`: `Action card Async Operation could not complete.\n Error Details: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x150  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x155  stloc.0
0x156  ldloc.0
0x157  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x15c  ldarg.0
0x15d  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x162  ldstr    aExecutehandler// "ExecuteHandlersStarted"
0x167  ldarg.0
0x168  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x16d  ldstr    aAsynchandlerEx// "AsyncHandler::ExecuteActionCardHandlers"
0x172  ldstr    aStartedProcess// "started processing all Action card Asyn"...
0x177  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x17c  box      [mscorlib]System.DateTime
0x181  call     string [mscorlib]System.String::Format(string, object)
0x186  ldsfld   string [mscorlib]System.String::Empty
0x18b  ldarg.0
0x18c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x191  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x196  ldarg.1
0x197  ldarg.0
0x198  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x19d  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, valuetype [mscorlib]System.Guid organizationId)
0x1a2  stloc.1
0x1a3  ldarg.1
0x1a4  ldloc.1
0x1a5  ldarg.0
0x1a6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x1ab  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler actionCardHandler, valuetype [mscorlib]System.Guid organizationId)
0x1b0  stloc.2
0x1b1  ldarg.1
0x1b2  ldloc.1
0x1b3  ldarg.0
0x1b4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x1b9  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler actionCardHandler, valuetype [mscorlib]System.Guid organizationId)
0x1be  stloc.3
0x1bf  ldarg.1
0x1c0  ldloc.1
0x1c1  ldarg.0
0x1c2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x1c7  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler actionCardHandler, valuetype [mscorlib]System.Guid organizationId)
0x1cc  stloc.s  4
0x1ce  ldloc.1
0x1cf  ldarg.2
0x1d0  callvirt instance class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::ParseLastRunConfig(string configData)
0x1d5  stloc.s  5
0x1d7  ldarg.0
0x1d8  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x1dd  ldstr    aRunconfig// "RunConfig"
0x1e2  ldarg.0
0x1e3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x1e8  ldstr    aAsynchandlerEx// "AsyncHandler::ExecuteActionCardHandlers"
0x1ed  ldstr    aActioncardRunC// "ActionCard Run Config settings are Last"...
0x1f2  ldloc.s  5
0x1f4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x1f9  box      [mscorlib]System.DateTime
0x1fe  ldloc.s  5
0x200  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunEndTime()
0x205  box      [mscorlib]System.DateTime
0x20a  call     string [mscorlib]System.String::Format(string, object, object)
0x20f  ldsfld   string [mscorlib]System.String::Empty
0x214  ldarg.0
0x215  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x21a  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x21f  ldloc.3
0x220  ldloc.s  5
0x222  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActivityCardHandler::CreateActivityCards(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x227  pop
0x228  ldarg.0
0x229  ldloc.s  4
0x22b  ldloc.s  5
0x22d  call     instance void Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CreateOpportunityCards(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IOpportunityActionCardHandler opportunityCardHandler, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x232  ldarg.0
0x233  ldloc.2
0x234  ldloc.s  5
0x236  call     instance void Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CreateNoActivityCards(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.INoActivityCardHandler noActivityCardHandler, class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig)
0x23b  ldarg.0
0x23c  ldloc.s  5
0x23e  ldarg.1
0x23f  call     instance void Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::UpdateLastRunConfiguration(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig runConfig, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x244  ldarg.0
0x245  call     instance void Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CleanStaleActionCards()
0x24a  ldloc.0
0x24b  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x250  ldarg.0
0x251  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x256  ldstr    aExecutehandler_0// "ExecuteHandlersCompleted"
0x25b  ldarg.0
0x25c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x261  ldstr    aAsynchandlerEx// "AsyncHandler::ExecuteActionCardHandlers"
0x266  ldloc.0
0x267  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x26c  ldstr    aCompletedProce// "Completed processing all Action card As"...
0x271  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x276  box      [mscorlib]System.DateTime
0x27b  ldloc.0
0x27c  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x281  box      [mscorlib]System.Int64
0x286  call     string [mscorlib]System.String::Format(string, object, object)
0x28b  ldsfld   string [mscorlib]System.String::Empty
0x290  ldarg.0
0x291  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x296  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardTimeTaken(string, valuetype [mscorlib]System.Guid, string, int64, string, string, valuetype [mscorlib]System.Guid)
0x29b  ldstr    aCompletedProce_0// "Completed processing all Action card As"...
0x2a0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2a5  box      [mscorlib]System.DateTime
0x2aa  call     string [mscorlib]System.String::Format(string, object)
0x2af  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0x2b4  stloc.s  6
0x2b6  leave.s  loc_2F8
0x2b8  stloc.s  7
0x2ba  ldarg.0
0x2bb  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x2c0  ldarg.0
0x2c1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x2c6  ldstr    aAsynchandlerEx// "AsyncHandler::ExecuteActionCardHandlers"
0x2cb  ldc.i4.2
0x2cc  ldstr    aActionCardAsyn_0// "Action card Async Operation could not c"...
0x2d1  ldloc.s  7
0x2d3  callvirt instance string [mscorlib]System.Object::ToString()
0x2d8  call     string [mscorlib]System.String::Format(string, object)
0x2dd  ldsfld   string [mscorlib]System.String::Empty
0x2e2  ldarg.0
0x2e3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x2e8  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x2ed  ldloc.s  7
0x2ef  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x2f4  stloc.s  6
0x2f6  leave.s  loc_2F8
0x2f8  ldloc.s  6
0x2fa  ret
```
