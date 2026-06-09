# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExceptionAppointment::GetRecurringAppointmentFromSeriesId

- ea: `0x69770`
- end: `0x69818`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeExceptionAppointment::GetRecurringAppointmentFromSeriesId`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x69730`

## callees

- `0x549e0`
- `0x54bb0`
- `0x56ec0`
- `0x56f40`
- `0x651e0`
- `0x69770`
- `0x700e0`
- `0x70120`
- `0x70170`
- `0x70190`
- `0x701b0`
- `0x701d0`
- `0x70300`
- `0x70330`
- `0x70b20`

## string_xrefs

- `0x69776`: `seriesid`

## pseudocode

```c

```

## disassembly

```asm
0x69770  ldarg.0
0x69771  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_InputSyncItem()
0x69776  ldstr    aSeriesid// "seriesid"
0x6977b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x69780  stloc.0
0x69781  ldloc.0
0x69782  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x69787  brtrue   loc_69816
0x6978c  ldarg.0
0x6978d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ExchangeSyncIdMappingOperations()
0x69792  ldsfld   string [mscorlib]System.String::Empty
0x69797  ldloc.0
0x69798  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations::RetrieveExchangeSyncIdMappings(string exchangeEntryId, string crmId)
0x6979d  call     T0x2B00009C
0x697a2  stloc.1
0x697a3  ldloc.1
0x697a4  brtrue.s loc_697AD
0x697a6  ldsfld   string [mscorlib]System.String::Empty
0x697ab  br.s     loc_697B3
0x697ad  ldloc.1
0x697ae  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x697b3  stloc.2
0x697b4  ldloc.2
0x697b5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x697ba  brtrue.s loc_69816
0x697bc  ldarg.0
0x697bd  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Provider()
0x697c2  ldloc.2
0x697c3  ldarg.0
0x697c4  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_ItemObjectType()
0x697c9  ldarg.0
0x697ca  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SyncPropertiesMapping()
0x697cf  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IProvider::GetItem(string id, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping syncPropertiesMapping)
0x697d4  castclass [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment
0x697d9  stloc.3
0x697da  ldloc.3
0x697db  brfalse.s loc_69816
0x697dd  ldarg.0
0x697de  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x697e3  ldc.i4   0x109B
0x697e8  ldarg.0
0x697e9  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Provider()
0x697ee  ldloc.3
0x697ef  ldarg.0
0x697f0  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_MailboxId()
0x697f5  ldarg.0
0x697f6  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Context()
0x697fb  ldc.i4.0
0x697fc  call     class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappings Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappingsTable::GetSyncPropertiesMappings(string mailboxId, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, [opt] bool reloadSyncAttributeMapping)
0x69801  ldc.i4   0x109B
0x69806  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappings::GetSyncPropertiesMapping(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType objectType)
0x6980b  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType, class Microsoft.Crm.Asynchronous.EmailConnector.IProvider provider, object item, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping syncPropertiesMapping)
0x69810  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeRecurringAppointment
0x69815  ret
0x69816  ldnull
0x69817  ret
```
