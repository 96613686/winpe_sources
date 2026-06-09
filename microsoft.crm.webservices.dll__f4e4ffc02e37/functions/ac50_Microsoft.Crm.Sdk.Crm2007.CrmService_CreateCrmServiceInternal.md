# Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal

- ea: `0xac50`
- end: `0xac5b`
- name: `Microsoft.Crm.Sdk.Crm2007.CrmService::CreateCrmServiceInternal`
- size: `11`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaa70`
- `0xaab0`
- `0xaaf0`
- `0xab30`
- `0xab80`
- `0xabd0`
- `0xac10`

## callees

- `0x540`

## pseudocode

```c

```

## disassembly

```asm
0xac50  ldsfld   class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EndpointVersionProvider::CrmSdk2007Version
0xac55  newobj   instance void Microsoft.Crm.Sdk.CrmServiceInternal::.ctor(class [mscorlib]System.Version endpointVersion)
0xac5a  ret
```
