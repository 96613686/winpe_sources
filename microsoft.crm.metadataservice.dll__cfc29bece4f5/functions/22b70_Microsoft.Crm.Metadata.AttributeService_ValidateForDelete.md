# Microsoft.Crm.Metadata.AttributeService::ValidateForDelete

- ea: `0x22b70`
- end: `0x22f70`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateForDelete`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1b070`

## callees

- `0x22b70`
- `0x22f70`

## string_xrefs

- `0x22c9e`: `Cannot delete attribute: {0} from Entity: {1} since the attribute is not a custom field`
- `0x22d04`: `Cannot delete logical/child attribute: {0} from Entity: {1}`
- `0x22d5b`: `Cannot delete Primary UI Attribute: {0} from Entity: {1}`
- `0x22da3`: `Cannot delete attribute: {0} from Entity: {1}`
- `0x22e05`: `Cannot Delete attribute: {0} from Entity: {1}. It is used in a published workflow.`

## pseudocode

```c

```

## disassembly

```asm
0x22b70  ldarg.1
0x22b71  stloc.0
0x22b72  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x22b77  ldarg.1
0x22b78  ldstr    aAttribute// "Attribute"
0x22b7d  ldc.i4.s 0xA
0x22b7f  newarr   [mscorlib]System.String
0x22b84  dup
0x22b85  ldc.i4.0
0x22b86  ldstr    aEntityid// "entityid"
0x22b8b  stelem.ref
0x22b8c  dup
0x22b8d  ldc.i4.1
0x22b8e  ldstr    aIscustomfield// "iscustomfield"
0x22b93  stelem.ref
0x22b94  dup
0x22b95  ldc.i4.2
0x22b96  ldstr    aName// "name"
0x22b9b  stelem.ref
0x22b9c  dup
0x22b9d  ldc.i4.3
0x22b9e  ldstr    aIslogical// "islogical"
0x22ba3  stelem.ref
0x22ba4  dup
0x22ba5  ldc.i4.4
0x22ba6  ldstr    aDisplaymask// "displaymask"
0x22bab  stelem.ref
0x22bac  dup
0x22bad  ldc.i4.5
0x22bae  ldstr    aIsbasecurrency// "isbasecurrency"
0x22bb3  stelem.ref
0x22bb4  dup
0x22bb5  ldc.i4.6
0x22bb6  ldstr    aAttributeof// "attributeof"
0x22bbb  stelem.ref
0x22bbc  dup
0x22bbd  ldc.i4.7
0x22bbe  ldstr    aAttributetypei// "attributetypeid"
0x22bc3  stelem.ref
0x22bc4  dup
0x22bc5  ldc.i4.8
0x22bc6  ldstr    aAttributelogic// "attributelogicaltypeid"
0x22bcb  stelem.ref
0x22bcc  dup
0x22bcd  ldc.i4.s 9
0x22bcf  ldstr    aCalculationof// "calculationof"
0x22bd4  stelem.ref
0x22bd5  ldarg.2
0x22bd6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22bdb  stloc.1
0x22bdc  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x22be1  ldloc.1
0x22be2  ldstr    aEntityid// "entityid"
0x22be7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22bec  unbox.any [mscorlib]System.Guid
0x22bf1  ldstr    aEntity_0// "Entity"
0x22bf6  ldc.i4.3
0x22bf7  newarr   [mscorlib]System.String
0x22bfc  dup
0x22bfd  ldc.i4.0
0x22bfe  ldstr    aName// "name"
0x22c03  stelem.ref
0x22c04  dup
0x22c05  ldc.i4.1
0x22c06  ldstr    aLogicalname// "logicalname"
0x22c0b  stelem.ref
0x22c0c  dup
0x22c0d  ldc.i4.2
0x22c0e  ldstr    aIsactivitypart// "isactivityparty"
0x22c13  stelem.ref
0x22c14  ldarg.2
0x22c15  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22c1a  stloc.2
0x22c1b  ldloc.2
0x22c1c  ldstr    aName// "name"
0x22c21  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22c26  castclass [mscorlib]System.String
0x22c2b  stloc.3
0x22c2c  ldloc.1
0x22c2d  ldstr    aName// "name"
0x22c32  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22c37  castclass [mscorlib]System.String
0x22c3c  stloc.s  4
0x22c3e  ldloc.2
0x22c3f  ldstr    aLogicalname// "logicalname"
0x22c44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22c49  castclass [mscorlib]System.String
0x22c4e  stloc.s  5
0x22c50  ldloc.1
0x22c51  ldstr    aIscustomfield// "iscustomfield"
0x22c56  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22c5b  unbox.any [mscorlib]System.Boolean
0x22c60  brtrue.s loc_22CC2
0x22c62  ldarg.2
0x22c63  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x22c68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x22c6d  ldarg.2
0x22c6e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x22c73  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x22c78  call     bool [Microsoft.Crm.Core]Microsoft.Crm.OptInSolutionHelper::IsOptInSolutionUninstall(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext)
0x22c7d  brtrue.s loc_22CC2
0x22c7f  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x22c84  brtrue.s loc_22CC2
0x22c86  ldarg.2
0x22c87  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x22c8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x22c91  ldarg.2
0x22c92  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22c97  brtrue.s loc_22CC2
0x22c99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22c9e  ldstr    aCannotDeleteAt// "Cannot delete attribute: {0} from Entit"...
0x22ca3  ldc.i4.2
0x22ca4  newarr   [mscorlib]System.Object
0x22ca9  dup
0x22caa  ldc.i4.0
0x22cab  ldloc.s  4
0x22cad  stelem.ref
0x22cae  dup
0x22caf  ldc.i4.1
0x22cb0  ldloc.3
0x22cb1  stelem.ref
0x22cb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22cb7  ldc.i4   0x80047009
0x22cbc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22cc1  throw
0x22cc2  ldloc.1
0x22cc3  ldstr    aIslogical// "islogical"
0x22cc8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22ccd  unbox.any [mscorlib]System.Boolean
0x22cd2  brfalse.s loc_22D39
0x22cd4  ldloc.1
0x22cd5  ldstr    aAttributetypei// "attributetypeid"
0x22cda  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22cdf  unbox.any [mscorlib]System.Guid
0x22ce4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x22ce9  ldstr    aImage// "image"
0x22cee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x22cf3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x22cf8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x22cfd  brfalse.s loc_22D28
0x22cff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22d04  ldstr    aCannotDeleteLo// "Cannot delete logical/child attribute: "...
0x22d09  ldc.i4.2
0x22d0a  newarr   [mscorlib]System.Object
0x22d0f  dup
0x22d10  ldc.i4.0
0x22d11  ldloc.s  4
0x22d13  stelem.ref
0x22d14  dup
0x22d15  ldc.i4.1
0x22d16  ldloc.3
0x22d17  stelem.ref
0x22d18  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22d1d  ldc.i4   0x80047016
0x22d22  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22d27  throw
0x22d28  ldloc.1
0x22d29  ldstr    aAttributeof// "attributeof"
0x22d2e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22d33  unbox.any [mscorlib]System.Guid
0x22d38  stloc.0
0x22d39  ldloc.1
0x22d3a  ldstr    aDisplaymask// "displaymask"
0x22d3f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22d44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22d49  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x22d4e  ldc.i4   0x100
0x22d53  and
0x22d54  brfalse.s loc_22D7F
0x22d56  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22d5b  ldstr    aCannotDeletePr// "Cannot delete Primary UI Attribute: {0}"...
0x22d60  ldc.i4.2
0x22d61  newarr   [mscorlib]System.Object
0x22d66  dup
0x22d67  ldc.i4.0
0x22d68  ldloc.s  4
0x22d6a  stelem.ref
0x22d6b  dup
0x22d6c  ldc.i4.1
0x22d6d  ldloc.3
0x22d6e  stelem.ref
0x22d6f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22d74  ldc.i4   0x80047002
0x22d79  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22d7e  throw
0x22d7f  ldloc.1
0x22d80  ldstr    aIsbasecurrency// "isbasecurrency"
0x22d85  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22d8a  brfalse.s loc_22DC7
0x22d8c  ldloc.1
0x22d8d  ldstr    aIsbasecurrency// "isbasecurrency"
0x22d92  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22d97  unbox.any [mscorlib]System.Boolean
0x22d9c  brfalse.s loc_22DC7
0x22d9e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22da3  ldstr    aCannotDeleteAt_0// "Cannot delete attribute: {0} from Entit"...
0x22da8  ldc.i4.2
0x22da9  newarr   [mscorlib]System.Object
0x22dae  dup
0x22daf  ldc.i4.0
0x22db0  ldloc.s  4
0x22db2  stelem.ref
0x22db3  dup
0x22db4  ldc.i4.1
0x22db5  ldloc.3
0x22db6  stelem.ref
0x22db7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22dbc  ldc.i4   0x80048CFE
0x22dc1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22dc6  throw
0x22dc7  ldloc.1
0x22dc8  ldarg.2
0x22dc9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Metadata.AttributeService::GetRollupFieldForAccessoryAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x22dce  stloc.s  6
0x22dd0  ldloc.s  6
0x22dd2  brfalse.s loc_22DEF
0x22dd4  ldc.i4   0x80060541
0x22dd9  ldc.i4.1
0x22dda  newarr   [mscorlib]System.Object
0x22ddf  dup
0x22de0  ldc.i4.0
0x22de1  ldloc.s  6
0x22de3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x22de8  stelem.ref
0x22de9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x22dee  throw
0x22def  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x22df4  ldloc.s  4
0x22df6  ldloc.s  5
0x22df8  ldarg.2
0x22df9  callvirt instance bool class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::IsAttributeUsedInWorkflows(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22dfe  brfalse.s loc_22E29
0x22e00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22e05  ldstr    aCannotDeleteAt_1// "Cannot Delete attribute: {0} from Entit"...
0x22e0a  ldc.i4.2
0x22e0b  newarr   [mscorlib]System.Object
0x22e10  dup
0x22e11  ldc.i4.0
0x22e12  ldloc.s  4
0x22e14  stelem.ref
0x22e15  dup
0x22e16  ldc.i4.1
0x22e17  ldloc.3
0x22e18  stelem.ref
0x22e19  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22e1e  ldc.i4   0x80045030
0x22e23  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22e28  throw
0x22e29  ldloc.2
0x22e2a  ldstr    aIsactivitypart// "isactivityparty"
0x22e2f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22e34  unbox.any [mscorlib]System.Boolean
0x22e39  brfalse  loc_22F16
0x22e3e  ldloc.s  5
0x22e40  call     bool [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::IsEntityListedForEmailDisabled(string)
0x22e45  brtrue   loc_22F16
0x22e4a  ldloc.1
0x22e4b  ldstr    aAttributelogic// "attributelogicaltypeid"
0x22e50  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22e55  castclass [mscorlib]System.String
0x22e5a  ldstr    aEmail// "email"
0x22e5f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x22e64  brtrue   loc_22F16
0x22e69  ldstr    aAttribute// "Attribute"
0x22e6e  ldarg.2
0x22e6f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22e74  stloc.s  7
0x22e76  ldloc.s  7
0x22e78  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x22e7d  ldstr    aAttributeid// "attributeid"
0x22e82  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x22e87  ldloc.s  7
0x22e89  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x22e8e  ldstr    aEntityid// "entityid"
0x22e93  ldc.i4.1
0x22e94  newarr   [mscorlib]System.Guid
0x22e99  dup
0x22e9a  ldc.i4.0
0x22e9b  ldloc.1
0x22e9c  ldstr    aEntityid// "entityid"
0x22ea1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22ea6  unbox.any [mscorlib]System.Guid
0x22eab  stelem   [mscorlib]System.Guid
0x22eb0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x22eb5  ldloc.s  7
0x22eb7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x22ebc  ldstr    aAttributelogic// "attributelogicaltypeid"
0x22ec1  ldc.i4.1
0x22ec2  newarr   [mscorlib]System.String
0x22ec7  dup
0x22ec8  ldc.i4.0
0x22ec9  ldstr    aEmail// "email"
0x22ece  stelem.ref
0x22ecf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x22ed4  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x22ed9  ldloc.s  7
0x22edb  ldarg.2
0x22edc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22ee1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x22ee6  ldc.i4.1
  ... truncated ...
```
