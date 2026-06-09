# Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::.ctor

- ea: `0x4150`
- end: `0x4169`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4130`

## string_xrefs

- `0x4157`: `CompleteExchangeTask`

## pseudocode

```c

```

## disassembly

```asm
0x4150  ldarg.0
0x4151  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x4156  ldarg.0
0x4157  ldstr    aCompleteexchan// "CompleteExchangeTask"
0x415c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x4161  ldarg.0
0x4162  ldnull
0x4163  call     instance void Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::set_ExchangeTaskId(string value)
0x4168  ret
```
