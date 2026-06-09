# Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext

- ea: `0x24f30`
- end: `0x24f3b`
- name: `Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext`
- size: `11`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7040`
- `0xe670`
- `0xe780`
- `0xe890`
- `0x17ca0`
- `0x20020`
- `0x24aa0`
- `0x24ee0`
- `0x30870`
- `0x30db0`

## callees

- `0x24ec0`

## pseudocode

```c

```

## disassembly

```asm
0x24f30  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationId()
0x24f35  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x24f3a  ret
```
