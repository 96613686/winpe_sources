# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::CreateConfigBasedNoActivityCards

- ea: `0x11c70`
- end: `0x11e3a`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::CreateConfigBasedNoActivityCards`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x11c70`
- `0x12000`
- `0x120f0`
- `0x13380`
- `0x133a0`
- `0x134a0`

## string_xrefs

- `0x11c88`: `CreateConfigBasedNoActivityCards`
- `0x11d51`: `CreateConfigBasedNoActivityCards`
- `0x11d92`: `CreateConfigBasedNoActivityCards`
- `0x11c93`: `AsyncHandler::NoActivityCardHandler::CreateConfigBasedNoActivityCards`
- `0x11d5c`: `AsyncHandler::NoActivityCardHandler::CreateConfigBasedNoActivityCards`
- `0x11d9d`: `AsyncHandler::NoActivityCardHandler::CreateConfigBasedNoActivityCards`
- `0x11e0a`: `AsyncHandler::NoActivityCardHandler::CreateConfigBasedNoActivityCards`

## pseudocode

```c

```

## disassembly

```asm
0x11c70  ldc.i4.0
0x11c71  stloc.0
0x11c72  ldc.i4.0
0x11c73  stloc.1
0x11c74  ldarg.1
0x11c75  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_QueryStartTime()
0x11c7a  stloc.2
0x11c7b  ldarg.1
0x11c7c  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_QueryEndTime()
0x11c81  stloc.3
0x11c82  ldarg.0
0x11c83  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_cardsTrace
0x11c88  ldstr    aCreateconfigba// "CreateConfigBasedNoActivityCards"
0x11c8d  ldarg.0
0x11c8e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_organizationId
0x11c93  ldstr    aAsynchandlerNo// "AsyncHandler::NoActivityCardHandler::Cr"...
0x11c98  ldstr    aStartdate0AndE_0// "StartDate: {0} and EndDate: {1} for NoA"...
0x11c9d  ldc.i4.4
0x11c9e  newarr   [mscorlib]System.Object
0x11ca3  dup
0x11ca4  ldc.i4.0
0x11ca5  ldloc.2
0x11ca6  box      [mscorlib]System.DateTime
0x11cab  stelem.ref
0x11cac  dup
0x11cad  ldc.i4.1
0x11cae  ldloc.3
0x11caf  box      [mscorlib]System.DateTime
0x11cb4  stelem.ref
0x11cb5  dup
0x11cb6  ldc.i4.2
0x11cb7  ldarg.1
0x11cb8  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityLogicalName()
0x11cbd  stelem.ref
0x11cbe  dup
0x11cbf  ldc.i4.3
0x11cc0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11cc5  box      [mscorlib]System.DateTime
0x11cca  stelem.ref
0x11ccb  call     string [mscorlib]System.String::Format(string, object[])
0x11cd0  ldsfld   string [mscorlib]System.String::Empty
0x11cd5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11cda  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x11cdf  ldarg.0
0x11ce0  ldarg.1
0x11ce1  ldloc.2
0x11ce2  ldloc.3
0x11ce3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::GetNoActivityCardsFetchXml(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig actionCardConfig, valuetype [mscorlib]System.DateTime startDate, valuetype [mscorlib]System.DateTime endDate)
0x11ce8  stloc.s  4
0x11cea  ldarg.0
0x11ceb  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x11cf0  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_timePerParse
0x11cf5  ldarg.0
0x11cf6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_crmService
0x11cfb  ldloc.s  4
0x11cfd  call     T0x2B00002C
0x11d02  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x11d07  stloc.s  5
0x11d09  br.s     loc_11D29
0x11d0b  ldloc.s  5
0x11d0d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x11d12  stloc.s  6
0x11d14  ldarg.0
0x11d15  ldarg.1
0x11d16  ldloc.s  6
0x11d18  call     instance bool Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::TryCreateNoActivityActionCard(class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig actionCardConfig, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x11d1d  brfalse.s loc_11D25
0x11d1f  ldloc.0
0x11d20  ldc.i4.1
0x11d21  add
0x11d22  stloc.0
0x11d23  br.s     loc_11D29
0x11d25  ldloc.1
0x11d26  ldc.i4.1
0x11d27  add
0x11d28  stloc.1
0x11d29  ldloc.s  5
0x11d2b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11d30  brtrue.s loc_11D0B
0x11d32  leave.s  loc_11D40
0x11d34  ldloc.s  5
0x11d36  brfalse.s loc_11D3F
0x11d38  ldloc.s  5
0x11d3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11d3f  endfinally
0x11d40  ldarg.0
0x11d41  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_timePerParse
0x11d46  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x11d4b  ldarg.0
0x11d4c  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_cardsTrace
0x11d51  ldstr    aCreateconfigba// "CreateConfigBasedNoActivityCards"
0x11d56  ldarg.0
0x11d57  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_organizationId
0x11d5c  ldstr    aAsynchandlerNo// "AsyncHandler::NoActivityCardHandler::Cr"...
0x11d61  ldstr    aNoActivityCard// "No Activity Card creation for Entity: {"...
0x11d66  ldarg.1
0x11d67  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityLogicalName()
0x11d6c  ldloc.0
0x11d6d  box      [mscorlib]System.Int32
0x11d72  ldloc.1
0x11d73  box      [mscorlib]System.Int32
0x11d78  call     string [mscorlib]System.String::Format(string, object, object, object)
0x11d7d  ldsfld   string [mscorlib]System.String::Empty
0x11d82  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11d87  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x11d8c  ldarg.0
0x11d8d  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_cardsTrace
0x11d92  ldstr    aCreateconfigba// "CreateConfigBasedNoActivityCards"
0x11d97  ldarg.0
0x11d98  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_organizationId
0x11d9d  ldstr    aAsynchandlerNo// "AsyncHandler::NoActivityCardHandler::Cr"...
0x11da2  ldarg.0
0x11da3  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_timePerParse
0x11da8  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x11dad  ldstr    aNoActivityCard_0// "No Activity Card Creation for {0} on {1"...
0x11db2  ldarg.1
0x11db3  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityLogicalName()
0x11db8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11dbd  stloc.s  7
0x11dbf  ldloca.s 7
0x11dc1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x11dc6  box      [mscorlib]System.DateTime
0x11dcb  ldarg.0
0x11dcc  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_timePerParse
0x11dd1  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x11dd6  box      [mscorlib]System.TimeSpan
0x11ddb  call     string [mscorlib]System.String::Format(string, object, object, object)
0x11de0  ldsfld   string [mscorlib]System.String::Empty
0x11de5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11dea  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardTimeTaken(string, valuetype [mscorlib]System.Guid, string, int64, string, string, valuetype [mscorlib]System.Guid)
0x11def  leave.s  loc_11E38
0x11df1  stloc.s  8
0x11df3  ldarg.0
0x11df4  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_timePerParse
0x11df9  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x11dfe  ldarg.0
0x11dff  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_cardsTrace
0x11e04  ldarg.0
0x11e05  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardHandler::_organizationId
0x11e0a  ldstr    aAsynchandlerNo// "AsyncHandler::NoActivityCardHandler::Cr"...
0x11e0f  ldc.i4.4
0x11e10  ldstr    aFailedToGenera// " failed to generate cards for Entity: {"...
0x11e15  ldarg.1
0x11e16  callvirt instance string Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_EntityLogicalName()
0x11e1b  ldloc.s  8
0x11e1d  callvirt instance string [mscorlib]System.Object::ToString()
0x11e22  call     string [mscorlib]System.String::Format(string, object, object)
0x11e27  ldsfld   string [mscorlib]System.String::Empty
0x11e2c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11e31  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x11e36  leave.s  loc_11E38
0x11e38  ldloc.0
0x11e39  ret
```
