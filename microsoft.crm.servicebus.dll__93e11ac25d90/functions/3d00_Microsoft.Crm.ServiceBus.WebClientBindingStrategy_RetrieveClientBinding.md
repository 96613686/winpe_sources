# Microsoft.Crm.ServiceBus.WebClientBindingStrategy::RetrieveClientBinding

- ea: `0x3d00`
- end: `0x3d36`
- name: `Microsoft.Crm.ServiceBus.WebClientBindingStrategy::RetrieveClientBinding`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2b30`
- `0x3520`

## pseudocode

```c

```

## disassembly

```asm
0x3d00  call     class [Microsoft.ServiceBus]Microsoft.ServiceBus.ConnectivitySettings [Microsoft.ServiceBus]Microsoft.ServiceBus.ServiceBusEnvironment::get_SystemConnectivity()
0x3d05  ldc.i4.0
0x3d06  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.ConnectivitySettings::set_Mode(valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.ConnectivityMode)
0x3d0b  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::.ctor()
0x3d10  stloc.0
0x3d11  ldloc.0
0x3d12  callvirt instance class [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelaySecurity [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::get_Security()
0x3d17  ldarg.0
0x3d18  ldfld    valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.EndToEndWebHttpSecurityMode Microsoft.Crm.ServiceBus.WebClientBindingStrategy::securityMode
0x3d1d  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelaySecurity::set_Mode(valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.EndToEndWebHttpSecurityMode)
0x3d22  ldc.i4.4
0x3d23  ldarg.0
0x3d24  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.WebClientBindingStrategy::orgId
0x3d29  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor(valuetype Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix propertyPrefix, valuetype [mscorlib]System.Guid orgId)
0x3d2e  ldloc.0
0x3d2f  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply(class [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding binding)
0x3d34  ldloc.0
0x3d35  ret
```
