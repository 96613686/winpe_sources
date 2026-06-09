# <>c__DisplayClass78_0::<UpdateInternal>b__0

- ea: `0x757d0`
- end: `0x7605b`
- name: `<>c__DisplayClass78_0::<UpdateInternal>b__0`
- size: `2187`
- prototype: ``
- caller_count: `0`
- callee_count: `47`
- tags: `installer_update`

## callees

- `0x17950`
- `0x17980`
- `0x179b0`
- `0x18440`
- `0x18450`
- `0x18470`
- `0x18490`
- `0x184d0`
- `0x184e0`
- `0x184f0`
- `0x18530`
- `0x18610`
- `0x18630`
- `0x18760`
- `0x187b0`
- `0x1aa90`
- `0x1c6a0`
- `0x1c6c0`
- `0x1c750`
- `0x1d2f0`
- `0x1e5d0`
- `0x1e5f0`
- `0x1e670`
- `0x1e910`
- `0x1ea70`
- `0x1ed40`
- `0x1ed70`
- `0x1f020`
- `0x1f1f0`
- `0x1f330`
- `0x1f3e0`
- `0x1f5d0`
- `0x1f670`
- `0x1f700`
- `0x1fe80`
- `0x1ff00`
- `0x20a60`
- `0x20ab0`
- `0x20b40`
- `0x23300`
- `0x255f0`
- `0x26190`
- `0x261b0`
- `0x29080`
- `0x44120`
- `0x59320`
- `0x757d0`

## string_xrefs

- `0x75a73`: `UpdateAttribute`
- `0x75a78`: `UpdateAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x757d0  ldc.i4.0
0x757d1  stloc.0
0x757d2  ldstr    asc_804C0// ""
0x757d7  stloc.1
0x757d8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x757dd  stloc.2
0x757de  ldarg.0
0x757df  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x757e4  ldarg.0
0x757e5  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass78_0::attributeId
0x757ea  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_AttributeId(valuetype [mscorlib]System.Guid value)
0x757ef  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x757f4  ldarg.0
0x757f5  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass78_0::attributeId
0x757fa  ldstr    aAttribute// "Attribute"
0x757ff  ldarg.0
0x75800  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75805  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7580a  stloc.3
0x7580b  ldarg.0
0x7580c  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75811  ldloc.3
0x75812  ldstr    aEntityid// "entityid"
0x75817  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x7581c  unbox.any [mscorlib]System.Guid
0x75821  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_EntityId(valuetype [mscorlib]System.Guid value)
0x75826  ldarg.0
0x75827  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7582c  isinst   Microsoft.Crm.Metadata.EnumAttributeInfo
0x75831  stloc.s  4
0x75833  ldloc.s  4
0x75835  brfalse.s loc_75851
0x75837  ldloc.s  4
0x75839  ldarg.0
0x7583a  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7583f  ldloc.3
0x75840  ldarg.0
0x75841  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75846  ldarg.0
0x75847  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x7584c  call     void Microsoft.Crm.Metadata.AttributeService::UpdateEnumAttribute(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x75851  ldloc.3
0x75852  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x75857  stloc.s  5
0x75859  ldarg.0
0x7585a  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7585f  isinst   Microsoft.Crm.Metadata.StringAttributeInfo
0x75864  brfalse.s loc_75884
0x75866  ldloc.s  5
0x75868  ldarg.0
0x75869  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7586e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75873  ldarg.0
0x75874  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75879  ldarg.0
0x7587a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x7587f  call     void Microsoft.Crm.Metadata.AttributeService::HandleFieldLevelSecurityForYomiAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription existingAttributeDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x75884  ldarg.0
0x75885  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7588a  ldloc.3
0x7588b  ldc.i4.0
0x7588c  ldarg.0
0x7588d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75892  ldarg.0
0x75893  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75898  call     void Microsoft.Crm.Metadata.AttributeService::ValidateForUpdate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, bool isSystemAttributeCreate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x7589d  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x758a2  ldloc.3
0x758a3  ldstr    aEntityid// "entityid"
0x758a8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x758ad  unbox.any [mscorlib]System.Guid
0x758b2  ldstr    aEntity_0// "Entity"
0x758b7  ldc.i4.3
0x758b8  newarr   [mscorlib]System.String
0x758bd  dup
0x758be  ldc.i4.0
0x758bf  ldstr    aEntityid// "entityid"
0x758c4  stelem.ref
0x758c5  dup
0x758c6  ldc.i4.1
0x758c7  ldstr    aIscustomizable// "iscustomizable"
0x758cc  stelem.ref
0x758cd  dup
0x758ce  ldc.i4.2
0x758cf  ldstr    aIsmanaged// "ismanaged"
0x758d4  stelem.ref
0x758d5  ldarg.0
0x758d6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x758db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x758e0  stloc.s  6
0x758e2  ldarg.0
0x758e3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x758e8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x758ed  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x758f2  ldc.i4.7
0x758f3  beq.s    loc_75923
0x758f5  ldarg.0
0x758f6  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x758fb  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x75900  brtrue.s loc_75923
0x75902  ldarg.0
0x75903  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75908  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x7590d  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInUpgradeOrSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x75912  brtrue.s loc_75923
0x75914  ldloc.3
0x75915  ldloc.s  6
0x75917  call     bool Microsoft.Crm.Metadata.AttributeService::IsCustomizableAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity parentEntityData)
0x7591c  brtrue.s loc_75923
0x7591e  leave    loc_7605A
0x75923  ldarg.0
0x75924  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75929  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7592e  stloc.s  7
0x75930  ldloc.s  7
0x75932  ldloc.s  5
0x75934  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x75939  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeId(valuetype [mscorlib]System.Guid)
0x7593e  ldloc.s  7
0x75940  ldloc.s  5
0x75942  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x75947  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_EntityId(valuetype [mscorlib]System.Guid)
0x7594c  ldloc.s  7
0x7594e  ldloc.s  5
0x75950  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_Name()
0x75955  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Name(string)
0x7595a  ldloc.s  7
0x7595c  ldloc.s  5
0x7595e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x75963  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x75968  ldarg.0
0x75969  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7596e  ldloc.s  7
0x75970  ldloc.s  5
0x75972  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetDescriptionPropertiesForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag existingDescription)
0x75977  ldarg.0
0x75978  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x7597d  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x75982  brfalse.s loc_759A0
0x75984  ldarg.0
0x75985  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x7598a  ldloc.s  7
0x7598c  ldloc.s  5
0x7598e  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetDescriptionPropertiesForInternalSolutions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag existingDescription)
0x75993  ldarg.0
0x75994  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75999  ldloc.s  7
0x7599b  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetDisplayMasksForInternalSolutions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag updateDescription)
0x759a0  ldarg.0
0x759a1  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x759a6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x759ab  ldstr    aAutonumberform// "autonumberformat"
0x759b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x759b5  brfalse.s loc_759D3
0x759b7  ldloc.s  5
0x759b9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomField()
0x759be  brfalse.s loc_759D3
0x759c0  ldloc.s  7
0x759c2  dup
0x759c3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x759c8  ldc.i4   0x400000
0x759cd  or
0x759ce  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x759d3  ldarg.0
0x759d4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x759d9  call     bool Microsoft.Crm.Metadata.AttributeService::CheckIfIsGlobalFilterEnabledExists(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x759de  brfalse.s loc_75A20
0x759e0  ldarg.0
0x759e1  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x759e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x759eb  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0x759f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x759f5  brfalse.s loc_75A20
0x759f7  ldarg.0
0x759f8  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x759fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75a02  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsGlobalFilterEnabled()
0x75a07  brfalse.s loc_75A20
0x75a09  ldloc.s  7
0x75a0b  ldarg.0
0x75a0c  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75a11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75a16  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsGlobalFilterEnabled()
0x75a1b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsGlobalFilterEnabled(bool)
0x75a20  ldarg.0
0x75a21  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75a26  call     bool Microsoft.Crm.Metadata.AttributeService::CheckIfIsSortableEnabledExists(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x75a2b  brfalse.s loc_75A6D
0x75a2d  ldarg.0
0x75a2e  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75a33  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75a38  ldstr    aIssortableenab// "issortableenabled"
0x75a3d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x75a42  brfalse.s loc_75A6D
0x75a44  ldarg.0
0x75a45  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75a4a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75a4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsSortableEnabled()
0x75a54  brfalse.s loc_75A6D
0x75a56  ldloc.s  7
0x75a58  ldarg.0
0x75a59  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75a5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75a63  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsSortableEnabled()
0x75a68  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSortableEnabled(bool)
0x75a6d  ldarg.0
0x75a6e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass78_0::attributeId
0x75a73  ldstr    aUpdateattribut// "UpdateAttribute"
0x75a78  ldstr    aUpdateattribut// "UpdateAttribute"
0x75a7d  ldarg.0
0x75a7e  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75a83  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsAuditEnabled()
0x75a88  ldarg.0
0x75a89  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75a8e  call     void Microsoft.Crm.Metadata.AuditHelper::InvokeAuditMetadataPlugin(valuetype [mscorlib]System.Guid targetId, string messageName, string requestName, bool isAuditEnabled, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x75a93  ldloc.s  5
0x75a95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x75a9a  ldarg.0
0x75a9b  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75aa0  ldc.i4.1
0x75aa1  newarr   [mscorlib]System.String
0x75aa6  dup
0x75aa7  ldc.i4.0
0x75aa8  ldstr    aDataproviderid// "dataproviderid"
0x75aad  stelem.ref
0x75aae  ldarg.0
0x75aaf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75ab4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x75ab9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription Microsoft.Crm.Metadata.AttributeService::GetParentEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, string[] columnNames, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x75abe  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_DataProviderId()
0x75ac3  stloc.s  0x10
0x75ac5  ldloca.s 0x10
0x75ac7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x75acc  stloc.s  8
0x75ace  ldloc.s  7
0x75ad0  ldarg.0
0x75ad1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75ad6  ldarg.0
0x75ad7  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75adc  call     void Microsoft.Crm.Metadata.AttributeService::FixAttributePropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x75ae1  ldarg.0
0x75ae2  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75ae7  ldloc.s  7
0x75ae9  ldc.i4.1
0x75aea  ldarg.0
0x75aeb  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75af0  ldarg.0
0x75af1  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75af6  ldarg.0
0x75af7  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption <>c__DisplayClass78_0::modifierOption
0x75afc  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetModifierForChildAttribute(class Microsoft.Crm.Metadata.AttributeInfo attribute, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper mh, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifier)
0x75b01  ldloc.s  8
0x75b03  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption, bool)
0x75b08  ldnull
0x75b09  stloc.s  9
0x75b0b  ldnull
0x75b0c  stloc.s  0xA
0x75b0e  ldarg.0
0x75b0f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass78_0::attributeId
0x75b14  ldarg.0
0x75b15  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75b1a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x75b1f  ldloca.s 9
0x75b21  ldloca.s 0xA
0x75b23  ldc.i4.1
0x75b24  call     void Microsoft.Crm.Metadata.AttributeService::GetExistingAttributeDisplayInformation(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection& displayNames, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection& descriptions, bool retrieveDeletedLabels)
0x75b29  ldarg.0
0x75b2a  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75b2f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75b34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x75b39  ldc.i4.2
0x75b3a  ldarg.0
0x75b3b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75b40  call     bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ShouldUseActiveContext(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x75b45  brtrue.s loc_75B4F
0x75b47  ldarg.0
0x75b48  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption <>c__DisplayClass78_0::modifierOption
0x75b4d  br.s     loc_75B50
0x75b4f  ldc.i4.1
0x75b50  stloc.s  0xB
0x75b52  ldarg.0
0x75b53  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75b58  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.AttributeInfo::get_Description()
0x75b5d  ldarg.0
0x75b5e  ldfld    class Microsoft.Crm.Metadata.AttributeInfo <>c__DisplayClass78_0::attributeInfo
0x75b63  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x75b68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x75b6d  ldstr    aDescription// "Description"
0x75b72  ldloc.s  0xA
0x75b74  ldarg.0
0x75b75  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass78_0::metadataHelper
0x75b7a  ldc.i4.1
0x75b7b  ldarg.0
0x75b7c  ldfld    bool <>c__DisplayClass78_0::mergeLabels
0x75b81  ldloc.s  0xB
0x75b83  ldarg.0
0x75b84  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass78_0::context
0x75b89  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x75b8e  ldc.i4.1
0x75b8f  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.LocalizedLabel::UpdateDisplayInformation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, bool)
  ... truncated ...
```
