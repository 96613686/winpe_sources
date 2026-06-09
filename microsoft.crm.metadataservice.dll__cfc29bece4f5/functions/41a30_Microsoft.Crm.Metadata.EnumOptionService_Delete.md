# Microsoft.Crm.Metadata.EnumOptionService::Delete

- ea: `0x41a30`
- end: `0x41d2f`
- name: `Microsoft.Crm.Metadata.EnumOptionService::Delete`
- size: `767`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0xe380`
- `0x35940`
- `0x60740`

## callees

- `0x413e0`
- `0x41a30`
- `0x41d30`
- `0x426c0`
- `0x42b50`
- `0x4bc30`
- `0x5a810`

## string_xrefs

- `0x41b02`: `prvWriteAttribute`
- `0x41ae9`: `prvWriteOptionSet`
- `0x41b9b`: `Option type was already verified in ValidateForDelete().`
- `0x41d0e`: `EnumOptionServce.Delete caught exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x41a30  ldarg.1
0x41a31  ldstr    aAttributepickl_1// "attributePicklistValueId"
0x41a36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x41a3b  ldarg.3
0x41a3c  ldstr    aContext// "context"
0x41a41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x41a46  ldarg.3
0x41a47  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41a4c  pop
0x41a4d  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x41a52  ldarg.1
0x41a53  ldstr    aAttributepickl// "AttributePicklistValue"
0x41a58  ldc.i4.2
0x41a59  newarr   [mscorlib]System.String
0x41a5e  dup
0x41a5f  ldc.i4.0
0x41a60  ldstr    aValue// "value"
0x41a65  stelem.ref
0x41a66  dup
0x41a67  ldc.i4.1
0x41a68  ldstr    aOptionsetid// "optionsetid"
0x41a6d  stelem.ref
0x41a6e  ldarg.3
0x41a6f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41a74  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x41a79  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x41a7e  stloc.0
0x41a7f  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x41a84  ldloc.0
0x41a85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41a8a  ldstr    aOptionset_0// "OptionSet"
0x41a8f  ldc.i4.7
0x41a90  newarr   [mscorlib]System.String
0x41a95  dup
0x41a96  ldc.i4.0
0x41a97  ldstr    aOptionsettype// "optionsettype"
0x41a9c  stelem.ref
0x41a9d  dup
0x41a9e  ldc.i4.1
0x41a9f  ldstr    aIsglobal// "isglobal"
0x41aa4  stelem.ref
0x41aa5  dup
0x41aa6  ldc.i4.2
0x41aa7  ldstr    aIsmanaged// "ismanaged"
0x41aac  stelem.ref
0x41aad  dup
0x41aae  ldc.i4.3
0x41aaf  ldstr    aIscustomizable// "iscustomizable"
0x41ab4  stelem.ref
0x41ab5  dup
0x41ab6  ldc.i4.4
0x41ab7  ldstr    aName// "name"
0x41abc  stelem.ref
0x41abd  dup
0x41abe  ldc.i4.5
0x41abf  ldstr    aOptionsetid// "optionsetid"
0x41ac4  stelem.ref
0x41ac5  dup
0x41ac6  ldc.i4.6
0x41ac7  ldstr    aParentoptionse// "parentoptionsetid"
0x41acc  stelem.ref
0x41acd  ldarg.3
0x41ace  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41ad3  stloc.1
0x41ad4  ldloc.1
0x41ad5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x41ada  stloc.2
0x41adb  ldloc.2
0x41adc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x41ae1  brfalse.s loc_41AFC
0x41ae3  ldarg.3
0x41ae4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41ae9  ldstr    aPrvwriteoption// "prvWriteOptionSet"
0x41aee  ldarg.3
0x41aef  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41af4  ldarg.3
0x41af5  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41afa  br.s     loc_41B68
0x41afc  ldarg.3
0x41afd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41b02  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x41b07  ldarg.3
0x41b08  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41b0d  ldarg.3
0x41b0e  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41b13  ldloc.1
0x41b14  ldarg.3
0x41b15  call     bool Microsoft.Crm.Metadata.EnumOptionService::IsOptionSetCustomizableInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity optionSetData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41b1a  brtrue.s loc_41B68
0x41b1c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41b21  ldstr    aDeletionOfLoca// "Deletion of local OptionSet({0}, Id={1}"...
0x41b26  ldc.i4.2
0x41b27  newarr   [mscorlib]System.Object
0x41b2c  dup
0x41b2d  ldc.i4.0
0x41b2e  ldloc.2
0x41b2f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x41b34  stelem.ref
0x41b35  dup
0x41b36  ldc.i4.1
0x41b37  ldloc.2
0x41b38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x41b3d  box      [mscorlib]System.Guid
0x41b42  stelem.ref
0x41b43  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x41b48  ldarg.3
0x41b49  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41b4e  ldstr    aA65a629c476e11// "a65a629c-476e-11df-82c0-8000600fe800"
0x41b53  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x41b58  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedPropertyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetManagedProperty(valuetype [mscorlib]System.Guid)
0x41b5d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedPropertyMetadata::get_ErrorCode()
0x41b62  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x41b67  throw
0x41b68  ldarg.2
0x41b69  ldloc.2
0x41b6a  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateIsGlobalAgainstExistingOptionSet(bool expectedIsGlobal, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x41b6f  ldarg.3
0x41b70  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x41b75  stloc.3
0x41b76  ldarg.0
0x41b77  ldarg.1
0x41b78  ldarg.3
0x41b79  call     instance void Microsoft.Crm.Metadata.EnumOptionService::ValidateForDelete(valuetype [mscorlib]System.Guid attributePicklistValueId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41b7e  ldloc.2
0x41b7f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x41b84  stloc.s  5
0x41b86  ldloc.s  5
0x41b88  brfalse.s loc_41B91
0x41b8a  ldloc.s  5
0x41b8c  ldc.i4.2
0x41b8d  beq.s    loc_41B96
0x41b8f  br.s     loc_41B9B
0x41b91  ldc.i4.m1
0x41b92  stloc.s  4
0x41b94  br.s     loc_41BAB
0x41b96  ldc.i4.m1
0x41b97  stloc.s  4
0x41b99  br.s     loc_41BAB
0x41b9b  ldstr    aOptionTypeWasA// "Option type was already verified in Val"...
0x41ba0  ldc.i4   0x80040216
0x41ba5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x41baa  throw
0x41bab  ldarg.3
0x41bac  ldc.i4.1
0x41bad  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x41bb2  stloc.s  6
0x41bb4  ldarg.3
0x41bb5  ldarg.3
0x41bb6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x41bbb  ldc.i4.1
0x41bbc  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x41bc1  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x41bc6  stloc.s  7
0x41bc8  ldstr    aAttribute// "Attribute"
0x41bcd  ldarg.3
0x41bce  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41bd3  stloc.s  8
0x41bd5  ldloc.s  8
0x41bd7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x41bdc  ldstr    aAttributeid// "attributeid"
0x41be1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x41be6  ldloc.s  8
0x41be8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x41bed  ldstr    aAppdefaultvalu// "appdefaultvalue"
0x41bf2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x41bf7  ldloc.s  8
0x41bf9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x41bfe  ldstr    aOptionsetid// "optionsetid"
0x41c03  ldc.i4.0
0x41c04  ldc.i4.1
0x41c05  newarr   [mscorlib]System.Guid
0x41c0a  dup
0x41c0b  ldc.i4.0
0x41c0c  ldloc.0
0x41c0d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41c12  stelem   [mscorlib]System.Guid
0x41c17  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x41c1c  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x41c21  ldloc.s  8
0x41c23  ldarg.3
0x41c24  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41c29  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x41c2e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x41c33  stloc.s  0xA
0x41c35  br.s     loc_41C7D
0x41c37  ldloc.s  0xA
0x41c39  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x41c3e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x41c43  stloc.s  0xB
0x41c45  ldloc.0
0x41c46  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_Value()
0x41c4b  ldloc.s  0xB
0x41c4d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AppDefaultValue()
0x41c52  bne.un.s loc_41C7D
0x41c54  ldarg.3
0x41c55  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41c5a  stloc.s  0xC
0x41c5c  ldloc.s  0xC
0x41c5e  ldloc.s  0xB
0x41c60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x41c65  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeId(valuetype [mscorlib]System.Guid)
0x41c6a  ldloc.s  0xC
0x41c6c  ldloc.s  4
0x41c6e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AppDefaultValue(int32)
0x41c73  ldloc.s  7
0x41c75  ldloc.s  0xC
0x41c77  ldc.i4.1
0x41c78  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x41c7d  ldloc.s  0xA
0x41c7f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x41c84  brtrue.s loc_41C37
0x41c86  leave.s  loc_41C94
0x41c88  ldloc.s  0xA
0x41c8a  brfalse.s loc_41C93
0x41c8c  ldloc.s  0xA
0x41c8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41c93  endfinally
0x41c94  ldloc.0
0x41c95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41c9a  ldarg.3
0x41c9b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41ca0  call     void Microsoft.Crm.Metadata.EnumOptionService::UpdateParentOptionSet(valuetype [mscorlib]System.Guid optionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x41ca5  ldarg.3
0x41ca6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41cab  stloc.s  9
0x41cad  ldloc.s  9
0x41caf  ldarg.1
0x41cb0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_AttributePicklistValueId(valuetype [mscorlib]System.Guid)
0x41cb5  ldloc.s  7
0x41cb7  ldloc.s  9
0x41cb9  ldc.i4.2
0x41cba  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x41cbf  ldloc.0
0x41cc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41cc5  ldloc.0
0x41cc6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_Value()
0x41ccb  ldloc.s  7
0x41ccd  ldarg.3
0x41cce  call     void Microsoft.Crm.Metadata.EnumOptionService::RemoveReferencesToParentValue(valuetype [mscorlib]System.Guid parentOptionSetId, int32 parentValue, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41cd3  ldloc.s  7
0x41cd5  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x41cda  ldarg.3
0x41cdb  ldc.i4.4
0x41cdc  ldloc.0
0x41cdd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x41ce2  ldc.i4.s 9
0x41ce4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x41ce9  leave.s  loc_41CF7
0x41ceb  ldloc.s  6
0x41ced  brfalse.s loc_41CF6
0x41cef  ldloc.s  6
0x41cf1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41cf6  endfinally
0x41cf7  ldloc.3
0x41cf8  brfalse.s loc_41D00
0x41cfa  ldarg.3
0x41cfb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x41d00  leave.s  loc_41D2E
0x41d02  stloc.s  0xD
0x41d04  ldloc.s  0xD
0x41d06  ldarg.3
0x41d07  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x41d0c  ldc.i4.s 0x19
0x41d0e  ldstr    aEnumoptionserv_1// "EnumOptionServce.Delete caught exceptio"...
0x41d13  ldc.i4.1
0x41d14  newarr   [mscorlib]System.Object
0x41d19  dup
0x41d1a  ldc.i4.0
0x41d1b  ldloc.s  0xD
0x41d1d  stelem.ref
0x41d1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x41d23  ldloc.3
0x41d24  brfalse.s loc_41D2C
0x41d26  ldarg.3
0x41d27  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x41d2c  rethrow
0x41d2e  ret
```
