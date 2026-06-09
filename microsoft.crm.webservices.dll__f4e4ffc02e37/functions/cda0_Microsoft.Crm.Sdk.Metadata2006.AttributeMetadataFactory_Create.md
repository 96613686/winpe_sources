# Microsoft.Crm.Sdk.Metadata2006.AttributeMetadataFactory::Create

- ea: `0xcda0`
- end: `0xce66`
- name: `Microsoft.Crm.Sdk.Metadata2006.AttributeMetadataFactory::Create`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xd260`

## callees

- `0xc3f0`
- `0xc690`
- `0xc730`
- `0xc7f0`
- `0xc8b0`
- `0xc980`
- `0xca80`
- `0xcb60`
- `0xcc60`
- `0xcda0`

## pseudocode

```c

```

## disassembly

```asm
0xcda0  ldarg.0
0xcda1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xcda6  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xcdab  stloc.1
0xcdac  ldloc.1
0xcdad  switch   loc_CE02, loc_CE5C, loc_CE5C, loc_CE20, loc_CE2A, loc_CE34, loc_CE5C, loc_CE5C, loc_CE48, loc_CE3E, loc_CE5C, loc_CE5C, loc_CDF8, loc_CE5C, loc_CE0C, loc_CE16, loc_CE52
0xcdf6  br.s     loc_CE5C
0xcdf8  ldarg.0
0xcdf9  ldarg.1
0xcdfa  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.PicklistAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xcdff  stloc.0
0xce00  br.s     loc_CE64
0xce02  ldarg.0
0xce03  ldarg.1
0xce04  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.PicklistAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce09  stloc.0
0xce0a  br.s     loc_CE64
0xce0c  ldarg.0
0xce0d  ldarg.1
0xce0e  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.StateAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce13  stloc.0
0xce14  br.s     loc_CE64
0xce16  ldarg.0
0xce17  ldarg.1
0xce18  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.StatusAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce1d  stloc.0
0xce1e  br.s     loc_CE64
0xce20  ldarg.0
0xce21  ldarg.1
0xce22  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.DecimalAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce27  stloc.0
0xce28  br.s     loc_CE64
0xce2a  ldarg.0
0xce2b  ldarg.1
0xce2c  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.FloatAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce31  stloc.0
0xce32  br.s     loc_CE64
0xce34  ldarg.0
0xce35  ldarg.1
0xce36  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.IntegerAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce3b  stloc.0
0xce3c  br.s     loc_CE64
0xce3e  ldarg.0
0xce3f  ldarg.1
0xce40  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.MoneyAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce45  stloc.0
0xce46  br.s     loc_CE64
0xce48  ldarg.0
0xce49  ldarg.1
0xce4a  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.StringAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce4f  stloc.0
0xce50  br.s     loc_CE64
0xce52  ldarg.0
0xce53  ldarg.1
0xce54  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.StringAttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce59  stloc.0
0xce5a  br.s     loc_CE64
0xce5c  ldarg.0
0xce5d  ldarg.1
0xce5e  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.AttributeMetadata::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, valuetype [mscorlib]System.Guid organizationId)
0xce63  stloc.0
0xce64  ldloc.0
0xce65  ret
```
