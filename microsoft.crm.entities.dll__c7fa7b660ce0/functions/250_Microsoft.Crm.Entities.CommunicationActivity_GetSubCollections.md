# Microsoft.Crm.Entities.CommunicationActivity::GetSubCollections

- ea: `0x250`
- end: `0x2e2`
- name: `Microsoft.Crm.Entities.CommunicationActivity::GetSubCollections`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x250`
- `0xc50`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0x250  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::.ctor()
0x255  stloc.0
0x256  ldarg.0
0x257  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x25c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x261  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x266  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x26b  stloc.1
0x26c  br.s     loc_2C2
0x26e  ldloc.1
0x26f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x274  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x279  stloc.2
0x27a  ldloc.2
0x27b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x280  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x285  ldc.i4.s 0xB
0x287  bne.un.s loc_2C2
0x289  ldstr    aAllparties// "allparties"
0x28e  ldloc.2
0x28f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x294  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x299  brfalse.s loc_2C2
0x29b  ldarg.0
0x29c  ldfld    class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::partyMappingCollection
0x2a1  ldloc.2
0x2a2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2a7  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(string logicalName)
0x2ac  stloc.3
0x2ad  ldloc.3
0x2ae  brfalse.s loc_2C2
0x2b0  ldloc.0
0x2b1  ldloc.2
0x2b2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2b7  ldloc.3
0x2b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x2bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::set_Item(var<u1>, !!T0)
0x2c2  ldloc.1
0x2c3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c8  brtrue.s loc_26E
0x2ca  leave.s  loc_2E0
0x2cc  ldloc.1
0x2cd  isinst   [mscorlib]System.IDisposable
0x2d2  stloc.s  4
0x2d4  ldloc.s  4
0x2d6  brfalse.s loc_2DF
0x2d8  ldloc.s  4
0x2da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2df  endfinally
0x2e0  ldloc.0
0x2e1  ret
```
