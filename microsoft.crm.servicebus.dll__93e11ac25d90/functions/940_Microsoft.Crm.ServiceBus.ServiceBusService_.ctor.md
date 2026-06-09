# Microsoft.Crm.ServiceBus.ServiceBusService::.ctor

- ea: `0x940`
- end: `0x96d`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::.ctor`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x910`
- `0x9a0`

## string_xrefs

- `0x947`: `service`
- `0x952`: `authService`

## pseudocode

```c

```

## disassembly

```asm
0x940  ldarg.0
0x941  call     instance void [mscorlib]System.Object::.ctor()
0x946  ldarg.1
0x947  ldstr    aService// "service"
0x94c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x951  ldarg.2
0x952  ldstr    aAuthservice// "authService"
0x957  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x95c  ldarg.0
0x95d  ldarg.1
0x95e  ldarg.2
0x95f  ldnull
0x960  ldnull
0x961  call     instance void Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusServiceInternal(class Microsoft.Crm.ServiceBus.IInternalServiceEndpointService service, class Microsoft.Crm.ServiceBus.IInternalAuthenticationTokenService authService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory orgServiceFactory, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x966  ldarg.0
0x967  call     instance void Microsoft.Crm.ServiceBus.ServiceBusService::InitializeExceptionConverter()
0x96c  ret
```
