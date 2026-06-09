# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::GetOpportunityCardsConfiguration

- ea: `0x127d0`
- end: `0x128cd`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::GetOpportunityCardsConfiguration`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x11b70`
- `0x136f0`
- `0x13760`

## string_xrefs

- `0x12850`: `ActionCard.CloseDateComingSoon.Title`
- `0x12855`: `ActionCard.CloseDateComingSoon.Body`
- `0x1285a`: `ActionCard.CloseDateComingSoon.MiniCardText`

## pseudocode

```c

```

## disassembly

```asm
0x127d0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x127d5  ldarg.1
0x127d6  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x127db  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x127e0  stloc.2
0x127e1  ldloca.s 2
0x127e3  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x127e8  conv.i4
0x127e9  stloc.0
0x127ea  ldloc.0
0x127eb  ldc.i4.1
0x127ec  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x127f1  stloc.0
0x127f2  ldarg.0
0x127f3  ldfld    class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityActionCardHandler::_actionCardHandler
0x127f8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::CloseDateComingSoon
0x127fd  ldc.i4.0
0x127fe  callvirt instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.IActionCardHandler::GetCardOptionAgeFromUserSettings(valuetype [mscorlib]System.Guid actionCardTypeId, int32 defaultValue)
0x12803  stloc.1
0x12804  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>::.ctor()
0x12809  dup
0x1280a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::CloseDateComingSoon
0x1280f  ldc.i4.s 0x14
0x12811  ldc.i4.3
0x12812  ldarg.1
0x12813  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x12818  stloc.3
0x12819  ldloca.s 3
0x1281b  ldc.i4.7
0x1281c  ldloc.1
0x1281d  add
0x1281e  conv.r8
0x1281f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x12824  stloc.3
0x12825  ldloca.s 3
0x12827  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1282c  ldarg.1
0x1282d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x12832  stloc.3
0x12833  ldloca.s 3
0x12835  ldc.i4.7
0x12836  ldloc.1
0x12837  add
0x12838  ldloc.0
0x12839  add
0x1283a  conv.r8
0x1283b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x12840  stloc.3
0x12841  ldloca.s 3
0x12843  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x12848  ldc.i4   0x258
0x1284d  ldloc.1
0x1284e  neg
0x1284f  ldc.i4.1
0x12850  ldstr    aActioncardClos// "ActionCard.CloseDateComingSoon.Title"
0x12855  ldstr    aActioncardClos_0// "ActionCard.CloseDateComingSoon.Body"
0x1285a  ldstr    aActioncardClos_1// "ActionCard.CloseDateComingSoon.MiniCard"...
0x1285f  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, int32 entityTypeCode, valuetype [mscorlib]System.DateTime queryStartDate, valuetype [mscorlib]System.DateTime queryEndDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, int32 daysToStartCard, int32 daysToEndCard, string titleResourceId, string bodyResourceId, string miniCardResourceId)
0x12864  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>::Add(var<u1>)
0x12869  dup
0x1286a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardTypes::MissedCloseDate
0x1286f  ldc.i4.s 0x10
0x12871  ldc.i4.3
0x12872  ldarg.1
0x12873  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x12878  stloc.3
0x12879  ldloca.s 3
0x1287b  ldc.r8   6.0
0x12884  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x12889  stloc.3
0x1288a  ldloca.s 3
0x1288c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x12891  ldarg.1
0x12892  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.RunConfig::get_LastRunStartTime()
0x12897  stloc.3
0x12898  ldloca.s 3
0x1289a  ldc.i4.6
0x1289b  ldloc.0
0x1289c  add
0x1289d  conv.r8
0x1289e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x128a3  stloc.3
0x128a4  ldloca.s 3
0x128a6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x128ab  ldc.i4   0x190
0x128b0  ldc.i4.1
0x128b1  ldc.i4.s 0xF
0x128b3  ldstr    aActioncardMiss// "ActionCard.MissedCloseDate.Title"
0x128b8  ldstr    aActioncardMiss_0// "ActionCard.MissedCloseDate.Body"
0x128bd  ldstr    aActioncardMiss_1// "ActionCard.MissedCloseDate.MiniCardText"
0x128c2  newobj   instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig::.ctor(valuetype [mscorlib]System.Guid associatedActionCardTypeId, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardType cardType, int32 entityTypeCode, valuetype [mscorlib]System.DateTime queryStartDate, valuetype [mscorlib]System.DateTime queryEndDate, valuetype Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardPriority priority, int32 daysToStartCard, int32 daysToEndCard, string titleResourceId, string bodyResourceId, string miniCardResourceId)
0x128c7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OpportunityCardConfig>::Add(var<u1>)
0x128cc  ret
```
