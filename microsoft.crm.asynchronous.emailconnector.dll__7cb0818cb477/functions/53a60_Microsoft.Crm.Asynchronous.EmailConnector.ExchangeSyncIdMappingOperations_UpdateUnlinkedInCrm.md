# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::UpdateUnlinkedInCrm

- ea: `0x53a60`
- end: `0x53ad4`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::UpdateUnlinkedInCrm`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x53a20`
- `0x54b30`
- `0x54b60`
- `0x54bb0`
- `0x54c00`
- `0x54cd0`
- `0x71300`

## string_xrefs

- `0x53a90`: `Updated as Unlinked in CRM for the IdMapping with Mapping id {0}, Exchange id {1}, Crm id {2}, Item ObjectType {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x53a60  ldarg.1
0x53a61  ldstr    aExchangesyncid_3// "exchangeSyncIdMapping"
0x53a66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x53a6b  ldarg.1
0x53a6c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x53a71  ldstr    aExchangesyncid_4// "exchangeSyncIdMapping.ExchangeSyncIdMap"...
0x53a76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x53a7b  ldarg.1
0x53a7c  ldarg.2
0x53a7d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::set_IsUnlinkedInCrm(bool value)
0x53a82  ldarg.0
0x53a83  ldarg.1
0x53a84  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::UpdateExchangeSyncIdMapping(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper exchangeSyncIdMapping)
0x53a89  ldarg.0
0x53a8a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::traceHandler
0x53a8f  ldc.i4.4
0x53a90  ldstr    aUpdatedAsUnlin// "Updated as Unlinked in CRM for the IdMa"...
0x53a95  ldc.i4.4
0x53a96  newarr   [mscorlib]System.Object
0x53a9b  dup
0x53a9c  ldc.i4.0
0x53a9d  ldarg.1
0x53a9e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeSyncIdMappingId()
0x53aa3  box      [mscorlib]System.Guid
0x53aa8  stelem.ref
0x53aa9  dup
0x53aaa  ldc.i4.1
0x53aab  ldarg.1
0x53aac  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x53ab1  stelem.ref
0x53ab2  dup
0x53ab3  ldc.i4.2
0x53ab4  ldarg.1
0x53ab5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_CrmId()
0x53aba  box      [mscorlib]System.Guid
0x53abf  stelem.ref
0x53ac0  dup
0x53ac1  ldc.i4.3
0x53ac2  ldarg.1
0x53ac3  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ItemObjectType()
0x53ac8  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x53acd  stelem.ref
0x53ace  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x53ad3  ret
```
