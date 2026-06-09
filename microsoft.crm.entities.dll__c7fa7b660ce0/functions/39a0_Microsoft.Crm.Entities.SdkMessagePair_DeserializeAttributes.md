# Microsoft.Crm.Entities.SdkMessagePair::DeserializeAttributes

- ea: `0x39a0`
- end: `0x39b7`
- name: `Microsoft.Crm.Entities.SdkMessagePair::DeserializeAttributes`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x39a0  ldarg.0
0x39a1  ldnull
0x39a2  stfld    class Microsoft.Crm.Entities.SdkMessageRequest Microsoft.Crm.Entities.SdkMessagePair::_messageRequest
0x39a7  ldarg.0
0x39a8  ldnull
0x39a9  stfld    class Microsoft.Crm.Entities.SdkMessageResponse Microsoft.Crm.Entities.SdkMessagePair::_messageResponse
0x39ae  ldarg.0
0x39af  ldarg.1
0x39b0  ldarg.2
0x39b1  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::DeserializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x39b6  ret
```
