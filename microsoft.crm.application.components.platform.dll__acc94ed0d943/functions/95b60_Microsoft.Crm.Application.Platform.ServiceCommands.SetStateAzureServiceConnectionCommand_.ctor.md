# Microsoft.Crm.Application.Platform.ServiceCommands.SetStateAzureServiceConnectionCommand::.ctor

- ea: `0x95b60`
- end: `0x95ba9`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.SetStateAzureServiceConnectionCommand::.ctor`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5aae0`

## callees

- `0x6a810`
- `0x90d10`
- `0x90e40`

## string_xrefs

- `0x95b61`: `azureserviceconnection`
- `0x95b7b`: `azureserviceconnection`

## pseudocode

```c

```

## disassembly

```asm
0x95b60  ldarg.0
0x95b61  ldstr    aAzureserviceco// "azureserviceconnection"
0x95b66  ldarg.s  5
0x95b68  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x95b6d  ldarg.s  5
0x95b6f  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class Microsoft.Crm.Application.Platform.EntityType entityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x95b74  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::.ctor()
0x95b79  stloc.0
0x95b7a  ldloc.0
0x95b7b  ldstr    aAzureserviceco// "azureserviceconnection"
0x95b80  ldarg.1
0x95b81  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x95b86  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_EntityMoniker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x95b8b  ldloc.0
0x95b8c  ldarg.2
0x95b8d  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_State(int32)
0x95b92  ldloc.0
0x95b93  ldarg.3
0x95b94  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_Status(int32)
0x95b99  ldloc.0
0x95b9a  ldarg.s  4
0x95b9c  callvirt instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_CascadeModelState(bool)
0x95ba1  ldarg.0
0x95ba2  ldloc.0
0x95ba3  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest value)
0x95ba8  ret
```
