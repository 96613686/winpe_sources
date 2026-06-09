# Microsoft.Crm.Metadata.AttributeService::UpdateSystemAttributeInternal

- ea: `0x1e420`
- end: `0x1e5ca`
- name: `Microsoft.Crm.Metadata.AttributeService::UpdateSystemAttributeInternal`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x311e0`

## callees

- `0x17950`
- `0x17980`
- `0x179b0`
- `0x183f0`
- `0x18470`
- `0x184f0`
- `0x18760`
- `0x1e420`
- `0x1ff00`
- `0x20ab0`
- `0x20b40`
- `0x211c0`
- `0x22840`
- `0x40f10`
- `0x44120`
- `0x45580`
- `0x4ab20`
- `0x4ab70`
- `0x4bf20`
- `0x56280`
- `0x56500`

## string_xrefs

- `0x1e580`: `AttributeLookupCreate`

## pseudocode

```c

```

## disassembly

```asm
0x1e420  ldarg.1
0x1e421  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::RemoveLinkAttributes()
0x1e426  ldarg.1
0x1e427  ldarg.2
0x1e428  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1e42d  ldc.i4.1
0x1e42e  ldarg.s  6
0x1e430  ldarg.s  4
0x1e432  call     void Microsoft.Crm.Metadata.AttributeService::ValidateForUpdate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, bool isSystemAttributeCreate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1e437  ldarg.1
0x1e438  isinst   Microsoft.Crm.Metadata.EnumAttributeInfo
0x1e43d  stloc.0
0x1e43e  ldloc.0
0x1e43f  brfalse  loc_1E4F9
0x1e444  ldloc.0
0x1e445  call     valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType Microsoft.Crm.Metadata.AttributeService::GetOptionSetTypeForEnum(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo)
0x1e44a  stloc.1
0x1e44b  ldarg.2
0x1e44c  ldstr    aOptionsetid// "optionsetid"
0x1e451  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x1e456  unbox.any [mscorlib]System.Guid
0x1e45b  stloc.2
0x1e45c  ldarg.s  4
0x1e45e  ldloc.2
0x1e45f  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::RemoveOptionsForOptionSetFromQueue(valuetype [mscorlib]System.Guid)
0x1e464  brfalse.s loc_1E492
0x1e466  ldloc.2
0x1e467  ldloc.0
0x1e468  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1e46d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1e472  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_ParentOptionSetId()
0x1e477  ldloc.1
0x1e478  ldloc.0
0x1e479  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1e47e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x1e483  ldnull
0x1e484  ldarg.s  4
0x1e486  ldarg.s  6
0x1e488  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1e48d  call     void Microsoft.Crm.Metadata.OptionSetService::CreateEnumOptions(valuetype [mscorlib]System.Guid optionSetId, valuetype [mscorlib]System.Guid parentOptionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary enumOptions, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary oldEnumOptions, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1e492  ldarg.s  4
0x1e494  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1e499  brfalse.s loc_1E4F9
0x1e49b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1e4a0  stloc.3
0x1e4a1  ldloc.0
0x1e4a2  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1e4a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1e4ac  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x1e4b1  brfalse.s loc_1E4D0
0x1e4b3  ldstr    aIscustomizable_0// "IsCustomizable"
0x1e4b8  ldloc.3
0x1e4b9  ldloc.0
0x1e4ba  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1e4bf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1e4c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x1e4c9  ldarg.s  6
0x1e4cb  call     void Microsoft.Crm.Metadata.AttributeService::UpdateOptionsetProperty(string propertyName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> propertiesToUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity optionSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1e4d0  ldloc.3
0x1e4d1  ldstr    aIscustomoption// "iscustomoptionset"
0x1e4d6  ldloc.0
0x1e4d7  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x1e4dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x1e4e1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsCustomOptionSet()
0x1e4e6  box      [mscorlib]System.Boolean
0x1e4eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1e4f0  ldarg.s  4
0x1e4f2  ldloc.2
0x1e4f3  ldloc.3
0x1e4f4  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::UpdateOptionSetCreateActionInQueue(valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x1e4f9  ldarg.1
0x1e4fa  ldarg.2
0x1e4fb  ldarg.1
0x1e4fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1e501  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetDescriptionPropertiesForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag existingDescription)
0x1e506  ldarg.s  4
0x1e508  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1e50d  brfalse.s loc_1E523
0x1e50f  ldarg.1
0x1e510  ldarg.2
0x1e511  ldarg.1
0x1e512  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1e517  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetDescriptionPropertiesForInternalSolutions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag existingDescription)
0x1e51c  ldarg.1
0x1e51d  ldarg.2
0x1e51e  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetDisplayMasksForInternalSolutions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription)
0x1e523  ldarg.0
0x1e524  ldstr    aDescription// "Description"
0x1e529  ldarg.1
0x1e52a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_Description()
0x1e52f  ldarg.3
0x1e530  ldc.i4.1
0x1e531  ldarg.s  4
0x1e533  ldarg.s  5
0x1e535  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::UpdateDisplayInformation(valuetype [mscorlib]System.Guid objectId, string objectColumnName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection newLabels, class [mscorlib]System.Collections.ICollection oldLabels, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption)
0x1e53a  ldarg.0
0x1e53b  ldstr    aDisplayname// "DisplayName"
0x1e540  ldarg.1
0x1e541  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_DisplayNames()
0x1e546  ldarg.3
0x1e547  ldc.i4.1
0x1e548  ldarg.s  4
0x1e54a  ldarg.s  5
0x1e54c  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::UpdateDisplayInformation(valuetype [mscorlib]System.Guid objectId, string objectColumnName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection newLabels, class [mscorlib]System.Collections.ICollection oldLabels, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption)
0x1e551  ldarg.s  4
0x1e553  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1e558  brfalse.s loc_1E5C9
0x1e55a  ldarg.1
0x1e55b  isinst   Microsoft.Crm.Metadata.LookupAttributeInfo
0x1e560  stloc.s  4
0x1e562  ldloc.s  4
0x1e564  brfalse.s loc_1E5C9
0x1e566  ldarg.s  6
0x1e568  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x1e56d  ldstr    aImportData// "Import_Data"
0x1e572  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1e577  brfalse.s loc_1E5C9
0x1e579  ldarg.s  6
0x1e57b  newobj   instance void Microsoft.Crm.Metadata.AttributePropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1e580  ldstr    aAttributelooku_0// "AttributeLookupCreate"
0x1e585  ldarg.2
0x1e586  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1e58b  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken Microsoft.Crm.Metadata.PropertiesBackCompatOverrider::GetPropertyValue(string propertyName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataObject)
0x1e590  stloc.s  5
0x1e592  ldloc.s  5
0x1e594  brfalse.s loc_1E5C9
0x1e596  ldloc.s  5
0x1e598  callvirt instance string [mscorlib]System.Object::ToString()
0x1e59d  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1e5a2  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x1e5a7  brfalse.s loc_1E5C9
0x1e5a9  ldarg.0
0x1e5aa  ldarg.s  6
0x1e5ac  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1e5b1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary Microsoft.Crm.Metadata.AttributeService::GetExistingAttributeLookupValues(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1e5b6  stloc.s  6
0x1e5b8  ldloc.s  4
0x1e5ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary Microsoft.Crm.Metadata.LookupAttributeInfo::get_LookupValues()
0x1e5bf  ldarg.0
0x1e5c0  ldloc.s  6
0x1e5c2  ldarg.s  4
0x1e5c4  call     void Microsoft.Crm.Metadata.AttributeService::UpdateLookupTypes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary newLookupValues, valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeLookupValueByTypeDictionary oldLookupValues, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper)
0x1e5c9  ret
```
