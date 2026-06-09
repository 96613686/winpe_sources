# Microsoft.Crm.ObjectModel.AppModuleService::PublishAppConfigForAppModule

- ea: `0x92a80`
- end: `0x92b27`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::PublishAppConfigForAppModule`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x926d0`

## callees

- `0x92a80`
- `0x94a20`
- `0x94b00`
- `0x140260`
- `0x1405e0`
- `0x140720`

## string_xrefs

- `0x92a81`: `AppConfig`
- `0x92aa2`: `AppConfig`
- `0x92b15`: `AppConfig`
- `0x92aaf`: `appconfigid`
- `0x92ad5`: `appconfigid`
- `0x92ab7`: `appconfigidunique`
- `0x92aec`: `appconfigidunique`

## pseudocode

```c

```

## disassembly

```asm
0x92a80  ldarg.0
0x92a81  ldstr    aAppconfig// "AppConfig"
0x92a86  ldstr    aAppmoduleid// "appmoduleid"
0x92a8b  ldc.i4.1
0x92a8c  newarr   [mscorlib]System.Guid
0x92a91  dup
0x92a92  ldc.i4.0
0x92a93  ldarg.1
0x92a94  stelem   [mscorlib]System.Guid
0x92a99  ldarg.2
0x92a9a  ldc.i4.1
0x92a9b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression Microsoft.Crm.ObjectModel.AppModuleService::GetFilterExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool onlyUnpublishedData)
0x92aa0  stloc.1
0x92aa1  ldarg.0
0x92aa2  ldstr    aAppconfig// "AppConfig"
0x92aa7  ldc.i4.2
0x92aa8  newarr   [mscorlib]System.String
0x92aad  dup
0x92aae  ldc.i4.0
0x92aaf  ldstr    aAppconfigid// "appconfigid"
0x92ab4  stelem.ref
0x92ab5  dup
0x92ab6  ldc.i4.1
0x92ab7  ldstr    aAppconfigiduni// "appconfigidunique"
0x92abc  stelem.ref
0x92abd  ldloc.1
0x92abe  ldarg.2
0x92abf  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppModuleService::RetrieveRecords(string platformName, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression filter, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92ac4  stloc.0
0x92ac5  ldloc.0
0x92ac6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x92acb  ldc.i4.0
0x92acc  ble.s    loc_92B26
0x92ace  ldloc.0
0x92acf  ldc.i4.0
0x92ad0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x92ad5  ldstr    aAppconfigid// "appconfigid"
0x92ada  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x92adf  unbox.any [mscorlib]System.Guid
0x92ae4  stloc.2
0x92ae5  ldloc.0
0x92ae6  ldc.i4.0
0x92ae7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x92aec  ldstr    aAppconfigiduni// "appconfigidunique"
0x92af1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x92af6  unbox.any [mscorlib]System.Guid
0x92afb  stloc.3
0x92afc  ldarg.2
0x92afd  newobj   instance void Microsoft.Crm.ObjectModel.AppConfigPublisher::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92b02  dup
0x92b03  ldloc.2
0x92b04  ldloc.3
0x92b05  ldarg.2
0x92b06  callvirt instance void Microsoft.Crm.ObjectModel.AppConfigPublisher::PublishAppConfigInstances(valuetype [mscorlib]System.Guid appconfigID, valuetype [mscorlib]System.Guid appconfigidUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92b0b  ldloc.2
0x92b0c  ldloc.3
0x92b0d  ldarg.2
0x92b0e  callvirt instance void Microsoft.Crm.ObjectModel.AppConfigPublisher::PublishNavigationSettings(valuetype [mscorlib]System.Guid appconfigID, valuetype [mscorlib]System.Guid appconfigidUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92b13  ldarg.0
0x92b14  ldloc.2
0x92b15  ldstr    aAppconfig// "AppConfig"
0x92b1a  ldarg.2
0x92b1b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x92b20  ldarg.2
0x92b21  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::PublishShared(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92b26  ret
```
