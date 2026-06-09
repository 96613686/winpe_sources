# Microsoft.Crm.Service.ObjectModel.ContractService::GetContract

- ea: `0x4220`
- end: `0x422a`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::GetContract`
- size: `10`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x31c0`
- `0x3710`
- `0x3830`
- `0x3960`
- `0x3a80`
- `0x3d30`
- `0x3da0`
- `0x4040`

## callees

- `0x4230`

## pseudocode

```c

```

## disassembly

```asm
0x4220  ldarg.0
0x4221  ldarg.1
0x4222  ldc.i4.0
0x4223  ldarg.2
0x4224  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract Microsoft.Crm.Service.ObjectModel.ContractService::GetContract(valuetype [mscorlib]System.Guid contractId, bool disableFLSCheck, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4229  ret
```
