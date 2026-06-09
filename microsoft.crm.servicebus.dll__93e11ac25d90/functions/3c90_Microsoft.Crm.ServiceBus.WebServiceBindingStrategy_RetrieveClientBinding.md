# Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::RetrieveClientBinding

- ea: `0x3c90`
- end: `0x3cc6`
- name: `Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::RetrieveClientBinding`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2b30`
- `0x33f0`

## pseudocode

```c

```

## disassembly

```asm
0x3c90  call     class [Microsoft.ServiceBus]Microsoft.ServiceBus.ConnectivitySettings [Microsoft.ServiceBus]Microsoft.ServiceBus.ServiceBusEnvironment::get_SystemConnectivity()
0x3c95  ldc.i4.0
0x3c96  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.ConnectivitySettings::set_Mode(valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.ConnectivityMode)
0x3c9b  newobj   instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WS2007HttpRelayBinding::.ctor()
0x3ca0  stloc.0
0x3ca1  ldloc.0
0x3ca2  callvirt instance class [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelaySecurity [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBinding::get_Security()
0x3ca7  ldarg.0
0x3ca8  ldfld    valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.EndToEndSecurityMode Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::securityMode
0x3cad  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelaySecurity::set_Mode(valuetype [Microsoft.ServiceBus]Microsoft.ServiceBus.EndToEndSecurityMode)
0x3cb2  ldc.i4.3
0x3cb3  ldarg.0
0x3cb4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::orgId
0x3cb9  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::.ctor(valuetype Microsoft.Crm.ServiceBus.ServiceBusPropertyPrefix propertyPrefix, valuetype [mscorlib]System.Guid orgId)
0x3cbe  ldloc.0
0x3cbf  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply(class [Microsoft.ServiceBus]Microsoft.ServiceBus.WS2007HttpRelayBinding binding)
0x3cc4  ldloc.0
0x3cc5  ret
```
