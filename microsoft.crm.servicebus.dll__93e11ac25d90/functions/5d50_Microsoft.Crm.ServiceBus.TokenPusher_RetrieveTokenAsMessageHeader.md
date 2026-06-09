# Microsoft.Crm.ServiceBus.TokenPusher::RetrieveTokenAsMessageHeader

- ea: `0x5d50`
- end: `0x5d66`
- name: `Microsoft.Crm.ServiceBus.TokenPusher::RetrieveTokenAsMessageHeader`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d80`

## callees

- `0x5cd0`

## string_xrefs

- `0x5d50`: `SecurityToken`

## pseudocode

```c

```

## disassembly

```asm
0x5d50  ldstr    aSecuritytoken// "SecurityToken"
0x5d55  ldsfld   string [mscorlib]System.String::Empty
0x5d5a  ldarg.0
0x5d5b  call     instance string Microsoft.Crm.ServiceBus.TokenPusher::get_Token()
0x5d60  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x5d65  ret
```
