# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendFaxCommand

- ea: `0x3170`
- end: `0x317d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendFaxCommand`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x40d0`

## pseudocode

```c

```

## disassembly

```asm
0x3170  ldarg.0
0x3171  castclass Microsoft.Crm.Common.Application.Platform.Fax
0x3176  callvirt instance bool Microsoft.Crm.Common.Application.Platform.Fax::Send()
0x317b  pop
0x317c  ret
```
