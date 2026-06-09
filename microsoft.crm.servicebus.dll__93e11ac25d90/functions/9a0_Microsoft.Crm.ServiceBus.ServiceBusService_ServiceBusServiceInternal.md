# Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusServiceInternal

- ea: `0x9a0`
- end: `0x9ce`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusServiceInternal`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x940`
- `0x970`

## callees

- `0x9a0`

## pseudocode

```c

```

## disassembly

```asm
0x9a0  ldarg.0
0x9a1  ldarg.1
0x9a2  brfalse.s loc_9A7
0x9a4  ldarg.1
0x9a5  br.s     loc_9AA
0x9a7  ldarg.0
0x9a8  stloc.0
0x9a9  ldloc.0
0x9aa  stfld    class Microsoft.Crm.ServiceBus.IInternalServiceEndpointService Microsoft.Crm.ServiceBus.ServiceBusService::internalService
0x9af  ldarg.0
0x9b0  ldarg.2
0x9b1  brfalse.s loc_9B6
0x9b3  ldarg.2
0x9b4  br.s     loc_9B9
0x9b6  ldarg.0
0x9b7  stloc.1
0x9b8  ldloc.1
0x9b9  stfld    class Microsoft.Crm.ServiceBus.IInternalAuthenticationTokenService Microsoft.Crm.ServiceBus.ServiceBusService::internalAuthService
0x9be  ldarg.0
0x9bf  ldarg.3
0x9c0  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory Microsoft.Crm.ServiceBus.ServiceBusService::internalOrgServiceFactory
0x9c5  ldarg.0
0x9c6  ldarg.s  4
0x9c8  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::internalContext
0x9cd  ret
```
