# Microsoft.Crm.Entities.CommunicationActivity::TryGetActivityAttributeMetadata

- ea: `0xa40`
- end: `0xa6b`
- name: `Microsoft.Crm.Entities.CommunicationActivity::TryGetActivityAttributeMetadata`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa70`

## callees

- `0xa40`

## pseudocode

```c

```

## disassembly

```asm
0xa40  ldarg.0
0xa41  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xa46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa4b  ldarg.1
0xa4c  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0xa51  ldarg.2
0xa52  ldnull
0xa53  stind.ref
0xa54  dup
0xa55  brfalse.s loc_A6A
0xa57  ldarg.2
0xa58  ldarg.0
0xa59  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xa5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa63  ldarg.1
0xa64  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xa69  stind.ref
0xa6a  ret
```
