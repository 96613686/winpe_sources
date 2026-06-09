# Microsoft.Crm.ServiceBus.ServiceBusService::.ctor_0

- ea: `0x970`
- end: `0x99d`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::.ctor_0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x910`
- `0x9a0`

## string_xrefs

- `0x977`: `orgServiceFactory`

## pseudocode

```c

```

## disassembly

```asm
0x970  ldarg.0
0x971  call     instance void [mscorlib]System.Object::.ctor()
0x976  ldarg.1
0x977  ldstr    aOrgservicefact// "orgServiceFactory"
0x97c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x981  ldarg.2
0x982  ldstr    aContext// "context"
0x987  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x98c  ldarg.0
0x98d  ldnull
0x98e  ldnull
0x98f  ldarg.1
0x990  ldarg.2
0x991  call     instance void Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusServiceInternal(class Microsoft.Crm.ServiceBus.IInternalServiceEndpointService service, class Microsoft.Crm.ServiceBus.IInternalAuthenticationTokenService authService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory orgServiceFactory, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x996  ldarg.0
0x997  call     instance void Microsoft.Crm.ServiceBus.ServiceBusService::InitializeExceptionConverter()
0x99c  ret
```
