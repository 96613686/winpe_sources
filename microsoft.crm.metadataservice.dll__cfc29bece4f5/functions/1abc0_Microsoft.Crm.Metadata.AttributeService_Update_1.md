# Microsoft.Crm.Metadata.AttributeService::Update_1

- ea: `0x1abc0`
- end: `0x1ad3c`
- name: `Microsoft.Crm.Metadata.AttributeService::Update_1`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf380`

## callees

- `0x18ae0`
- `0x19760`
- `0x1abc0`
- `0x1ad50`
- `0x23330`
- `0x48b90`

## string_xrefs

- `0x1abd2`: `The AttributeDescription of the AttributeUpdateData passed to Update must contain the attribute id`

## pseudocode

```c

```

## disassembly

```asm
0x1abc0  ldarg.1
0x1abc1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1abc6  ldstr    aAttributeid// "attributeid"
0x1abcb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1abd0  brfalse.s loc_1ABDD
0x1abd2  ldstr    aTheAttributede_1// "The AttributeDescription of the Attribu"...
0x1abd7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x1abdc  throw
0x1abdd  ldarg.1
0x1abde  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1abe3  ldstr    aAttributeid// "attributeid"
0x1abe8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1abed  unbox.any [mscorlib]System.Guid
0x1abf2  stloc.0
0x1abf3  ldarg.3
0x1abf4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1abf9  ldstr    aAttribute// "Attribute"
0x1abfe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata::GetMetadataEntityByName(string)
0x1ac03  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadataDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_Attributes()
0x1ac08  ldnull
0x1ac09  stloc.1
0x1ac0a  ldstr    aSourcetype// "sourcetype"
0x1ac0f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata>::ContainsKey(var<u1>)
0x1ac14  brfalse.s loc_1AC61
0x1ac16  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1ac1b  ldarg.1
0x1ac1c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1ac21  ldstr    aAttributeid// "attributeid"
0x1ac26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1ac2b  unbox.any [mscorlib]System.Guid
0x1ac30  ldstr    aAttribute// "Attribute"
0x1ac35  ldc.i4.3
0x1ac36  newarr   [mscorlib]System.String
0x1ac3b  dup
0x1ac3c  ldc.i4.0
0x1ac3d  ldstr    aAttributetypei// "attributetypeid"
0x1ac42  stelem.ref
0x1ac43  dup
0x1ac44  ldc.i4.1
0x1ac45  ldstr    aName// "name"
0x1ac4a  stelem.ref
0x1ac4b  dup
0x1ac4c  ldc.i4.2
0x1ac4d  ldstr    aSourcetype// "sourcetype"
0x1ac52  stelem.ref
0x1ac53  ldarg.3
0x1ac54  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1ac59  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x1ac5e  stloc.1
0x1ac5f  br.s     loc_1AC9D
0x1ac61  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x1ac66  ldarg.1
0x1ac67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1ac6c  ldstr    aAttributeid// "attributeid"
0x1ac71  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1ac76  unbox.any [mscorlib]System.Guid
0x1ac7b  ldstr    aAttribute// "Attribute"
0x1ac80  ldc.i4.2
0x1ac81  newarr   [mscorlib]System.String
0x1ac86  dup
0x1ac87  ldc.i4.0
0x1ac88  ldstr    aAttributetypei// "attributetypeid"
0x1ac8d  stelem.ref
0x1ac8e  dup
0x1ac8f  ldc.i4.1
0x1ac90  ldstr    aName// "name"
0x1ac95  stelem.ref
0x1ac96  ldarg.3
0x1ac97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ac9c  stloc.1
0x1ac9d  ldarg.1
0x1ac9e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1aca3  ldstr    aSourcetype// "sourcetype"
0x1aca8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1acad  brtrue.s loc_1ACD4
0x1acaf  ldarg.1
0x1acb0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1acb5  ldstr    aSourcetype// "sourcetype"
0x1acba  ldloc.1
0x1acbb  ldstr    aSourcetype// "sourcetype"
0x1acc0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1acc5  unbox.any [mscorlib]System.Int32
0x1acca  box      [mscorlib]System.Int32
0x1accf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1acd4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1acd9  stloc.2
0x1acda  ldarg.1
0x1acdb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1ace0  ldstr    aAttributetypei// "attributetypeid"
0x1ace5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1acea  brtrue.s loc_1AD04
0x1acec  ldarg.1
0x1aced  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1acf2  ldstr    aAttributetypei// "attributetypeid"
0x1acf7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1acfc  unbox.any [mscorlib]System.Guid
0x1ad01  stloc.2
0x1ad02  br.s     loc_1AD15
0x1ad04  ldloc.1
0x1ad05  ldstr    aAttributetypei// "attributetypeid"
0x1ad0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1ad0f  unbox.any [mscorlib]System.Guid
0x1ad14  stloc.2
0x1ad15  ldarg.1
0x1ad16  ldloc.2
0x1ad17  ldarg.3
0x1ad18  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeInfoFromAttributeUpdateData(class Microsoft.Crm.Metadata.AttributeUpdateData updateData, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1ad1d  stloc.3
0x1ad1e  ldloc.3
0x1ad1f  ldloc.1
0x1ad20  call     void Microsoft.Crm.Metadata.AttributeService::ValidateTypeMatch(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData)
0x1ad25  ldloc.3
0x1ad26  ldarg.3
0x1ad27  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1ad2c  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::ValidateUpdate(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1ad31  ldarg.0
0x1ad32  ldloc.0
0x1ad33  ldloc.3
0x1ad34  ldarg.2
0x1ad35  ldarg.3
0x1ad36  call     instance void Microsoft.Crm.Metadata.AttributeService::Update(valuetype [mscorlib]System.Guid attributeId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, bool mergeLabels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ad3b  ret
```
