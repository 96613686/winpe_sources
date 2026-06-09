# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::.ctor

- ea: `0x57ab0`
- end: `0x57b5d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::.ctor`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5a780`

## callees

- `0x7d00`
- `0x42280`
- `0x57ab0`
- `0x57b60`
- `0x57c60`
- `0x58a20`

## string_xrefs

- `0x57afd`: `exchangesyncstatexml`
- `0x57b16`: `exchangesyncstatexml`

## pseudocode

```c

```

## disassembly

```asm
0x57ab0  ldarg.0
0x57ab1  ldc.i4.1
0x57ab2  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_incrementalRebuildIdMappingSuccess
0x57ab7  ldarg.0
0x57ab8  call     instance void [mscorlib]System.Object::.ctor()
0x57abd  ldarg.0
0x57abe  ldarg.1
0x57abf  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_crmService
0x57ac4  ldarg.0
0x57ac5  ldarg.2
0x57ac6  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57acb  ldarg.0
0x57acc  ldarg.0
0x57acd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_context
0x57ad2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeACTAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext::get_ACTAccessConfiguration()
0x57ad7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x57adc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x57ae1  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToStringValue(valuetype [mscorlib]System.Guid propertyValue)
0x57ae6  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailboxId
0x57aeb  ldarg.0
0x57aec  ldarg.0
0x57aed  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::RetrieveSyncState()
0x57af2  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x57af7  ldarg.0
0x57af8  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x57afd  ldstr    aExchangesyncst// "exchangesyncstatexml"
0x57b02  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x57b07  brtrue.s loc_57B10
0x57b09  ldsfld   string [mscorlib]System.String::Empty
0x57b0e  br.s     loc_57B25
0x57b10  ldarg.0
0x57b11  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x57b16  ldstr    aExchangesyncst// "exchangesyncstatexml"
0x57b1b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x57b20  castclass [mscorlib]System.String
0x57b25  stloc.0
0x57b26  ldarg.0
0x57b27  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x57b2c  ldstr    aOrgmarkedaspri// "orgmarkedasprimaryforexchangesync"
0x57b31  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x57b36  brfalse.s loc_57B55
0x57b38  ldarg.0
0x57b39  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::_mailbox
0x57b3e  ldstr    aOrgmarkedaspri// "orgmarkedasprimaryforexchangesync"
0x57b43  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x57b48  unbox.any [mscorlib]System.Boolean
0x57b4d  brfalse.s loc_57B55
0x57b4f  ldsfld   string [mscorlib]System.String::Empty
0x57b54  stloc.0
0x57b55  ldarg.0
0x57b56  ldloc.0
0x57b57  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncStateService::DeserializeXml(string exchangeSyncStateXml)
0x57b5c  ret
```
