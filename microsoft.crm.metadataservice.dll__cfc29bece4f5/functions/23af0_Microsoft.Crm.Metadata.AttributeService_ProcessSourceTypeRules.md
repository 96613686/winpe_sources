# Microsoft.Crm.Metadata.AttributeService::ProcessSourceTypeRules

- ea: `0x23af0`
- end: `0x23cf0`
- name: `Microsoft.Crm.Metadata.AttributeService::ProcessSourceTypeRules`
- size: `512`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c170`
- `0x1ff00`

## callees

- `0x184d0`
- `0x18760`
- `0x187a0`
- `0x187b0`
- `0x187c0`
- `0x187d0`
- `0x18af0`
- `0x23af0`
- `0x23cf0`
- `0x24220`
- `0x24290`
- `0x242e0`
- `0x24340`
- `0x24e90`
- `0x25610`

## string_xrefs

- `0x23c1e`: `FieldSecurityProfile`
- `0x23c30`: `prvWriteFieldSecurityProfile`

## pseudocode

```c

```

## disassembly

```asm
0x23af0  ldarg.1
0x23af1  brfalse  loc_23BAB
0x23af6  ldarg.1
0x23af7  ldstr    aSourcetype// "sourcetype"
0x23afc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x23b01  brtrue   loc_23BAB
0x23b06  ldarg.0
0x23b07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23b0c  ldstr    aSourcetype// "sourcetype"
0x23b11  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x23b16  brtrue.s loc_23B30
0x23b18  ldarg.0
0x23b19  ldarg.1
0x23b1a  ldstr    aSourcetype// "sourcetype"
0x23b1f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23b24  unbox.any [mscorlib]System.Int32
0x23b29  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_SourceType(int32 value)
0x23b2e  br.s     loc_23BAB
0x23b30  ldarg.0
0x23b31  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23b36  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceType()
0x23b3b  ldarg.1
0x23b3c  ldstr    aSourcetype// "sourcetype"
0x23b41  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23b46  unbox.any [mscorlib]System.Int32
0x23b4b  beq.s    loc_23BAB
0x23b4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23b52  ldstr    aAttribute0HasS// "Attribute {0} has SourceType {1}, but {"...
0x23b57  ldc.i4.3
0x23b58  newarr   [mscorlib]System.Object
0x23b5d  dup
0x23b5e  ldc.i4.0
0x23b5f  ldarg.1
0x23b60  ldstr    aName// "name"
0x23b65  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23b6a  castclass [mscorlib]System.String
0x23b6f  stelem.ref
0x23b70  dup
0x23b71  ldc.i4.1
0x23b72  ldarg.1
0x23b73  ldstr    aSourcetype// "sourcetype"
0x23b78  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x23b7d  unbox.any [mscorlib]System.Int32
0x23b82  box      [mscorlib]System.Int32
0x23b87  stelem.ref
0x23b88  dup
0x23b89  ldc.i4.2
0x23b8a  ldarg.0
0x23b8b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23b90  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_SourceType()
0x23b95  box      [mscorlib]System.Int32
0x23b9a  stelem.ref
0x23b9b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23ba0  ldc.i4   0x80041A06
0x23ba5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x23baa  throw
0x23bab  ldarg.0
0x23bac  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::ValidateSourceType()
0x23bb1  ldarg.0
0x23bb2  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsCalculatedField()
0x23bb7  brtrue.s loc_23BC2
0x23bb9  ldarg.0
0x23bba  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsRollupField()
0x23bbf  brtrue.s loc_23BC2
0x23bc1  ret
0x23bc2  ldarg.0
0x23bc3  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsCalculatedField()
0x23bc8  brfalse.s loc_23BE1
0x23bca  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x23bcf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x23bd4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CalculatedFields()
0x23bd9  ldarg.2
0x23bda  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23bdf  brfalse.s loc_23C00
0x23be1  ldarg.0
0x23be2  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsRollupField()
0x23be7  brfalse.s loc_23C11
0x23be9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x23bee  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x23bf3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Rollups()
0x23bf8  ldarg.2
0x23bf9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23bfe  brtrue.s loc_23C11
0x23c00  ldc.i4   0x80060422
0x23c05  ldc.i4.0
0x23c06  newarr   [mscorlib]System.Object
0x23c0b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23c10  throw
0x23c11  ldarg.0
0x23c12  ldarg.1
0x23c13  call     void Microsoft.Crm.Metadata.AttributeService::DecideIfFormulaRegenerationRequired(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData)
0x23c18  ldarg.2
0x23c19  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23c1e  ldstr    aFieldsecurityp// "FieldSecurityProfile"
0x23c23  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x23c28  stloc.0
0x23c29  ldarg.2
0x23c2a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x23c2f  ldloc.0
0x23c30  ldstr    aPrvwritefields// "prvWriteFieldSecurityProfile"
0x23c35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(string)
0x23c3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x23c3f  ldarg.2
0x23c40  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23c45  ldarg.0
0x23c46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23c4b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_FormulaDefinition()
0x23c50  brtrue.s loc_23C53
0x23c52  ret
0x23c53  ldarg.2
0x23c54  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x23c59  ldarg.0
0x23c5a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x23c5f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x23c64  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x23c69  ldarg.0
0x23c6a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23c6f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_FormulaDefinition()
0x23c74  ldarg.2
0x23c75  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Metadata.AttributeService::DeserializeFormulaDefinition(string entityLogicalName, string formulaDefinition, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23c7a  stloc.1
0x23c7b  ldarg.0
0x23c7c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23c81  ldloc.1
0x23c82  ldarg.2
0x23c83  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowDependencyVisitorBase Microsoft.Crm.Metadata.AttributeService::GetFormulaDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attribute, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep formula, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23c88  stloc.2
0x23c89  ldarg.0
0x23c8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23c8f  ldloc.2
0x23c90  ldarg.2
0x23c91  call     int32 Microsoft.Crm.Metadata.AttributeService::GetSourceTypeMaskFromFormulaDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag description, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowDependencyVisitorBase visitor, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23c96  stloc.3
0x23c97  ldarg.0
0x23c98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23c9d  ldloc.3
0x23c9e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_SourceTypeMask(int32)
0x23ca3  ldarg.2
0x23ca4  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x23ca9  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x23cae  ldc.i4.1
0x23caf  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x23cb4  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x23cb9  brtrue.s loc_23CD0
0x23cbb  ldarg.0
0x23cbc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23cc1  ldloc.1
0x23cc2  ldloc.2
0x23cc3  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x23cc8  ldarg.2
0x23cc9  call     void Microsoft.Crm.Metadata.AttributeService::ValidateFormulaDefinition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attribute, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep formula, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowDependencyVisitorBase visitor, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> attributesInSolution, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23cce  br.s     loc_23CE7
0x23cd0  ldarg.0
0x23cd1  callvirt instance int32 Microsoft.Crm.Metadata.AttributeInfo::get_SourceType()
0x23cd6  ldc.i4.1
0x23cd7  bne.un.s loc_23CE7
0x23cd9  ldarg.0
0x23cda  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x23cdf  ldloc.1
0x23ce0  ldarg.2
0x23ce1  ldc.i4.1
0x23ce2  call     void Microsoft.Crm.Metadata.AttributeService::ValidateFormulaDefinitionContentBySourceType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attribute, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep formula, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool ignoreInvalidAttributes)
0x23ce7  ldarg.0
0x23ce8  ldloc.1
0x23ce9  ldarg.2
0x23cea  call     void Microsoft.Crm.Metadata.AttributeService::SetRollupFieldDefaultValue(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep formula, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23cef  ret
```
