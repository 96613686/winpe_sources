# Microsoft.Crm.Metadata.ActivityEntityService::UpdateDefaultDataOnRelatedAttributes

- ea: `0x284e0`
- end: `0x286d7`
- name: `Microsoft.Crm.Metadata.ActivityEntityService::UpdateDefaultDataOnRelatedAttributes`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x276c0`

## callees

- `0x284e0`
- `0x286e0`
- `0x28720`
- `0x44e50`
- `0x45110`
- `0x45150`
- `0x55de0`
- `0x56500`
- `0x565f0`
- `0x56670`

## string_xrefs

- `0x285eb`: `validforcreateapi`
- `0x285fd`: `validforupdateapi`

## pseudocode

```c

```

## disassembly

```asm
0x284e0  ldarg.1
0x284e1  ldstr    aAttribute// "Attribute"
0x284e6  ldloca.s 0
0x284e8  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition::TryRetrieveRelatedDataSet(string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>&)
0x284ed  brtrue.s loc_284F0
0x284ef  ret
0x284f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x284f5  stloc.1
0x284f6  ldarg.3
0x284f7  newobj   instance void Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x284fc  ldarg.2
0x284fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.IEntityInfo::get_EntityDescription()
0x28502  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x28507  stloc.3
0x28508  ldloca.s 3
0x2850a  constrained. [mscorlib]System.Guid
0x28510  callvirt instance string [mscorlib]System.Object::ToString()
0x28515  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::GetIgnoreListForAttributes(string entityId)
0x2851a  stloc.2
0x2851b  ldloc.0
0x2851c  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Values()
0x28521  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x28526  stloc.s  4
0x28528  br       loc_286B4
0x2852d  ldloc.s  4
0x2852f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x28534  stloc.s  5
0x28536  ldloc.s  5
0x28538  ldstr    aDisplaymask// "displaymask"
0x2853d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x28542  unbox.any [mscorlib]System.Int32
0x28547  stloc.s  6
0x28549  ldarg.2
0x2854a  callvirt instance bool Microsoft.Crm.Metadata.IEntityInfo::get_IsCollaboration()
0x2854f  brfalse.s loc_28574
0x28551  ldloc.s  6
0x28553  ldc.i4   0x100
0x28558  and
0x28559  brfalse.s loc_28574
0x2855b  ldloc.s  6
0x2855d  ldc.i4.2
0x2855e  or
0x2855f  stloc.s  6
0x28561  ldloc.s  5
0x28563  ldstr    aDisplaymask// "displaymask"
0x28568  ldloc.s  6
0x2856a  box      [mscorlib]System.Int32
0x2856f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x28574  ldloc.s  5
0x28576  ldstr    aAttributetypei// "attributetypeid"
0x2857b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x28580  unbox.any [mscorlib]System.Guid
0x28585  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x2858a  ldstr    aStatus// "status"
0x2858f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x28594  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x28599  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2859e  brfalse.s loc_285BD
0x285a0  ldloc.s  6
0x285a2  ldc.i4   0x1C000000
0x285a7  or
0x285a8  stloc.s  6
0x285aa  ldloc.s  5
0x285ac  ldstr    aDisplaymask// "displaymask"
0x285b1  ldloc.s  6
0x285b3  box      [mscorlib]System.Int32
0x285b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x285bd  ldarg.0
0x285be  ldarg.2
0x285bf  ldloc.s  5
0x285c1  ldarg.s  4
0x285c3  call     instance void Microsoft.Crm.Metadata.ActivityEntityService::MarkAttributesValidForUpdate(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attribute, [opt] bool isInternalSolution)
0x285c8  ldloc.s  5
0x285ca  ldstr    aIsinheritancet// "isinheritancetypeattribute"
0x285cf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x285d4  brtrue.s loc_2860D
0x285d6  ldloc.s  5
0x285d8  ldstr    aIsinheritancet// "isinheritancetypeattribute"
0x285dd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x285e2  unbox.any [mscorlib]System.Boolean
0x285e7  brfalse.s loc_2860D
0x285e9  ldloc.s  5
0x285eb  ldstr    aValidforcreate// "validforcreateapi"
0x285f0  ldc.i4.0
0x285f1  box      [mscorlib]System.Boolean
0x285f6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x285fb  ldloc.s  5
0x285fd  ldstr    aValidforupdate// "validforupdateapi"
0x28602  ldc.i4.0
0x28603  box      [mscorlib]System.Boolean
0x28608  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x2860d  ldarg.2
0x2860e  callvirt instance bool Microsoft.Crm.Metadata.IEntityInfo::get_IsCustomActivity()
0x28613  brfalse.s loc_28656
0x28615  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x2861a  ldloc.s  5
0x2861c  ldstr    aName// "name"
0x28621  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x28626  castclass [mscorlib]System.String
0x2862b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28630  brfalse.s loc_28656
0x28632  ldloc.s  5
0x28634  ldstr    aIsfilterable// "isfilterable"
0x28639  ldc.i4.1
0x2863a  box      [mscorlib]System.Boolean
0x2863f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x28644  ldloc.s  5
0x28646  ldstr    aIsfilterablese// "isfilterablesetbysystem"
0x2864b  ldc.i4.1
0x2864c  box      [mscorlib]System.Boolean
0x28651  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x28656  ldarg.s  4
0x28658  brfalse.s loc_286B4
0x2865a  ldarg.3
0x2865b  newobj   instance void Microsoft.Crm.Metadata.AttributePropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x28660  ldloc.s  5
0x28662  callvirt instance void Microsoft.Crm.Metadata.IPropertiesBackCompatOverrider::Override(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity innerEntityData)
0x28667  ldloc.2
0x28668  ldloc.s  5
0x2866a  ldstr    aName// "name"
0x2866f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x28674  callvirt instance string [mscorlib]System.Object::ToString()
0x28679  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x2867e  brtrue.s loc_2869D
0x28680  ldsfld   class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.ActivityEntityService::_removedViewAttributesRelatedAttributeIds
0x28685  ldloc.s  5
0x28687  ldstr    aAttributeid// "attributeid"
0x2868c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x28691  unbox.any [mscorlib]System.Guid
0x28696  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x2869b  brfalse.s loc_286B4
0x2869d  ldloc.1
0x2869e  ldloc.s  5
0x286a0  ldstr    aName// "name"
0x286a5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x286aa  callvirt instance string [mscorlib]System.Object::ToString()
0x286af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x286b4  ldloc.s  4
0x286b6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x286bb  brtrue   loc_2852D
0x286c0  leave.s  loc_286CE
0x286c2  ldloc.s  4
0x286c4  brfalse.s loc_286CD
0x286c6  ldloc.s  4
0x286c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x286cd  endfinally
0x286ce  ldarg.0
0x286cf  ldarg.1
0x286d0  ldloc.1
0x286d1  call     instance void Microsoft.Crm.Metadata.ActivityEntityService::RemoveBadAttributeRelatedInfo(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityMetadataDefinition newActivityDefinition, class [mscorlib]System.Collections.Generic.List`1<string> attributesToBeDeleted)
0x286d6  ret
```
