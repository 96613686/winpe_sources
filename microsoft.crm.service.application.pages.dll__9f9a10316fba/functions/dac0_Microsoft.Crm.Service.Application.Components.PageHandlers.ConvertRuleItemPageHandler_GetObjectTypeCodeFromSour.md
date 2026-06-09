# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetObjectTypeCodeFromSourceTypeCode

- ea: `0xdac0`
- end: `0xdae3`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetObjectTypeCodeFromSourceTypeCode`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`

## callees

- `0xdac0`

## pseudocode

```c

```

## disassembly

```asm
0xdac0  ldarg.1
0xdac1  ldc.i4.1
0xdac2  beq.s    loc_DACA
0xdac4  ldarg.1
0xdac5  ldc.i4.2
0xdac6  beq.s    loc_DAD0
0xdac8  br.s     loc_DAD6
0xdaca  ldc.i4   0x1078
0xdacf  ret
0xdad0  ldc.i4   0x106A
0xdad5  ret
0xdad6  ldc.i4.0
0xdad7  ldstr    aInvalidSourceT// "Invalid source type code for the the cu"...
0xdadc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xdae1  ldc.i4.0
0xdae2  ret
```
