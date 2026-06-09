# Microsoft.Crm.ServiceBus.WebhookClient::IsSuccessHttpStatusCode

- ea: `0x65c0`
- end: `0x65d6`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::IsSuccessHttpStatusCode`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x68c0`

## callees

- `0x65c0`

## pseudocode

```c

```

## disassembly

```asm
0x65c0  ldarg.1
0x65c1  ldc.i4   0xC8
0x65c6  blt.s    loc_65D4
0x65c8  ldarg.1
0x65c9  ldc.i4   0x12B
0x65ce  cgt
0x65d0  ldc.i4.0
0x65d1  ceq
0x65d3  ret
0x65d4  ldc.i4.0
0x65d5  ret
```
