# Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::set_ExchangeTaskId

- ea: `0x4130`
- end: `0x4142`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::set_ExchangeTaskId`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4150`

## string_xrefs

- `0x4136`: `ExchangeTaskId`

## pseudocode

```c

```

## disassembly

```asm
0x4130  ldarg.0
0x4131  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x4136  ldstr    aExchangetaskid// "ExchangeTaskId"
0x413b  ldarg.1
0x413c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x4141  ret
```
