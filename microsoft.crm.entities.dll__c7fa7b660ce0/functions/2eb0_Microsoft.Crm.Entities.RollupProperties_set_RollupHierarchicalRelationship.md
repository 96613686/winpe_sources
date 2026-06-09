# Microsoft.Crm.Entities.RollupProperties::set_RollupHierarchicalRelationship

- ea: `0x2eb0`
- end: `0x2f04`
- name: `Microsoft.Crm.Entities.RollupProperties::set_RollupHierarchicalRelationship`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2eb0`

## pseudocode

```c

```

## disassembly

```asm
0x2eb0  ldarg.0
0x2eb1  ldarg.1
0x2eb2  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Entities.RollupProperties::_rollupHierarchicalRelationship
0x2eb7  ldarg.1
0x2eb8  brfalse.s loc_2EE2
0x2eba  ldarg.0
0x2ebb  ldstr    aAllowhierarchy// "allowhierarchyonsource"
0x2ec0  ldc.i4.1
0x2ec1  box      [mscorlib]System.Boolean
0x2ec6  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2ecb  ldarg.0
0x2ecc  ldstr    aSourcehierarch// "sourcehierarchicalrelationshipname"
0x2ed1  ldarg.0
0x2ed2  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Entities.RollupProperties::_rollupHierarchicalRelationship
0x2ed7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_Name()
0x2edc  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2ee1  ret
0x2ee2  ldarg.0
0x2ee3  ldstr    aAllowhierarchy// "allowhierarchyonsource"
0x2ee8  ldc.i4.0
0x2ee9  box      [mscorlib]System.Boolean
0x2eee  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2ef3  ldarg.0
0x2ef4  ldstr    aSourcehierarch// "sourcehierarchicalrelationshipname"
0x2ef9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2efe  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f03  ret
```
