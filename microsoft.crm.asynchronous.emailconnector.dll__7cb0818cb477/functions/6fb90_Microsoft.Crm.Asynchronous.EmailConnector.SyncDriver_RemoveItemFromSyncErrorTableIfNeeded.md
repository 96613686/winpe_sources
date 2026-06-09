# Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::RemoveItemFromSyncErrorTableIfNeeded

- ea: `0x6fb90`
- end: `0x6fc4c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::RemoveItemFromSyncErrorTableIfNeeded`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x7e5b0`
- `0x807d0`
- `0x80d00`

## callees

- `0x54a00`
- `0x54a20`
- `0x54d20`
- `0x54d70`
- `0x54dc0`
- `0x58c10`
- `0x5a9e0`
- `0x5eb20`
- `0x5f150`
- `0x5f170`
- `0x5f190`
- `0x5f1a0`
- `0x6f5f0`
- `0x6f600`
- `0x6fb90`

## string_xrefs

- `0x6fb97`: `RemoveItemFromSyncErrorTableIfNeeded`
- `0x6fc37`: `RemoveItemFromSyncErrorTableIfNeeded`

## pseudocode

```c

```

## disassembly

```asm
0x6fb90  ldc.i4.0
0x6fb91  ldarg.0
0x6fb92  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_Context()
0x6fb97  ldstr    aRemoveitemfrom// "RemoveItemFromSyncErrorTableIfNeeded"
0x6fb9c  ldstr    asc_8A7C2// ""
0x6fba1  ldstr    asc_8A7C2// ""
0x6fba6  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x6fbab  ldarg.1
0x6fbac  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x6fbb1  brfalse.s loc_6FC30
0x6fbb3  ldarg.1
0x6fbb4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x6fbb9  brfalse.s loc_6FC30
0x6fbbb  ldarg.1
0x6fbbc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_CrmSyncItemChangeInfo()
0x6fbc1  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemChangeType()
0x6fbc6  ldc.i4.2
0x6fbc7  beq.s    loc_6FBD7
0x6fbc9  ldarg.1
0x6fbca  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSideSyncItemChangeInfo()
0x6fbcf  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemChangeType()
0x6fbd4  ldc.i4.2
0x6fbd5  bne.un.s loc_6FBF6
0x6fbd7  ldarg.0
0x6fbd8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_StepContext()
0x6fbdd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x6fbe2  ldarg.1
0x6fbe3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x6fbe8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::DeleteExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x6fbed  ldarg.1
0x6fbee  ldnull
0x6fbef  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncData::set_ExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper value)
0x6fbf4  br.s     loc_6FC30
0x6fbf6  ldarg.1
0x6fbf7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x6fbfc  ldc.i4.m1
0x6fbfd  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_Retries(int32 value)
0x6fc02  ldarg.1
0x6fc03  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x6fc08  ldc.i4.0
0x6fc09  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_ToCrmChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x6fc0e  ldarg.1
0x6fc0f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x6fc14  ldc.i4.0
0x6fc15  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_FromCrmChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x6fc1a  ldarg.0
0x6fc1b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_StepContext()
0x6fc20  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorkerStepContext::get_ExchangeSyncIdMappingOperations()
0x6fc25  ldarg.1
0x6fc26  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper Microsoft.Crm.Asynchronous.EmailConnector.SyncData::get_ExchangeSyncIdMapping()
0x6fc2b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x6fc30  ldc.i4.1
0x6fc31  ldarg.0
0x6fc32  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncDriver::get_Context()
0x6fc37  ldstr    aRemoveitemfrom// "RemoveItemFromSyncErrorTableIfNeeded"
0x6fc3c  ldstr    asc_8A7C2// ""
0x6fc41  ldstr    asc_8A7C2// ""
0x6fc46  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x6fc4b  ret
```
