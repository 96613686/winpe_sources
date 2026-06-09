# Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::CreateDescriptionWithDefaults

- ea: `0x3f720`
- end: `0x3f819`
- name: `Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::CreateDescriptionWithDefaults`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x3ee70`
- `0x3f690`
- `0x3f720`
- `0x6fd60`
- `0x6fe90`

## string_xrefs

- `0x3f772`: `cascadedelete`
- `0x3f7f6`: `cascadelinkmask`

## pseudocode

```c

```

## disassembly

```asm
0x3f720  ldarg.1
0x3f721  newobj   instance void Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3f726  dup
0x3f727  callvirt instance class Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag::get_InnerEntityData()
0x3f72c  stloc.0
0x3f72d  ldloc.0
0x3f72e  ldstr    aRelationshipid// "relationshipid"
0x3f733  ldarg.0
0x3f734  box      [mscorlib]System.Guid
0x3f739  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f73e  ldloc.0
0x3f73f  ldstr    aRelationshipty_0// "relationshiptype"
0x3f744  ldc.i4.0
0x3f745  box      [mscorlib]System.Int32
0x3f74a  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f74f  ldloc.0
0x3f750  ldstr    aIslogical_0// "islogical"
0x3f755  ldc.i4.0
0x3f756  box      [mscorlib]System.Boolean
0x3f75b  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f760  ldloc.0
0x3f761  ldstr    aIsvalidforadva_0// "isvalidforadvancedfind"
0x3f766  ldc.i4.0
0x3f767  box      [mscorlib]System.Boolean
0x3f76c  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f771  ldloc.0
0x3f772  ldstr    aCascadedelete_0// "cascadedelete"
0x3f777  ldc.i4.2
0x3f778  box      [mscorlib]System.Byte
0x3f77d  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f782  ldloc.0
0x3f783  ldstr    aCascadeassign_0// "cascadeassign"
0x3f788  ldc.i4.0
0x3f789  box      [mscorlib]System.Byte
0x3f78e  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f793  ldloc.0
0x3f794  ldstr    aCascadeshare_0// "cascadeshare"
0x3f799  ldc.i4.0
0x3f79a  box      [mscorlib]System.Byte
0x3f79f  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f7a4  ldloc.0
0x3f7a5  ldstr    aCascadeunshare_0// "cascadeunshare"
0x3f7aa  ldc.i4.0
0x3f7ab  box      [mscorlib]System.Byte
0x3f7b0  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f7b5  ldloc.0
0x3f7b6  ldstr    aCascademerge_0// "cascademerge"
0x3f7bb  ldc.i4.0
0x3f7bc  box      [mscorlib]System.Byte
0x3f7c1  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f7c6  ldloc.0
0x3f7c7  ldstr    aCascadereparen_0// "cascadereparent"
0x3f7cc  ldc.i4.0
0x3f7cd  box      [mscorlib]System.Byte
0x3f7d2  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f7d7  ldloc.0
0x3f7d8  ldstr    aCascaderollupv_0// "cascaderollupview"
0x3f7dd  callvirt instance bool Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string propertyName)
0x3f7e2  brfalse.s loc_3F7F5
0x3f7e4  ldloc.0
0x3f7e5  ldstr    aCascaderollupv_0// "cascaderollupview"
0x3f7ea  ldc.i4.0
0x3f7eb  box      [mscorlib]System.Byte
0x3f7f0  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f7f5  ldloc.0
0x3f7f6  ldstr    aCascadelinkmas_0// "cascadelinkmask"
0x3f7fb  ldc.i4.0
0x3f7fc  conv.i8
0x3f7fd  box      [mscorlib]System.Int64
0x3f802  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f807  ldloc.0
0x3f808  ldstr    aIscustomrelati_0// "iscustomrelationship"
0x3f80d  ldc.i4.0
0x3f80e  box      [mscorlib]System.Boolean
0x3f813  callvirt instance void Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string propertyName, object value)
0x3f818  ret
```
