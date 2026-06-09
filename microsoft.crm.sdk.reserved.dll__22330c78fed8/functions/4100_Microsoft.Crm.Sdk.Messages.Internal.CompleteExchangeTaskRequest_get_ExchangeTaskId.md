# Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::get_ExchangeTaskId

- ea: `0x4100`
- end: `0x412a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CompleteExchangeTaskRequest::get_ExchangeTaskId`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4100`

## string_xrefs

- `0x4106`: `ExchangeTaskId`
- `0x4118`: `ExchangeTaskId`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldarg.0
0x4101  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x4106  ldstr    aExchangetaskid// "ExchangeTaskId"
0x410b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x4110  brfalse.s loc_4128
0x4112  ldarg.0
0x4113  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x4118  ldstr    aExchangetaskid// "ExchangeTaskId"
0x411d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x4122  castclass [mscorlib]System.String
0x4127  ret
0x4128  ldnull
0x4129  ret
```
