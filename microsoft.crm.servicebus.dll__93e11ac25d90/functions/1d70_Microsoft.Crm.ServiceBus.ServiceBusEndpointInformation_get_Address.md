# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Address

- ea: `0x1d70`
- end: `0x1daa`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Address`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a90`
- `0x1ab0`
- `0x1ad0`
- `0x1cb0`
- `0x1cd0`
- `0x1d70`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldarg.0
0x1d71  call     instance valuetype NamespaceFormatType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_NamespaceFormat()
0x1d76  ldc.i4.2
0x1d77  bne.un.s loc_1D92
0x1d79  ldarg.0
0x1d7a  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_NamespaceAddress()
0x1d7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d84  brtrue.s loc_1D92
0x1d86  ldarg.0
0x1d87  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_NamespaceAddress()
0x1d8c  newobj   instance void [System]System.Uri::.ctor(string)
0x1d91  ret
0x1d92  ldarg.0
0x1d93  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Scheme()
0x1d98  ldarg.0
0x1d99  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_SolutionName()
0x1d9e  ldarg.0
0x1d9f  call     instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Path()
0x1da4  call     class [System]System.Uri [Microsoft.ServiceBus]Microsoft.ServiceBus.ServiceBusEnvironment::CreateServiceUri(string, string, string)
0x1da9  ret
```
