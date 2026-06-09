# Microsoft.Crm.Metadata.AttributeService::ValidateDuplicateLink

- ea: `0x220b0`
- end: `0x2214b`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateDuplicateLink`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x21d50`

## callees

- `0x18660`
- `0x220b0`

## string_xrefs

- `0x220e3`: `linkedattributeid`
- `0x2211b`: `Given linked attribute is alreadly linked to other attribute {0}`

## pseudocode

```c

```

## disassembly

```asm
0x220b0  ldstr    aAttribute// "Attribute"
0x220b5  ldarg.2
0x220b6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x220bb  stloc.0
0x220bc  ldloc.0
0x220bd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x220c2  ldc.i4.2
0x220c3  newarr   [mscorlib]System.String
0x220c8  dup
0x220c9  ldc.i4.0
0x220ca  ldstr    aAttributeid// "attributeid"
0x220cf  stelem.ref
0x220d0  dup
0x220d1  ldc.i4.1
0x220d2  ldstr    aName// "name"
0x220d7  stelem.ref
0x220d8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x220dd  ldloc.0
0x220de  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x220e3  ldstr    aLinkedattribut// "linkedattributeid"
0x220e8  ldarg.0
0x220e9  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x220ee  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x220f3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, object)
0x220f8  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x220fd  ldloc.0
0x220fe  ldarg.2
0x220ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22104  stloc.1
0x22105  ldarg.1
0x22106  brtrue.s loc_2210B
0x22108  ldc.i4.1
0x22109  br.s     loc_2210C
0x2210b  ldc.i4.0
0x2210c  stloc.2
0x2210d  ldloc.1
0x2210e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x22113  ldloc.2
0x22114  ble.s    loc_2214A
0x22116  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2211b  ldstr    aGivenLinkedAtt// "Given linked attribute is alreadly link"...
0x22120  ldc.i4.1
0x22121  newarr   [mscorlib]System.Object
0x22126  dup
0x22127  ldc.i4.0
0x22128  ldloc.1
0x22129  ldc.i4.0
0x2212a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x2212f  ldstr    aName// "name"
0x22134  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22139  stelem.ref
0x2213a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2213f  ldc.i4   0x8004F0FE
0x22144  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22149  throw
0x2214a  ret
```
