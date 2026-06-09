# Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails

- ea: `0x42d0`
- end: `0x42dd`
- name: `Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a80`
- `0x3da0`
- `0x4040`

## callees

- `0x42f0`

## pseudocode

```c

```

## disassembly

```asm
0x42d0  ldarg.0
0x42d1  ldarg.1
0x42d2  ldnull
0x42d3  ldc.i4.0
0x42d4  ldc.i4.0
0x42d5  ldc.i4.1
0x42d6  ldarg.2
0x42d7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.ContractService::GetContractDetails(valuetype [mscorlib]System.Guid contractId, string[] columns, bool allColumns, bool disableFLSCheck, bool includeCanceled, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x42dc  ret
```
