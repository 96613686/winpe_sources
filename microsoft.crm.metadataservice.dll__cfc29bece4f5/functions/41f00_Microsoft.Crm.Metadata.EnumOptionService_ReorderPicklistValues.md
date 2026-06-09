# Microsoft.Crm.Metadata.EnumOptionService::ReorderPicklistValues

- ea: `0x41f00`
- end: `0x421fe`
- name: `Microsoft.Crm.Metadata.EnumOptionService::ReorderPicklistValues`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xe7c0`

## callees

- `0x41f00`
- `0x426c0`
- `0x4bc30`
- `0x5a810`

## string_xrefs

- `0x41fa2`: `prvWriteAttribute`
- `0x41f86`: `prvWriteOptionSet`

## pseudocode

```c

```

## disassembly

```asm
0x41f00  ldarg.1
0x41f01  ldstr    aOptionsetid_0// "optionSetId"
0x41f06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x41f0b  ldarg.3
0x41f0c  ldstr    aNeworderofvalu// "newOrderOfValues"
0x41f11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x41f16  ldarg.s  4
0x41f18  ldstr    aContext// "context"
0x41f1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x41f22  ldarg.s  4
0x41f24  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x41f29  pop
0x41f2a  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x41f2f  ldarg.1
0x41f30  ldstr    aOptionset_0// "OptionSet"
0x41f35  ldc.i4.5
0x41f36  newarr   [mscorlib]System.String
0x41f3b  dup
0x41f3c  ldc.i4.0
0x41f3d  ldstr    aName// "name"
0x41f42  stelem.ref
0x41f43  dup
0x41f44  ldc.i4.1
0x41f45  ldstr    aOptionsetid// "optionsetid"
0x41f4a  stelem.ref
0x41f4b  dup
0x41f4c  ldc.i4.2
0x41f4d  ldstr    aIsglobal// "isglobal"
0x41f52  stelem.ref
0x41f53  dup
0x41f54  ldc.i4.3
0x41f55  ldstr    aIscustomizable// "iscustomizable"
0x41f5a  stelem.ref
0x41f5b  dup
0x41f5c  ldc.i4.4
0x41f5d  ldstr    aIsmanaged// "ismanaged"
0x41f62  stelem.ref
0x41f63  ldarg.s  4
0x41f65  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x41f6a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x41f6f  stloc.0
0x41f70  ldloc.0
0x41f71  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x41f76  stloc.1
0x41f77  ldloc.1
0x41f78  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x41f7d  brfalse.s loc_41F9B
0x41f7f  ldarg.s  4
0x41f81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41f86  ldstr    aPrvwriteoption// "prvWriteOptionSet"
0x41f8b  ldarg.s  4
0x41f8d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41f92  ldarg.s  4
0x41f94  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41f99  br.s     loc_41FF0
0x41f9b  ldarg.s  4
0x41f9d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x41fa2  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x41fa7  ldarg.s  4
0x41fa9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41fae  ldarg.s  4
0x41fb0  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x41fb5  ldloc.0
0x41fb6  ldarg.s  4
0x41fb8  call     bool Microsoft.Crm.Metadata.EnumOptionService::IsOptionSetCustomizableInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity optionSetData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x41fbd  brtrue.s loc_41FF0
0x41fbf  ldarg.s  4
0x41fc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x41fc6  ldc.i4.s 0x19
0x41fc8  ldstr    aLocalOptionset_0// "Local OptionSet({0}, Id={1}) is not cus"...
0x41fcd  ldc.i4.2
0x41fce  newarr   [mscorlib]System.Object
0x41fd3  dup
0x41fd4  ldc.i4.0
0x41fd5  ldloc.1
0x41fd6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_Name()
0x41fdb  stelem.ref
0x41fdc  dup
0x41fdd  ldc.i4.1
0x41fde  ldloc.1
0x41fdf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x41fe4  box      [mscorlib]System.Guid
0x41fe9  stelem.ref
0x41fea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x41fef  ret
0x41ff0  ldarg.2
0x41ff1  ldloc.1
0x41ff2  call     void Microsoft.Crm.Metadata.OptionSetService::ValidateIsGlobalAgainstExistingOptionSet(bool expectedIsGlobal, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag existingOptionSetDescription)
0x41ff7  ldarg.s  4
0x41ff9  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x41ffe  stloc.2
0x41fff  ldstr    aAttributepickl// "AttributePicklistValue"
0x42004  ldarg.s  4
0x42006  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4200b  stloc.3
0x4200c  ldloc.3
0x4200d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x42012  ldc.i4.3
0x42013  newarr   [mscorlib]System.String
0x42018  dup
0x42019  ldc.i4.0
0x4201a  ldstr    aDisplayorder// "displayorder"
0x4201f  stelem.ref
0x42020  dup
0x42021  ldc.i4.1
0x42022  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x42027  stelem.ref
0x42028  dup
0x42029  ldc.i4.2
0x4202a  ldstr    aValue// "value"
0x4202f  stelem.ref
0x42030  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[])
0x42035  ldloc.3
0x42036  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4203b  ldstr    aOptionsetid// "optionsetid"
0x42040  ldarg.1
0x42041  box      [mscorlib]System.Guid
0x42046  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, object)
0x4204b  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x42050  ldloc.3
0x42051  ldarg.s  4
0x42053  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x42058  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4205d  stloc.s  4
0x4205f  ldarg.3
0x42060  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0x42065  ldloc.s  4
0x42067  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x4206c  beq.s    loc_420B4
0x4206e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42073  ldstr    aThereAre0Exist// "There are {0} existing options for opti"...
0x42078  ldc.i4.3
0x42079  newarr   [mscorlib]System.Object
0x4207e  dup
0x4207f  ldc.i4.0
0x42080  ldloc.s  4
0x42082  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42087  box      [mscorlib]System.Int32
0x4208c  stelem.ref
0x4208d  dup
0x4208e  ldc.i4.1
0x4208f  ldarg.1
0x42090  box      [mscorlib]System.Guid
0x42095  stelem.ref
0x42096  dup
0x42097  ldc.i4.2
0x42098  ldarg.3
0x42099  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0x4209e  box      [mscorlib]System.Int32
0x420a3  stelem.ref
0x420a4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x420a9  ldc.i4   0x80044324
0x420ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x420b3  throw
0x420b4  ldarg.s  4
0x420b6  ldc.i4.1
0x420b7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x420bc  stloc.s  5
0x420be  ldarg.s  4
0x420c0  ldarg.s  4
0x420c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x420c7  ldc.i4.1
0x420c8  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x420cd  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x420d2  stloc.s  6
0x420d4  ldloc.s  4
0x420d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x420db  stloc.s  7
0x420dd  br       loc_42189
0x420e2  ldloc.s  7
0x420e4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x420e9  stloc.s  8
0x420eb  ldloc.s  8
0x420ed  ldstr    aValue// "value"
0x420f2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x420f7  unbox.any [mscorlib]System.Int32
0x420fc  stloc.s  9
0x420fe  ldarg.3
0x420ff  ldloc.s  9
0x42101  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::IndexOf(var<u1>)
0x42106  stloc.s  0xA
0x42108  ldloc.s  0xA
0x4210a  ldc.i4.m1
0x4210b  bne.un.s loc_42140
0x4210d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42112  ldstr    aEnumOptionWith// "Enum option with value {0} for optionSe"...
0x42117  ldc.i4.2
0x42118  newarr   [mscorlib]System.Object
0x4211d  dup
0x4211e  ldc.i4.0
0x4211f  ldloc.s  9
0x42121  box      [mscorlib]System.Int32
0x42126  stelem.ref
0x42127  dup
0x42128  ldc.i4.1
0x42129  ldarg.1
0x4212a  box      [mscorlib]System.Guid
0x4212f  stelem.ref
0x42130  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42135  ldc.i4   0x80044325
0x4213a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x4213f  throw
0x42140  ldloc.s  0xA
0x42142  ldloc.s  8
0x42144  ldstr    aDisplayorder// "displayorder"
0x42149  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4214e  unbox.any [mscorlib]System.Int32
0x42153  beq.s    loc_42189
0x42155  ldarg.s  4
0x42157  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4215c  stloc.s  0xB
0x4215e  ldloc.s  0xB
0x42160  ldloc.s  8
0x42162  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x42167  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4216c  unbox.any [mscorlib]System.Guid
0x42171  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_AttributePicklistValueId(valuetype [mscorlib]System.Guid)
0x42176  ldloc.s  0xB
0x42178  ldloc.s  0xA
0x4217a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_DisplayOrder(int32)
0x4217f  ldloc.s  6
0x42181  ldloc.s  0xB
0x42183  ldc.i4.1
0x42184  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType)
0x42189  ldloc.s  7
0x4218b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x42190  brtrue   loc_420E2
0x42195  leave.s  loc_421A3
0x42197  ldloc.s  7
0x42199  brfalse.s loc_421A2
0x4219b  ldloc.s  7
0x4219d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x421a2  endfinally
0x421a3  ldloc.s  6
0x421a5  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x421aa  ldarg.s  4
0x421ac  ldc.i4.4
0x421ad  ldarg.1
0x421ae  ldc.i4.s 9
0x421b0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x421b5  leave.s  loc_421C3
0x421b7  ldloc.s  5
0x421b9  brfalse.s loc_421C2
0x421bb  ldloc.s  5
0x421bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x421c2  endfinally
0x421c3  ldloc.2
0x421c4  brfalse.s loc_421CD
0x421c6  ldarg.s  4
0x421c8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0x421cd  leave.s  loc_421FD
0x421cf  stloc.s  0xC
0x421d1  ldloc.s  0xC
0x421d3  ldarg.s  4
0x421d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x421da  ldc.i4.s 0x19
0x421dc  ldstr    aEnumoptionserv_2// "EnumOptionServce.ReorderPicklistValues "...
0x421e1  ldc.i4.1
0x421e2  newarr   [mscorlib]System.Object
0x421e7  dup
0x421e8  ldc.i4.0
0x421e9  ldloc.s  0xC
0x421eb  stelem.ref
0x421ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x421f1  ldloc.2
0x421f2  brfalse.s loc_421FB
0x421f4  ldarg.s  4
0x421f6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x421fb  rethrow
0x421fd  ret
```
