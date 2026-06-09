# Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetForCreate

- ea: `0x22580`
- end: `0x22832`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetForCreate`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x21360`

## callees

- `0x18530`
- `0x18760`
- `0x216e0`
- `0x22580`
- `0x22840`
- `0x40f10`
- `0x40f20`
- `0x4ab20`
- `0x4ab70`
- `0x4ba00`

## string_xrefs

- `0x225b0`: `OptionSet.IsGlobal is NULL. It should have been set already.`
- `0x22714`: `OptionSet.OptionSetId cannot be NULL or Guid.Empty. In order to create an Attribute that links to a Global OptionSet you must set the OptionSet.OptionSetId property to a valid existing Global OptionSet.`
- `0x227b4`: `You cannot set Options property for an Attribute that links to an existing Global OptionSet.`
- `0x227f3`: `OptionSet with OptionSetId ({0}) does not exist. You cannot create an Attribute that links to an OptionSet that does not exist.`

## pseudocode

```c

```

## disassembly

```asm
0x22580  ldarg.0
0x22581  ldstr    aEnuminfo// "enumInfo"
0x22586  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2258b  ldarg.0
0x2258c  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType Microsoft.Crm.Metadata.AttributeService::GetOptionSetTypeForEnum(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo)
0x22591  stloc.0
0x22592  ldarg.0
0x22593  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x22598  stloc.1
0x22599  ldloc.1
0x2259a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2259f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x225a4  ldstr    aIsglobal// "isglobal"
0x225a9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x225ae  brfalse.s loc_225C0
0x225b0  ldstr    aOptionsetIsglo_0// "OptionSet.IsGlobal is NULL. It should h"...
0x225b5  ldc.i4   0x80048403
0x225ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x225bf  throw
0x225c0  ldnull
0x225c1  stloc.2
0x225c2  ldloc.1
0x225c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x225c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x225cd  brtrue   loc_226E6
0x225d2  ldarg.0
0x225d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x225d8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x225dd  ldstr    aOptionsetid// "optionsetid"
0x225e2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x225e7  brtrue   loc_22676
0x225ec  ldloc.1
0x225ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x225f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x225f7  ldstr    aOptionsetid// "optionsetid"
0x225fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x22601  brfalse.s loc_22613
0x22603  ldstr    aAttributeOptio// "Attribute.OptionSetId must be NULL when"...
0x22608  ldc.i4   0x80048403
0x2260d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22612  throw
0x22613  ldloc.1
0x22614  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22619  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x2261e  ldarg.0
0x2261f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x22624  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x22629  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2262e  brfalse.s loc_22676
0x22630  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22635  ldstr    aAttributeOptio_0// "Attribute.OptionSetId({0}) is optional."...
0x2263a  ldc.i4.2
0x2263b  newarr   [mscorlib]System.Object
0x22640  dup
0x22641  ldc.i4.0
0x22642  ldarg.0
0x22643  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x22648  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x2264d  box      [mscorlib]System.Guid
0x22652  stelem.ref
0x22653  dup
0x22654  ldc.i4.1
0x22655  ldloc.1
0x22656  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2265b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x22660  box      [mscorlib]System.Guid
0x22665  stelem.ref
0x22666  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2266b  ldc.i4   0x80048403
0x22670  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22675  throw
0x22676  ldloc.1
0x22677  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2267c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x22681  ldstr    aOptionsettype// "optionsettype"
0x22686  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2268b  brtrue   loc_22829
0x22690  ldloc.0
0x22691  ldloc.1
0x22692  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22697  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x2269c  beq      loc_22829
0x226a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x226a6  ldstr    aTheAttributeTy// "The Attribute type ({0}) and OptionSet "...
0x226ab  ldc.i4.3
0x226ac  newarr   [mscorlib]System.Object
0x226b1  dup
0x226b2  ldc.i4.0
0x226b3  ldarg.0
0x226b4  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x226b9  stelem.ref
0x226ba  dup
0x226bb  ldc.i4.1
0x226bc  ldloc.1
0x226bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x226c2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x226c7  box      [mscorlib]System.Int32
0x226cc  stelem.ref
0x226cd  dup
0x226ce  ldc.i4.2
0x226cf  ldloc.0
0x226d0  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType
0x226d5  stelem.ref
0x226d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x226db  ldc.i4   0x80048403
0x226e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x226e5  throw
0x226e6  ldloc.1
0x226e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x226ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x226f1  ldstr    aOptionsetid// "optionsetid"
0x226f6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x226fb  brtrue.s loc_22714
0x226fd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22702  ldloc.1
0x22703  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22708  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x2270d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x22712  brfalse.s loc_22724
0x22714  ldstr    aOptionsetOptio// "OptionSet.OptionSetId cannot be NULL or"...
0x22719  ldc.i4   0x80048403
0x2271e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22723  throw
0x22724  ldarg.0
0x22725  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2272a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x2272f  ldstr    aOptionsetid// "optionsetid"
0x22734  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x22739  brtrue.s loc_2279E
0x2273b  ldloc.1
0x2273c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22741  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x22746  ldarg.0
0x22747  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2274c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x22751  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x22756  brfalse.s loc_2279E
0x22758  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2275d  ldstr    aAttributeOptio_1// "Attribute.OptionSetId({0}) is optional."...
0x22762  ldc.i4.2
0x22763  newarr   [mscorlib]System.Object
0x22768  dup
0x22769  ldc.i4.0
0x2276a  ldarg.0
0x2276b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x22770  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x22775  box      [mscorlib]System.Guid
0x2277a  stelem.ref
0x2277b  dup
0x2277c  ldc.i4.1
0x2277d  ldloc.1
0x2277e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22783  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x22788  box      [mscorlib]System.Guid
0x2278d  stelem.ref
0x2278e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22793  ldc.i4   0x80048403
0x22798  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2279d  throw
0x2279e  ldloc.1
0x2279f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x227a4  brfalse.s loc_227C4
0x227a6  ldc.i4.0
0x227a7  ldloc.1
0x227a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x227ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x227b2  bge.s    loc_227C4
0x227b4  ldstr    aYouCannotSetOp// "You cannot set Options property for an "...
0x227b9  ldc.i4   0x80048403
0x227be  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x227c3  throw
0x227c4  nop
0x227c5  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x227ca  ldarg.0
0x227cb  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x227d0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x227d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x227da  ldstr    aOptionset_0// "OptionSet"
0x227df  ldarg.1
0x227e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x227e5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x227ea  stloc.2
0x227eb  leave.s  loc_2281D
0x227ed  stloc.3
0x227ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x227f3  ldstr    aOptionsetWithO// "OptionSet with OptionSetId ({0}) does n"...
0x227f8  ldc.i4.1
0x227f9  newarr   [mscorlib]System.Object
0x227fe  dup
0x227ff  ldc.i4.0
0x22800  ldarg.0
0x22801  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSetId()
0x22806  box      [mscorlib]System.Guid
0x2280b  stelem.ref
0x2280c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22811  ldloc.3
0x22812  ldc.i4   0x80048403
0x22817  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x2281c  throw
0x2281d  ldloc.1
0x2281e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22823  ldloc.2
0x22824  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateOptionSetAgainstExistingOptionSet(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag optionSetDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x22829  ldarg.0
0x2282a  ldloc.2
0x2282b  ldarg.1
0x2282c  call     void Microsoft.Crm.Metadata.AttributeService::ValidateParentEnumAttribute(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x22831  ret
```
