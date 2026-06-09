# Microsoft.Crm.Metadata.AttributeService::ValidateParentEnumAttribute

- ea: `0x216e0`
- end: `0x219a8`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateParentEnumAttribute`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x20350`
- `0x22580`

## callees

- `0x18490`
- `0x184d0`
- `0x18760`
- `0x216e0`
- `0x40f10`
- `0x4ab20`

## string_xrefs

- `0x2187d`: `The parent option set for '{0}' does not match the option set linked to the specified parent enum attribute {1} for {2}`
- `0x21903`: `The parent option set for '{0}' does not match the option set linked to the specified parent enum attribute {1} for {2}`

## pseudocode

```c

```

## disassembly

```asm
0x216e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x216e5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x216ea  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CascadingOptionSet()
0x216ef  ldarg.2
0x216f0  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x216f5  brtrue.s loc_2171E
0x216f7  ldarg.0
0x216f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x216fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ParentEnumAttributeId()
0x21702  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21707  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2170c  brfalse.s loc_2171E
0x2170e  ldstr    aCascadingOptio// "Cascading Option Set feature is not ena"...
0x21713  ldc.i4   0x80061113
0x21718  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2171d  throw
0x2171e  ldarg.0
0x2171f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21724  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x21729  ldstr    aParentenumattr// "parentenumattributeid"
0x2172e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string)
0x21733  brfalse  loc_219A7
0x21738  ldarg.0
0x21739  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2173e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x21743  ldstr    aParentenumattr// "parentenumattributeid"
0x21748  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2174d  brfalse  loc_219A7
0x21752  ldarg.0
0x21753  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21758  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ParentEnumAttributeId()
0x2175d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21762  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21767  brfalse  loc_2195A
0x2176c  ldarg.0
0x2176d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21772  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ParentEnumAttributeId()
0x21777  stloc.0
0x21778  ldc.i4.5
0x21779  newarr   [mscorlib]System.String
0x2177e  dup
0x2177f  ldc.i4.0
0x21780  ldstr    aAttributeid// "attributeid"
0x21785  stelem.ref
0x21786  dup
0x21787  ldc.i4.1
0x21788  ldstr    aName// "name"
0x2178d  stelem.ref
0x2178e  dup
0x2178f  ldc.i4.2
0x21790  ldstr    aAttributetypei// "attributetypeid"
0x21795  stelem.ref
0x21796  dup
0x21797  ldc.i4.3
0x21798  ldstr    aOptionsetid// "optionsetid"
0x2179d  stelem.ref
0x2179e  dup
0x2179f  ldc.i4.4
0x217a0  ldstr    aEntityid// "entityid"
0x217a5  stelem.ref
0x217a6  stloc.1
0x217a7  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x217ac  ldloc.0
0x217ad  ldstr    aAttribute// "Attribute"
0x217b2  ldloc.1
0x217b3  ldarg.2
0x217b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x217b9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x217be  stloc.2
0x217bf  ldloc.2
0x217c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x217c5  ldarg.0
0x217c6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x217cb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x217d0  ldstr    aBothEnumAttrib// "Both enum attribute attribute and its p"...
0x217d5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x217da  ldloc.2
0x217db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeTypeId()
0x217e0  ldarg.0
0x217e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x217e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeTypeId()
0x217eb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::IsValidParentEnumAttributeType(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x217f0  brtrue.s loc_2185A
0x217f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x217f7  ldstr    aParentenumattr_0// "ParentEnumAttribute of type '{0}' is no"...
0x217fc  ldc.i4.3
0x217fd  newarr   [mscorlib]System.Object
0x21802  dup
0x21803  ldc.i4.0
0x21804  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x21809  ldloc.2
0x2180a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeTypeId()
0x2180f  box      [mscorlib]System.Guid
0x21814  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x21819  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x2181e  stelem.ref
0x2181f  dup
0x21820  ldc.i4.1
0x21821  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x21826  ldarg.0
0x21827  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2182c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeTypeId()
0x21831  box      [mscorlib]System.Guid
0x21836  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2183b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x21840  stelem.ref
0x21841  dup
0x21842  ldc.i4.2
0x21843  ldarg.0
0x21844  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x21849  stelem.ref
0x2184a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2184f  ldc.i4   0x80040203
0x21854  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x21859  throw
0x2185a  ldarg.1
0x2185b  brfalse.s loc_218B3
0x2185d  ldarg.1
0x2185e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x21863  brfalse.s loc_218B3
0x21865  ldarg.1
0x21866  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x2186b  ldloc.2
0x2186c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x21871  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21876  brfalse.s loc_218B3
0x21878  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2187d  ldstr    aTheParentOptio// "The parent option set for '{0}' does no"...
0x21882  ldc.i4.3
0x21883  newarr   [mscorlib]System.Object
0x21888  dup
0x21889  ldc.i4.0
0x2188a  ldarg.1
0x2188b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x21890  stelem.ref
0x21891  dup
0x21892  ldc.i4.1
0x21893  ldloc.2
0x21894  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Name()
0x21899  stelem.ref
0x2189a  dup
0x2189b  ldc.i4.2
0x2189c  ldarg.0
0x2189d  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x218a2  stelem.ref
0x218a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x218a8  ldc.i4   0x80048403
0x218ad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x218b2  throw
0x218b3  ldarg.0
0x218b4  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x218b9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x218be  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x218c3  brtrue.s loc_21943
0x218c5  ldarg.0
0x218c6  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x218cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x218d0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x218d5  ldstr    aParentoptionse// "parentoptionsetid"
0x218da  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x218df  brtrue.s loc_21943
0x218e1  ldarg.0
0x218e2  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x218e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x218ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x218f1  ldloc.2
0x218f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x218f7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x218fc  brfalse.s loc_21943
0x218fe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21903  ldstr    aTheParentOptio// "The parent option set for '{0}' does no"...
0x21908  ldc.i4.3
0x21909  newarr   [mscorlib]System.Object
0x2190e  dup
0x2190f  ldc.i4.0
0x21910  ldarg.0
0x21911  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x21916  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2191b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x21920  stelem.ref
0x21921  dup
0x21922  ldc.i4.1
0x21923  ldloc.2
0x21924  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Name()
0x21929  stelem.ref
0x2192a  dup
0x2192b  ldc.i4.2
0x2192c  ldarg.0
0x2192d  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x21932  stelem.ref
0x21933  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21938  ldc.i4   0x80048403
0x2193d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x21942  throw
0x21943  ldarg.0
0x21944  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x21949  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2194e  ldloc.2
0x2194f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x21954  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::set_ParentOptionSetId(valuetype [mscorlib]System.Guid)
0x21959  ret
0x2195a  ldarg.0
0x2195b  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x21960  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x21965  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x2196a  brtrue.s loc_219A7
0x2196c  ldarg.0
0x2196d  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x21972  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x21977  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x2197c  ldstr    aParentoptionse// "parentoptionsetid"
0x21981  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string)
0x21986  brfalse.s loc_219A7
0x21988  ldarg.0
0x21989  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x2198e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x21993  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x21998  ldstr    aParentoptionse// "parentoptionsetid"
0x2199d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x219a2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x219a7  ret
```
