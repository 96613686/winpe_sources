# Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAttributeMetadata

- ea: `0x6220`
- end: `0x62a5`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAttributeMetadata`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x62b0`
- `0xd1c0`
- `0xe130`
- `0x14cb0`

## callees

- `0x6220`

## pseudocode

```c

```

## disassembly

```asm
0x6220  ldarg.0
0x6221  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::.ctor()
0x6226  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::_schemaColumnNameToAttributeMetadataDictionary
0x622b  ldarg.0
0x622c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_organizationId
0x6231  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x6236  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x623b  ldarg.0
0x623c  ldfld    string Microsoft.Crm.Asynchronous.ImportFileHelperData::_targetEntityName
0x6241  ldc.i4.1
0x6242  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x6247  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x624c  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x6251  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6256  stloc.0
0x6257  br.s     loc_6289
0x6259  ldloc.0
0x625a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x625f  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x6264  stloc.1
0x6265  ldloc.1
0x6266  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0x626b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6270  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6275  brfalse.s loc_6289
0x6277  ldarg.0
0x6278  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> Microsoft.Crm.Asynchronous.ImportFileHelperData::_schemaColumnNameToAttributeMetadataDictionary
0x627d  ldloc.1
0x627e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x6283  ldloc.1
0x6284  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::Add(var<u1>, !!T0)
0x6289  ldloc.0
0x628a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x628f  brtrue.s loc_6259
0x6291  leave.s  loc_62A4
0x6293  ldloc.0
0x6294  isinst   [mscorlib]System.IDisposable
0x6299  stloc.2
0x629a  ldloc.2
0x629b  brfalse.s loc_62A3
0x629d  ldloc.2
0x629e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62a3  endfinally
0x62a4  ret
```
