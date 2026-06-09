# Microsoft.Crm.Metadata.EntityKeyService::ValidateAttributeForAlternateKey

- ea: `0x2dfd0`
- end: `0x2e1ec`
- name: `Microsoft.Crm.Metadata.EntityKeyService::ValidateAttributeForAlternateKey`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2e1f0`

## callees

- `0x2dfd0`

## string_xrefs

- `0x2e11a`: `validforcreateapi`
- `0x2e127`: `validforcreateapi`
- `0x2e13a`: `validforupdateapi`
- `0x2e147`: `validforupdateapi`
- `0x2e16e`: `Attributes defined for EntityKey must be valid for create and valid for update`

## pseudocode

```c

```

## disassembly

```asm
0x2dfd0  ldarg.1
0x2dfd1  ldstr    aAttributetypei// "attributetypeid"
0x2dfd6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2dfdb  brtrue.s loc_2DFEF
0x2dfdd  ldarg.1
0x2dfde  ldstr    aAttributetypei// "attributetypeid"
0x2dfe3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2dfe8  unbox.any [mscorlib]System.Guid
0x2dfed  br.s     loc_2DFF4
0x2dfef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2dff4  stloc.0
0x2dff5  ldloc.0
0x2dff6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2dffb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2e000  brfalse.s loc_2E050
0x2e002  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x2e007  ldloc.0
0x2e008  box      [mscorlib]System.Guid
0x2e00d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2e012  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x2e017  ldc.i4.3
0x2e018  beq.s    loc_2E04D
0x2e01a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x2e01f  ldloc.0
0x2e020  box      [mscorlib]System.Guid
0x2e025  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2e02a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x2e02f  ldc.i4.5
0x2e030  beq.s    loc_2E04D
0x2e032  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x2e037  ldloc.0
0x2e038  box      [mscorlib]System.Guid
0x2e03d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2e042  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x2e047  ldc.i4.s 0x10
0x2e049  ceq
0x2e04b  br.s     loc_2E051
0x2e04d  ldc.i4.1
0x2e04e  br.s     loc_2E051
0x2e050  ldc.i4.0
0x2e051  stloc.1
0x2e052  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e057  ldstr    aAttributeName0// "Attribute - Name : {0}, Id : {1} is inv"...
0x2e05c  ldc.i4.2
0x2e05d  newarr   [mscorlib]System.Object
0x2e062  dup
0x2e063  ldc.i4.0
0x2e064  ldarg.1
0x2e065  ldstr    aName// "name"
0x2e06a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e06f  stelem.ref
0x2e070  dup
0x2e071  ldc.i4.1
0x2e072  ldarg.1
0x2e073  ldstr    aAttributeid// "attributeid"
0x2e078  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e07d  stelem.ref
0x2e07e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e083  ldstr    a0// "{0}"
0x2e088  call     string [mscorlib]System.String::Concat(string, string)
0x2e08d  stloc.2
0x2e08e  ldloc.1
0x2e08f  brtrue.s loc_2E0B5
0x2e091  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e096  ldloc.2
0x2e097  ldc.i4.1
0x2e098  newarr   [mscorlib]System.Object
0x2e09d  dup
0x2e09e  ldc.i4.0
0x2e09f  ldstr    aAttributesDefi// "Attributes defined for EntityKey must b"...
0x2e0a4  stelem.ref
0x2e0a5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e0aa  ldc.i4   0x80040203
0x2e0af  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e0b4  throw
0x2e0b5  ldarg.1
0x2e0b6  ldstr    aInheritsfrom// "inheritsfrom"
0x2e0bb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2e0c0  brtrue.s loc_2E0DE
0x2e0c2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2e0c7  ldarg.1
0x2e0c8  ldstr    aInheritsfrom// "inheritsfrom"
0x2e0cd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e0d2  unbox.any [mscorlib]System.Guid
0x2e0d7  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2e0dc  br.s     loc_2E0DF
0x2e0de  ldc.i4.1
0x2e0df  stloc.3
0x2e0e0  ldarg.1
0x2e0e1  ldstr    aIslogical// "islogical"
0x2e0e6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e0eb  unbox.any [mscorlib]System.Boolean
0x2e0f0  brtrue.s loc_2E0F5
0x2e0f2  ldloc.3
0x2e0f3  brtrue.s loc_2E119
0x2e0f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e0fa  ldloc.2
0x2e0fb  ldc.i4.1
0x2e0fc  newarr   [mscorlib]System.Object
0x2e101  dup
0x2e102  ldc.i4.0
0x2e103  ldstr    aAttributesDefi_0// "Attributes defined for EntityKey must n"...
0x2e108  stelem.ref
0x2e109  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e10e  ldc.i4   0x80040203
0x2e113  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e118  throw
0x2e119  ldarg.1
0x2e11a  ldstr    aValidforcreate// "validforcreateapi"
0x2e11f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2e124  brtrue.s loc_2E138
0x2e126  ldarg.1
0x2e127  ldstr    aValidforcreate// "validforcreateapi"
0x2e12c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e131  unbox.any [mscorlib]System.Boolean
0x2e136  br.s     loc_2E139
0x2e138  ldc.i4.0
0x2e139  ldarg.1
0x2e13a  ldstr    aValidforupdate// "validforupdateapi"
0x2e13f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2e144  brtrue.s loc_2E158
0x2e146  ldarg.1
0x2e147  ldstr    aValidforupdate// "validforupdateapi"
0x2e14c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e151  unbox.any [mscorlib]System.Boolean
0x2e156  br.s     loc_2E159
0x2e158  ldc.i4.0
0x2e159  stloc.s  4
0x2e15b  ldloc.s  4
0x2e15d  and
0x2e15e  brtrue.s loc_2E184
0x2e160  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e165  ldloc.2
0x2e166  ldc.i4.1
0x2e167  newarr   [mscorlib]System.Object
0x2e16c  dup
0x2e16d  ldc.i4.0
0x2e16e  ldstr    aAttributesDefi_1// "Attributes defined for EntityKey must b"...
0x2e173  stelem.ref
0x2e174  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e179  ldc.i4   0x80040203
0x2e17e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e183  throw
0x2e184  ldarg.1
0x2e185  ldstr    aIssecured// "issecured"
0x2e18a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e18f  unbox.any [mscorlib]System.Boolean
0x2e194  brfalse.s loc_2E1BA
0x2e196  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e19b  ldloc.2
0x2e19c  ldc.i4.1
0x2e19d  newarr   [mscorlib]System.Object
0x2e1a2  dup
0x2e1a3  ldc.i4.0
0x2e1a4  ldstr    aAttributesDefi_2// "Attributes defined for EntityKey must n"...
0x2e1a9  stelem.ref
0x2e1aa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e1af  ldc.i4   0x80040203
0x2e1b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e1b9  throw
0x2e1ba  ldarg.1
0x2e1bb  ldstr    aAttributeof// "attributeof"
0x2e1c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2e1c5  brfalse.s loc_2E1EB
0x2e1c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e1cc  ldloc.2
0x2e1cd  ldc.i4.1
0x2e1ce  newarr   [mscorlib]System.Object
0x2e1d3  dup
0x2e1d4  ldc.i4.0
0x2e1d5  ldstr    aAttributeofOfT// "AttributeOf of the attribute must be em"...
0x2e1da  stelem.ref
0x2e1db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e1e0  ldc.i4   0x80040203
0x2e1e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2e1ea  throw
0x2e1eb  ret
```
