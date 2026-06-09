# Microsoft.Crm.Asynchronous.EmailConnector.CrmSdkRequestExecutor::.ctor

- ea: `0x4db80`
- end: `0x4dbbd`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmSdkRequestExecutor::.ctor`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x311a0`
- `0x49b00`
- `0x526e0`
- `0x5a780`

## string_xrefs

- `0x4db9d`: `mailboxAccessConfiguration`
- `0x4db87`: `crmOrganizationService`

## pseudocode

```c

```

## disassembly

```asm
0x4db80  ldarg.0
0x4db81  call     instance void [mscorlib]System.Object::.ctor()
0x4db86  ldarg.1
0x4db87  ldstr    aCrmorganizatio// "crmOrganizationService"
0x4db8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4db91  ldarg.2
0x4db92  ldstr    aActivityprovid// "activityProviderContext"
0x4db97  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4db9c  ldarg.3
0x4db9d  ldstr    aMailboxaccessc// "mailboxAccessConfiguration"
0x4dba2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4dba7  ldarg.0
0x4dba8  ldarg.1
0x4dba9  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.CrmSdkRequestExecutor::crmOrganizationService
0x4dbae  ldarg.0
0x4dbaf  ldarg.2
0x4dbb0  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext Microsoft.Crm.Asynchronous.EmailConnector.CrmSdkRequestExecutor::activityProviderContext
0x4dbb5  ldarg.0
0x4dbb6  ldarg.3
0x4dbb7  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.CrmSdkRequestExecutor::mailboxAccessConfiguration
0x4dbbc  ret
```
