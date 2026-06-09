# Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::get_EntityRelationshipRelationshipsId

- ea: `0x36580`
- end: `0x365ae`
- name: `Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::get_EntityRelationshipRelationshipsId`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x36580`
- `0x6fd40`
- `0x6fe70`

## string_xrefs

- `0x36586`: `entityrelationshiprelationshipsid`
- `0x3659e`: `entityrelationshiprelationshipsid`

## pseudocode

```c

```

## disassembly

```asm
0x36580  ldarg.0
0x36581  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::_entityRelationshipRelationshipsData
0x36586  ldstr    aEntityrelation_13// "entityrelationshiprelationshipsid"
0x3658b  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string propertyName)
0x36590  brfalse.s loc_36598
0x36592  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36597  ret
0x36598  ldarg.0
0x36599  ldfld    class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescriptionPropertyBag::_entityRelationshipRelationshipsData
0x3659e  ldstr    aEntityrelation_13// "entityrelationshiprelationshipsid"
0x365a3  callvirt instance object Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string propertyName)
0x365a8  unbox.any [mscorlib]System.Guid
0x365ad  ret
```
