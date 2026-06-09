# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::IsMapControlFeatureAvailable

- ea: `0x118a0`
- end: `0x11985`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::IsMapControlFeatureAvailable`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x117b0`

## callees

- `0x118a0`

## string_xrefs

- `0x1194e`: `ExecuteHandlersCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x118a0  ldloca.s 0
0x118a2  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x118a8  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x118ad  ldstr    aBfdatacenter// "BFDatacenter"
0x118b2  ldc.i4.0
0x118b3  callvirt T0x2B00002A
0x118b8  stloc.0
0x118b9  leave.s  loc_118FE
0x118bb  stloc.3
0x118bc  ldarg.0
0x118bd  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_cardsTrace
0x118c2  ldarg.0
0x118c3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_organizationId
0x118c8  ldstr    aAsynchandlerAc_12// "AsyncHandler::ActionCardHandler::IsMapC"...
0x118cd  ldc.i4.2
0x118ce  ldstr    aErrorWhileRetr_0// "Error while retrieving BFData Center Se"...
0x118d3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x118d8  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x118dd  box      [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku
0x118e2  ldloc.3
0x118e3  callvirt instance string [mscorlib]System.Object::ToString()
0x118e8  call     string [mscorlib]System.String::Format(string, object, object)
0x118ed  ldsfld   string [mscorlib]System.String::Empty
0x118f2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x118f7  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x118fc  leave.s  loc_118FE
0x118fe  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x11903  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x11908  ldc.i4.2
0x11909  bne.un.s loc_11920
0x1190b  ldloca.s 0
0x1190d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x11912  brfalse.s loc_1191D
0x11914  ldloca.s 0
0x11916  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1191b  br.s     loc_11921
0x1191d  ldc.i4.0
0x1191e  br.s     loc_11921
0x11920  ldc.i4.0
0x11921  stloc.2
0x11922  ldloc.2
0x11923  brtrue.s loc_11946
0x11925  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1192a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1192f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MapControlEnabled()
0x11934  ldarg.0
0x11935  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_organizationId
0x1193a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1193f  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11944  br.s     loc_11947
0x11946  ldc.i4.0
0x11947  stloc.1
0x11948  ldarg.0
0x11949  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_cardsTrace
0x1194e  ldstr    aExecutehandler_0// "ExecuteHandlersCompleted"
0x11953  ldarg.0
0x11954  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.ActionCardHandler::_organizationId
0x11959  ldstr    aAsynchandlerAc_12// "AsyncHandler::ActionCardHandler::IsMapC"...
0x1195e  ldstr    aValueOfIsmapco// "value of isMapControlFeatureAvailable i"...
0x11963  ldloc.1
0x11964  box      [mscorlib]System.Boolean
0x11969  ldloc.2
0x1196a  box      [mscorlib]System.Boolean
0x1196f  call     string [mscorlib]System.String::Format(string, object, object)
0x11974  ldsfld   string [mscorlib]System.String::Empty
0x11979  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1197e  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardInformational(string, valuetype [mscorlib]System.Guid, string, string, string, valuetype [mscorlib]System.Guid)
0x11983  ldloc.1
0x11984  ret
```
