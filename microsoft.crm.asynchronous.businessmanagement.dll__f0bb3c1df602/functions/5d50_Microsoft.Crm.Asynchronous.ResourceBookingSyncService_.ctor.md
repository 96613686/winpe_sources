# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::.ctor

- ea: `0x5d50`
- end: `0x5da0`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::.ctor`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b90`

## callees

- `0x8aa0`
- `0x8ab0`
- `0x8ac0`
- `0x8ae0`
- `0x8af0`
- `0x8b00`
- `0x13dd0`
- `0x16700`

## pseudocode

```c

```

## disassembly

```asm
0x5d50  ldarg.0
0x5d51  newobj   instance void Metrics::.ctor()
0x5d56  stfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5d5b  ldarg.0
0x5d5c  newobj   instance void ConfigurationSettings::.ctor()
0x5d61  stfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5d66  ldarg.0
0x5d67  call     instance void [mscorlib]System.Object::.ctor()
0x5d6c  ldarg.0
0x5d6d  ldarg.1
0x5d6e  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::set_Context(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext value)
0x5d73  ldarg.0
0x5d74  ldarg.2
0x5d75  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::set_SystemService(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService value)
0x5d7a  ldarg.0
0x5d7b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_Context()
0x5d80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5d85  call     void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x5d8a  ldarg.0
0x5d8b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x5d90  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5d95  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationName(valuetype [mscorlib]System.Guid)
0x5d9a  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::set_OrganizationName(string value)
0x5d9f  ret
```
