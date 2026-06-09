# Microsoft.Crm.Metadata.AttributeService::ValidateLinkedAttributeForCreateUpdate

- ea: `0x21d50`
- end: `0x220ab`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateLinkedAttributeForCreateUpdate`
- size: `859`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ff00`
- `0x21360`

## callees

- `0x18490`
- `0x18530`
- `0x18660`
- `0x18760`
- `0x21d50`
- `0x220b0`
- `0x22150`

## string_xrefs

- `0x21e43`: `Not a valid entity for linked attribute {0}`
- `0x22032`: `Data type mismatch found with linked attribute for attribute {0}`

## pseudocode

```c

```

## disassembly

```asm
0x21d50  ldarg.1
0x21d51  ldarg.2
0x21d52  ldarg.3
0x21d53  call     void Microsoft.Crm.Metadata.AttributeService::ValidateDuplicateLink(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, bool isLinkedAttributeChanged, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x21d58  ldarg.2
0x21d59  brfalse  loc_220AA
0x21d5e  ldc.i4.s 0xE
0x21d60  newarr   [mscorlib]System.String
0x21d65  dup
0x21d66  ldc.i4.0
0x21d67  ldstr    aEntityid// "entityid"
0x21d6c  stelem.ref
0x21d6d  dup
0x21d6e  ldc.i4.1
0x21d6f  ldstr    aAttributetypei// "attributetypeid"
0x21d74  stelem.ref
0x21d75  dup
0x21d76  ldc.i4.2
0x21d77  ldstr    aAttributelogic// "attributelogicaltypeid"
0x21d7c  stelem.ref
0x21d7d  dup
0x21d7e  ldc.i4.3
0x21d7f  ldstr    aLength// "length"
0x21d84  stelem.ref
0x21d85  dup
0x21d86  ldc.i4.4
0x21d87  ldstr    aImemode// "imemode"
0x21d8c  stelem.ref
0x21d8d  dup
0x21d8e  ldc.i4.5
0x21d8f  ldstr    aMaxlength// "maxlength"
0x21d94  stelem.ref
0x21d95  dup
0x21d96  ldc.i4.6
0x21d97  ldstr    aMinvalue// "minvalue"
0x21d9c  stelem.ref
0x21d9d  dup
0x21d9e  ldc.i4.7
0x21d9f  ldstr    aMaxvalue// "maxvalue"
0x21da4  stelem.ref
0x21da5  dup
0x21da6  ldc.i4.8
0x21da7  ldstr    aAccuracy// "accuracy"
0x21dac  stelem.ref
0x21dad  dup
0x21dae  ldc.i4.s 9
0x21db0  ldstr    aAccuracysource// "accuracysource"
0x21db5  stelem.ref
0x21db6  dup
0x21db7  ldc.i4.s 0xA
0x21db9  ldstr    aReferencedenti_0// "referencedentityobjecttypecode"
0x21dbe  stelem.ref
0x21dbf  dup
0x21dc0  ldc.i4.s 0xB
0x21dc2  ldstr    aLookupstyle// "lookupstyle"
0x21dc7  stelem.ref
0x21dc8  dup
0x21dc9  ldc.i4.s 0xC
0x21dcb  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x21dd0  stelem.ref
0x21dd1  dup
0x21dd2  ldc.i4.s 0xD
0x21dd4  ldstr    aOptionsetid// "optionsetid"
0x21dd9  stelem.ref
0x21dda  stloc.0
0x21ddb  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x21de0  ldarg.1
0x21de1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.AttributeInfo::get_LinkedAttributeId()
0x21de6  stloc.3
0x21de7  ldloca.s 3
0x21de9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x21dee  ldstr    aAttribute// "Attribute"
0x21df3  ldloc.0
0x21df4  ldarg.3
0x21df5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x21dfa  stloc.1
0x21dfb  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x21e00  ldarg.0
0x21e01  ldstr    aEntity_0// "Entity"
0x21e06  ldarg.3
0x21e07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x21e0c  stloc.2
0x21e0d  ldloc.1
0x21e0e  ldstr    aEntityid// "entityid"
0x21e13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x21e18  unbox.any [mscorlib]System.Guid
0x21e1d  ldloc.2
0x21e1e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x21e23  ldstr    aRecurrencebase// "recurrencebaseentityid"
0x21e28  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::get_Item(string)
0x21e2d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Value()
0x21e32  unbox.any [mscorlib]System.Guid
0x21e37  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21e3c  brfalse.s loc_21E71
0x21e3e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21e43  ldstr    aNotAValidEntit// "Not a valid entity for linked attribute"...
0x21e48  ldc.i4.1
0x21e49  newarr   [mscorlib]System.Object
0x21e4e  dup
0x21e4f  ldc.i4.0
0x21e50  ldloc.2
0x21e51  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x21e56  ldstr    aPhysicalname// "physicalname"
0x21e5b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::get_Item(string)
0x21e60  stelem.ref
0x21e61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21e66  ldc.i4   0x8004F0FD
0x21e6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x21e70  throw
0x21e71  ldloc.1
0x21e72  brfalse  loc_220AA
0x21e77  ldloc.0
0x21e78  stloc.s  4
0x21e7a  ldc.i4.0
0x21e7b  stloc.s  5
0x21e7d  br       loc_2205C
0x21e82  ldloc.s  4
0x21e84  ldloc.s  5
0x21e86  ldelem.ref
0x21e87  stloc.s  6
0x21e89  ldc.i4.0
0x21e8a  stloc.s  7
0x21e8c  ldarg.1
0x21e8d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21e92  ldloc.s  6
0x21e94  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x21e99  brfalse  loc_22029
0x21e9e  ldstr    aAttributetypei// "attributetypeid"
0x21ea3  ldloc.s  6
0x21ea5  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21eaa  brtrue.s loc_21EE1
0x21eac  ldarg.1
0x21ead  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21eb2  ldloc.s  6
0x21eb4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x21eb9  unbox.any [mscorlib]System.Guid
0x21ebe  ldloc.1
0x21ebf  ldloc.s  6
0x21ec1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x21ec6  unbox.any [mscorlib]System.Guid
0x21ecb  stloc.s  8
0x21ecd  ldloc.s  8
0x21ecf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21ed4  brfalse  loc_22029
0x21ed9  ldc.i4.1
0x21eda  stloc.s  7
0x21edc  br       loc_22029
0x21ee1  ldstr    aAttributelogic// "attributelogicaltypeid"
0x21ee6  ldloc.s  6
0x21ee8  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21eed  brfalse.s loc_21F0B
0x21eef  ldstr    aImemode// "imemode"
0x21ef4  ldloc.s  6
0x21ef6  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21efb  brfalse.s loc_21F0B
0x21efd  ldstr    aLookupstyle// "lookupstyle"
0x21f02  ldloc.s  6
0x21f04  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f09  brtrue.s loc_21F40
0x21f0b  ldarg.1
0x21f0c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21f11  ldloc.s  6
0x21f13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x21f18  castclass [mscorlib]System.String
0x21f1d  ldloc.1
0x21f1e  ldloc.s  6
0x21f20  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x21f25  castclass [mscorlib]System.String
0x21f2a  stloc.s  9
0x21f2c  ldloc.s  9
0x21f2e  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f33  brfalse  loc_22029
0x21f38  ldc.i4.1
0x21f39  stloc.s  7
0x21f3b  br       loc_22029
0x21f40  ldstr    aLength// "length"
0x21f45  ldloc.s  6
0x21f47  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f4c  brfalse.s loc_21F94
0x21f4e  ldstr    aMaxlength// "maxlength"
0x21f53  ldloc.s  6
0x21f55  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f5a  brfalse.s loc_21F94
0x21f5c  ldstr    aAccuracy// "accuracy"
0x21f61  ldloc.s  6
0x21f63  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f68  brfalse.s loc_21F94
0x21f6a  ldstr    aAccuracysource// "accuracysource"
0x21f6f  ldloc.s  6
0x21f71  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f76  brfalse.s loc_21F94
0x21f78  ldstr    aReferencedenti_0// "referencedentityobjecttypecode"
0x21f7d  ldloc.s  6
0x21f7f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f84  brfalse.s loc_21F94
0x21f86  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x21f8b  ldloc.s  6
0x21f8d  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21f92  brtrue.s loc_21FC8
0x21f94  ldarg.1
0x21f95  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21f9a  ldloc.s  6
0x21f9c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x21fa1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21fa6  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x21fab  ldloc.1
0x21fac  ldloc.s  6
0x21fae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x21fb3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21fb8  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x21fbd  stloc.s  0xA
0x21fbf  ldloc.s  0xA
0x21fc1  beq.s    loc_22029
0x21fc3  ldc.i4.1
0x21fc4  stloc.s  7
0x21fc6  br.s     loc_22029
0x21fc8  ldstr    aMinvalue// "minvalue"
0x21fcd  ldloc.s  6
0x21fcf  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21fd4  brfalse.s loc_21FE4
0x21fd6  ldstr    aMaxvalue// "maxvalue"
0x21fdb  ldloc.s  6
0x21fdd  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x21fe2  brtrue.s loc_22018
0x21fe4  ldarg.1
0x21fe5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21fea  ldloc.s  6
0x21fec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x21ff1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21ff6  call     float64 [mscorlib]System.Convert::ToDouble(object, class [mscorlib]System.IFormatProvider)
0x21ffb  ldloc.1
0x21ffc  ldloc.s  6
0x21ffe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22003  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22008  call     float64 [mscorlib]System.Convert::ToDouble(object, class [mscorlib]System.IFormatProvider)
0x2200d  stloc.s  0xB
0x2200f  ldloc.s  0xB
0x22011  beq.s    loc_22029
0x22013  ldc.i4.1
0x22014  stloc.s  7
0x22016  br.s     loc_22029
0x22018  ldstr    aEntityid// "entityid"
0x2201d  ldloc.s  6
0x2201f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x22024  brfalse.s loc_22029
0x22026  ldc.i4.1
0x22027  stloc.s  7
0x22029  ldloc.s  7
0x2202b  brfalse.s loc_22056
0x2202d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22032  ldstr    aDataTypeMismat// "Data type mismatch found with linked at"...
0x22037  ldc.i4.1
0x22038  newarr   [mscorlib]System.Object
0x2203d  dup
0x2203e  ldc.i4.0
0x2203f  ldarg.1
0x22040  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x22045  stelem.ref
0x22046  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2204b  ldc.i4   0x8004F0FC
0x22050  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22055  throw
0x22056  ldloc.s  5
0x22058  ldc.i4.1
0x22059  add
0x2205a  stloc.s  5
0x2205c  ldloc.s  5
0x2205e  ldloc.s  4
0x22060  ldlen
0x22061  conv.i4
0x22062  blt      loc_21E82
0x22067  ldarg.1
0x22068  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x2206d  ldstr    aBit// "bit"
0x22072  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22077  brtrue.s loc_2209D
0x22079  ldarg.1
0x2207a  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x2207f  ldstr    aPicklist// "picklist"
0x22084  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22089  brtrue.s loc_2209D
0x2208b  ldarg.1
0x2208c  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x22091  ldstr    aMultiselectpic// "multiselectpicklist"
0x22096  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2209b  brfalse.s loc_220AA
0x2209d  ldarg.1
0x2209e  castclass Microsoft.Crm.Metadata.PicklistAttributeInfo
0x220a3  ldloc.1
0x220a4  ldarg.3
0x220a5  call     void Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetLinkedAttribute(class Microsoft.Crm.Metadata.PicklistAttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x220aa  ret
```
