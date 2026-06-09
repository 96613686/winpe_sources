# Microsoft.Crm.Sdk.ServiceDescription::GetEntityByObjectTypeCode

- ea: `0x86c0`
- end: `0x86cd`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetEntityByObjectTypeCode`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1880`
- `0x1c80`
- `0x8ba0`

## callees

- `0x9480`

## pseudocode

```c

```

## disassembly

```asm
0x86c0  ldarg.0
0x86c1  ldfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x86c6  ldarg.1
0x86c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.EntityMetadatas::GetEntity(int32 objectTypeCode)
0x86cc  ret
```
