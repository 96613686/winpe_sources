# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLoggerProvider::GetExchangeSyncErrorLogger

- ea: `0x311a0`
- end: `0x31203`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLoggerProvider::GetExchangeSyncErrorLogger`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7d00`
- `0x30f70`
- `0x417a0`
- `0x4db80`
- `0x534e0`
- `0x54980`
- `0x5abe0`
- `0x71200`

## string_xrefs

- `0x311a1`: `organizationService`
- `0x311c3`: `mailboxAccessConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x311a0  ldarg.1
0x311a1  ldstr    aOrganizationse_0// "organizationService"
0x311a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x311ab  ldarg.2
0x311ac  ldstr    aOrganizationse// "organizationSettings"
0x311b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x311b6  ldarg.3
0x311b7  ldstr    aContext// "context"
0x311bc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x311c1  ldarg.s  4
0x311c3  ldstr    aMailboxaccessc// "mailboxAccessConfiguration"
0x311c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x311cd  ldarg.s  4
0x311cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Mailbox()
0x311d4  ldarg.3
0x311d5  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x311da  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.TraceHandler::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData mailbox, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x311df  stloc.0
0x311e0  ldarg.s  4
0x311e2  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingRequestFactory::.ctor()
0x311e7  ldarg.1
0x311e8  ldarg.3
0x311e9  ldarg.s  4
0x311eb  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmSdkRequestExecutor::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmOrganizationService, class Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext activityProviderContext, class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration mailboxAccessConfiguration)
0x311f0  ldloc.0
0x311f1  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingOperations::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration mailboxAccessConfiguration, class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingRequestFactory exchangeSyncIdMappingRequestFactory, class Microsoft.Crm.Asynchronous.EmailConnector.ICrmSdkRequestExecutor crmSdkRequestExecutor, class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler traceHandler)
0x311f6  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorMapper::.ctor()
0x311fb  ldarg.2
0x311fc  ldloc.0
0x311fd  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncErrorLogger::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncIdMappingOperations exchangeSyncIdMappingOperations, class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeSyncErrorMapper exchangeSyncErrorMapper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings organizationSettings, class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler traceHandler)
0x31202  ret
```
