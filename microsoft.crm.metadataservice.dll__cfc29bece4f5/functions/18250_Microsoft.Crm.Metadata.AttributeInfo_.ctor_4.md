# Microsoft.Crm.Metadata.AttributeInfo::.ctor_4

- ea: `0x18250`
- end: `0x182fd`
- name: `Microsoft.Crm.Metadata.AttributeInfo::.ctor_4`
- size: `173`
- prototype: ``
- caller_count: `17`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19760`
- `0x1e910`
- `0x235e0`
- `0x29c50`
- `0x2bf00`
- `0x2c1d0`
- `0x33840`
- `0x3d920`
- `0x40ee0`
- `0x432a0`
- `0x435e0`
- `0x43950`
- `0x44080`
- `0x44640`
- `0x4a3e0`
- `0x4fe10`
- `0x58be0`

## callees

- `0x18250`
- `0x18480`
- `0x18500`
- `0x2bda0`
- `0x48b90`
- `0x48bf0`
- `0x48c30`

## string_xrefs

- `0x18288`: `The attribute description of the update data should not be null, otherwise we can't identify the attribute being updated`
- `0x1828d`: `updateData`
- `0x182aa`: `The attribute id must be set on the description of the update data`

## pseudocode

```c

```

## disassembly

```asm
0x18250  ldarg.0
0x18251  ldstr    aDisplaynames// "displaynames"
0x18256  ldstr    aDisplayname_0// "displayname"
0x1825b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x18260  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::<DisplayNames>k__BackingField
0x18265  ldarg.0
0x18266  ldstr    aDescriptions// "Descriptions"
0x1826b  ldstr    aDescription// "Description"
0x18270  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x18275  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::<Description>k__BackingField
0x1827a  ldarg.0
0x1827b  call     instance void [mscorlib]System.Object::.ctor()
0x18280  ldarg.1
0x18281  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x18286  brtrue.s loc_18298
0x18288  ldstr    aTheAttributeDe// "The attribute description of the update"...
0x1828d  ldstr    aUpdatedata// "updateData"
0x18292  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string, string)
0x18297  throw
0x18298  ldarg.1
0x18299  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1829e  ldstr    aAttributeid// "attributeid"
0x182a3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x182a8  brfalse.s loc_182B5
0x182aa  ldstr    aTheAttributeId// "The attribute id must be set on the des"...
0x182af  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x182b4  throw
0x182b5  ldarg.0
0x182b6  ldarg.1
0x182b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x182bc  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x182c1  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::attributeData
0x182c6  ldarg.0
0x182c7  ldarg.1
0x182c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeData::get_Descriptions()
0x182cd  ldstr    aDescriptions// "Descriptions"
0x182d2  ldstr    aDescription// "Description"
0x182d7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.DataToInfoConversionHelper::CreateLabelCollectionFromEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection labelsEntityCollection, string collectionName, string labelName)
0x182dc  call     instance void Microsoft.Crm.Metadata.AttributeInfo::set_Description(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection value)
0x182e1  ldarg.0
0x182e2  ldarg.1
0x182e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeData::get_DisplayNames()
0x182e8  ldstr    aDisplaynames// "displaynames"
0x182ed  ldstr    aDisplayname_0// "displayname"
0x182f2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.DataToInfoConversionHelper::CreateLabelCollectionFromEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection labelsEntityCollection, string collectionName, string labelName)
0x182f7  call     instance void Microsoft.Crm.Metadata.AttributeInfo::set_DisplayNames(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection value)
0x182fc  ret
```
