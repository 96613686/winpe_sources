# Microsoft.Crm.Entities.CommunicationActivity::<AddPartyMappingWithAliasedAttributes>b__23_0

- ea: `0xa70`
- end: `0xa9d`
- name: `Microsoft.Crm.Entities.CommunicationActivity::<AddPartyMappingWithAliasedAttributes>b__23_0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xa40`
- `0xa70`

## pseudocode

```c

```

## disassembly

```asm
0xa70  ldarg.0
0xa71  ldarg.1
0xa72  ldloca.s 0
0xa74  call     instance bool Microsoft.Crm.Entities.CommunicationActivity::TryGetActivityAttributeMetadata(string activityAttributeName, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata& activityAttributeMetadata)
0xa79  brfalse.s loc_A9B
0xa7b  ldloc.0
0xa7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xa81  brfalse.s loc_A99
0xa83  ldloc.0
0xa84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xa89  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xa8e  ldc.i4.s 0xB
0xa90  bne.un.s loc_A99
0xa92  ldloc.0
0xa93  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0xa98  ret
0xa99  ldc.i4.0
0xa9a  ret
0xa9b  ldc.i4.0
0xa9c  ret
```
