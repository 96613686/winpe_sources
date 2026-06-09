# Microsoft.Crm.ServiceBus.TokenPusher::get_Token

- ea: `0x5cd0`
- end: `0x5d03`
- name: `Microsoft.Crm.ServiceBus.TokenPusher::get_Token`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x50e0`
- `0x5d50`

## callees

- `0x55a0`
- `0x5cd0`
- `0x5d10`

## pseudocode

```c

```

## disassembly

```asm
0x5cd0  ldarg.0
0x5cd1  ldfld    string Microsoft.Crm.ServiceBus.TokenPusher::_token
0x5cd6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5cdb  brfalse.s loc_5CFC
0x5cdd  ldarg.0
0x5cde  ldfld    class Microsoft.Crm.ServiceBus.TokenProvider Microsoft.Crm.ServiceBus.TokenPusher::_provider
0x5ce3  brfalse.s loc_5CFC
0x5ce5  ldarg.0
0x5ce6  ldarg.0
0x5ce7  ldfld    class Microsoft.Crm.ServiceBus.TokenProvider Microsoft.Crm.ServiceBus.TokenPusher::_provider
0x5cec  ldarg.0
0x5ced  call     instance bool Microsoft.Crm.ServiceBus.TokenPusher::get_ForServiceBusScope()
0x5cf2  callvirt instance string Microsoft.Crm.ServiceBus.TokenProvider::RetrieveEndpointToken(bool fromServiceBusScope)
0x5cf7  stfld    string Microsoft.Crm.ServiceBus.TokenPusher::_token
0x5cfc  ldarg.0
0x5cfd  ldfld    string Microsoft.Crm.ServiceBus.TokenPusher::_token
0x5d02  ret
```
