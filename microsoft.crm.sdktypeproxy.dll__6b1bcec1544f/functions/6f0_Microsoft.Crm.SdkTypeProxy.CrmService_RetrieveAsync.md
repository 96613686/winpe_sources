# Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveAsync

- ea: `0x6f0`
- end: `0x6fb`
- name: `Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveAsync`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x700`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.0
0x6f1  ldarg.1
0x6f2  ldarg.2
0x6f3  ldarg.3
0x6f4  ldnull
0x6f5  call     instance void Microsoft.Crm.SdkTypeProxy.CrmService::RetrieveAsync(string entityName, valuetype [mscorlib]System.Guid id, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase columnSet, object userState)
0x6fa  ret
```
