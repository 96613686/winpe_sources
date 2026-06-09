# Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetForUpdate

- ea: `0x20350`
- end: `0x20580`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetForUpdate`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ff00`

## callees

- `0x18760`
- `0x20350`
- `0x216e0`
- `0x40f10`
- `0x4ab20`
- `0x4ab30`
- `0x4ab50`
- `0x4ab70`
- `0x4ba00`

## string_xrefs

- `0x20456`: `OptionSet.IsGlobal is NULL. It should have been set already`
- `0x204e1`: `The Attribute is linked to a Global OptionSet. Options for a Global OptionSet cannot be updated while updating an Attribute.`
- `0x204f9`: `The Attribute is linked to a Global OptionSet. DisplayNames for a Global OptionSet cannot be updated while updating an Attribute.`
- `0x20511`: `The Attribute is linked to a Global OptionSet. Descriptions for a Global OptionSet cannot be updated while updating an Attribute.`
- `0x20567`: `The Attribute is linked to a Global OptionSet. ParentOptionSetId for a Global OptionSet cannot be updated while updating an Attribute.`

## pseudocode

```c

```

## disassembly

```asm
0x20350  ldarg.0
0x20351  ldstr    aEnuminfo// "enumInfo"
0x20356  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2035b  ldarg.0
0x2035c  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x20361  stloc.0
0x20362  ldarg.1
0x20363  ldstr    aOptionsetid// "optionsetid"
0x20368  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2036d  unbox.any [mscorlib]System.Guid
0x20372  stloc.1
0x20373  ldloc.0
0x20374  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x20379  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x2037e  ldstr    aOptionsetid// "optionsetid"
0x20383  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x20388  brtrue.s loc_203D9
0x2038a  ldloc.1
0x2038b  ldloc.0
0x2038c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x20391  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x20396  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2039b  brfalse.s loc_203D9
0x2039d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x203a2  ldstr    aOptionsetidCan_0// "OptionSetId cannot be changed. EnumAttr"...
0x203a7  ldc.i4.2
0x203a8  newarr   [mscorlib]System.Object
0x203ad  dup
0x203ae  ldc.i4.0
0x203af  ldloc.0
0x203b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x203b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x203ba  box      [mscorlib]System.Guid
0x203bf  stelem.ref
0x203c0  dup
0x203c1  ldc.i4.1
0x203c2  ldloc.1
0x203c3  box      [mscorlib]System.Guid
0x203c8  stelem.ref
0x203c9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x203ce  ldc.i4   0x80048403
0x203d3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x203d8  throw
0x203d9  ldarg.0
0x203da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x203df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x203e4  ldstr    aOptionsetid// "optionsetid"
0x203e9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x203ee  brtrue.s loc_2043F
0x203f0  ldloc.1
0x203f1  ldarg.0
0x203f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x203f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x203fc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20401  brfalse.s loc_2043F
0x20403  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20408  ldstr    aOptionsetidCan_1// "OptionSetId cannot be changed. EnumAttr"...
0x2040d  ldc.i4.2
0x2040e  newarr   [mscorlib]System.Object
0x20413  dup
0x20414  ldc.i4.0
0x20415  ldarg.0
0x20416  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2041b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x20420  box      [mscorlib]System.Guid
0x20425  stelem.ref
0x20426  dup
0x20427  ldc.i4.1
0x20428  ldloc.1
0x20429  box      [mscorlib]System.Guid
0x2042e  stelem.ref
0x2042f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x20434  ldc.i4   0x80048403
0x20439  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2043e  throw
0x2043f  ldloc.0
0x20440  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x20445  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x2044a  ldstr    aIsglobal// "isglobal"
0x2044f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x20454  brfalse.s loc_20466
0x20456  ldstr    aOptionsetIsglo// "OptionSet.IsGlobal is NULL. It should h"...
0x2045b  ldc.i4   0x80048403
0x20460  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x20465  throw
0x20466  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x2046b  ldloc.1
0x2046c  ldstr    aOptionset_0// "OptionSet"
0x20471  ldc.i4.4
0x20472  newarr   [mscorlib]System.String
0x20477  dup
0x20478  ldc.i4.0
0x20479  ldstr    aOptionsettype// "optionsettype"
0x2047e  stelem.ref
0x2047f  dup
0x20480  ldc.i4.1
0x20481  ldstr    aIsglobal// "isglobal"
0x20486  stelem.ref
0x20487  dup
0x20488  ldc.i4.2
0x20489  ldstr    aOptionsetid// "optionsetid"
0x2048e  stelem.ref
0x2048f  dup
0x20490  ldc.i4.3
0x20491  ldstr    aParentoptionse// "parentoptionsetid"
0x20496  stelem.ref
0x20497  ldarg.2
0x20498  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2049d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x204a2  stloc.2
0x204a3  ldloc.0
0x204a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x204a9  ldloc.2
0x204aa  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateOptionSetAgainstExistingOptionSet(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag optionSetDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x204af  ldloc.0
0x204b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x204b5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x204ba  brfalse  loc_20577
0x204bf  ldloc.2
0x204c0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x204c5  ldc.i4.3
0x204c6  beq      loc_20577
0x204cb  ldloc.0
0x204cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x204d1  brfalse.s loc_204F1
0x204d3  ldc.i4.0
0x204d4  ldloc.0
0x204d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x204da  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x204df  bge.s    loc_204F1
0x204e1  ldstr    aTheAttributeIs// "The Attribute is linked to a Global Opt"...
0x204e6  ldc.i4   0x80048403
0x204eb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x204f0  throw
0x204f1  ldloc.0
0x204f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_DisplayNames()
0x204f7  brfalse.s loc_20509
0x204f9  ldstr    aTheAttributeIs_0// "The Attribute is linked to a Global Opt"...
0x204fe  ldc.i4   0x80048403
0x20503  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x20508  throw
0x20509  ldloc.0
0x2050a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.OptionSetInfo::get_Descriptions()
0x2050f  brfalse.s loc_20521
0x20511  ldstr    aTheAttributeIs_1// "The Attribute is linked to a Global Opt"...
0x20516  ldc.i4   0x80048403
0x2051b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x20520  throw
0x20521  ldloc.0
0x20522  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x20527  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x2052c  ldstr    aParentoptionse// "parentoptionsetid"
0x20531  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNameValid(string)
0x20536  brfalse.s loc_20577
0x20538  ldloc.0
0x20539  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2053e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x20543  ldstr    aParentoptionse// "parentoptionsetid"
0x20548  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2054d  brfalse.s loc_20577
0x2054f  ldloc.0
0x20550  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x20555  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x2055a  ldloc.2
0x2055b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x20560  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20565  brfalse.s loc_20577
0x20567  ldstr    aTheAttributeIs_2// "The Attribute is linked to a Global Opt"...
0x2056c  ldc.i4   0x80048403
0x20571  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x20576  throw
0x20577  ldarg.0
0x20578  ldloc.2
0x20579  ldarg.2
0x2057a  call     void Microsoft.Crm.Metadata.AttributeService::ValidateParentEnumAttribute(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2057f  ret
```
