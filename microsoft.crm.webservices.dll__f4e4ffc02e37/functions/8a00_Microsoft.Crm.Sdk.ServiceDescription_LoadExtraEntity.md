# Microsoft.Crm.Sdk.ServiceDescription::LoadExtraEntity

- ea: `0x8a00`
- end: `0x8a34`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadExtraEntity`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x89c0`

## callees

- `0x8a00`
- `0x94d0`

## pseudocode

```c

```

## disassembly

```asm
0x8a00  ldarg.0
0x8a01  ldfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x8a06  ldarg.1
0x8a07  ldc.i4.1
0x8a08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.EntityMetadatas::GetEntity(string logicalName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType nameMappingType)
0x8a0d  stloc.0
0x8a0e  ldarg.0
0x8a0f  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_entities
0x8a14  ldloc.0
0x8a15  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8a1a  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8a1f  brtrue.s loc_8A33
0x8a21  ldarg.0
0x8a22  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_entities
0x8a27  ldloc.0
0x8a28  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8a2d  ldloc.0
0x8a2e  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8a33  ret
```
