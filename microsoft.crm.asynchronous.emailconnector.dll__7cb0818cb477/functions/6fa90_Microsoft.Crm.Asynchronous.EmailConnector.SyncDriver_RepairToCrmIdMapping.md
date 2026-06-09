# Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::RepairToCrmIdMapping

- ea: `0x6fa90`
- end: `0x6fb0e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::RepairToCrmIdMapping`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6f810`

## callees

- `0x549d0`
- `0x58c10`
- `0x5a9e0`
- `0x5eac0`
- `0x5eb40`
- `0x6f5f0`
- `0x6f600`
- `0x6fa90`
- `0x6fb10`
- `0x702a0`
- `0x702d0`
- `0x70990`

## string_xrefs

- `0x6fa97`: `RepairToCrmIdMapping`
- `0x6faf9`: `RepairToCrmIdMapping`

## pseudocode

```c

```

## disassembly

```asm
0x6fa90  ldc.i4.0
0x6fa91  ldarg.0
0x6fa92  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_Context()
0x6fa97  ldstr    aRepairtocrmidm// "RepairToCrmIdMapping"
0x6fa9c  ldstr    asc_8A7C2// ""
0x6faa1  ldstr    asc_8A7C2// ""
0x6faa6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x6faab  ldarg.0
0x6faac  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_StepContext()
0x6fab1  ldarg.2
0x6fab2  ldarg.1
0x6fab3  ldc.i4.1
0x6fab4  ldarg.3
0x6fab5  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext stepContext, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo inputSyncInfo, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo outputSyncInfo, valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType itemChangeType, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x6faba  stloc.0
0x6fabb  ldloc.0
0x6fabc  brfalse.s loc_6FAF2
0x6fabe  ldarg.2
0x6fabf  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_SyncItem()
0x6fac4  stloc.1
0x6fac5  ldarg.0
0x6fac6  ldloc.0
0x6fac7  ldloc.1
0x6fac8  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::CheckGlobalIdMatch(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase fromCrmItem, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase toCrmItem)
0x6facd  brfalse.s loc_6FAF2
0x6facf  ldarg.0
0x6fad0  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_StepContext()
0x6fad5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x6fada  ldloc.0
0x6fadb  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_FromCrmId()
0x6fae0  ldloc.1
0x6fae1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ToCrmId()
0x6fae6  ldarg.2
0x6fae7  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemObjectType()
0x6faec  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::AddExchangeSyncIdMapping(string crmId, string exchangeEntryId, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType)
0x6faf1  pop
0x6faf2  ldc.i4.1
0x6faf3  ldarg.0
0x6faf4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_Context()
0x6faf9  ldstr    aRepairtocrmidm// "RepairToCrmIdMapping"
0x6fafe  ldstr    asc_8A7C2// ""
0x6fb03  ldstr    asc_8A7C2// ""
0x6fb08  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x6fb0d  ret
```
