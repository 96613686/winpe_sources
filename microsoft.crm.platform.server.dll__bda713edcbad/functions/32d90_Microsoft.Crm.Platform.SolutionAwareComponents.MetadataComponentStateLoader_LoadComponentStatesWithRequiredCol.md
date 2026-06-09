# Microsoft.Crm.Platform.SolutionAwareComponents.MetadataComponentStateLoader::LoadComponentStatesWithRequiredColumns

- ea: `0x32d90`
- end: `0x32fa9`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.MetadataComponentStateLoader::LoadComponentStatesWithRequiredColumns`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x32d50`

## callees

- `0x2f90`
- `0x3280`
- `0x32d90`
- `0x35b70`
- `0x35b90`
- `0x35bb0`
- `0x35bd0`
- `0x35bf0`
- `0x36060`
- `0x36340`
- `0x45fe0`
- `0x46250`
- `0x464b0`
- `0x46530`
- `0x46620`
- `0x46630`
- `0x46640`
- `0x467f0`

## string_xrefs

- `0x32d96`: `componentstate`
- `0x32e6c`: `componentstate`
- `0x32eab`: `componentstate`
- `0x32eb8`: `componentstate`
- `0x32f41`: `componentstate`
- `0x32f50`: `componentstate`
- `0x32db6`: `overwritetime`
- `0x32e5b`: `overwritetime`
- `0x32f17`: `overwritetime`
- `0x32f26`: `overwritetime`

## pseudocode

```c

```

## disassembly

```asm
0x32d90  ldarg.3
0x32d91  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32d96  ldstr    aComponentstate// "componentstate"
0x32d9b  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32da0  ldarg.3
0x32da1  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32da6  ldstr    aSolutionid_0// "solutionid"
0x32dab  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32db0  ldarg.3
0x32db1  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32db6  ldstr    aOverwritetime_0// "overwritetime"
0x32dbb  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32dc0  ldarg.3
0x32dc1  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32dc6  ldstr    aSupportingsolu// "supportingsolutionid"
0x32dcb  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32dd0  ldc.i4.7
0x32dd1  ldarg.1
0x32dd2  bne.un.s loc_32DF4
0x32dd4  ldarg.3
0x32dd5  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32dda  ldstr    aLabeltypecode// "labeltypecode"
0x32ddf  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32de4  ldarg.3
0x32de5  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32dea  ldstr    aObjectid// "objectid"
0x32def  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32df4  ldarg.1
0x32df5  call     class Microsoft.Crm.Dependency.ComponentDefinition Microsoft.Crm.Dependency.ComponentDefinitionFactory::Create(int32 componentType)
0x32dfa  stloc.0
0x32dfb  ldloc.0
0x32dfc  callvirt instance string Microsoft.Crm.Dependency.ComponentDefinition::get_GroupParentComponentAttributeName()
0x32e01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32e06  brtrue.s loc_32E19
0x32e08  ldarg.3
0x32e09  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32e0e  ldloc.0
0x32e0f  callvirt instance string Microsoft.Crm.Dependency.ComponentDefinition::get_GroupParentComponentAttributeName()
0x32e14  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32e19  ldarg.3
0x32e1a  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x32e1f  ldarg.3
0x32e20  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleBasicQueryExpression::get_MetadataEntity()
0x32e25  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x32e2a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x32e2f  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string attributeName)
0x32e34  ldarg.3
0x32e35  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x32e3a  ldarg.3
0x32e3b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleBasicQueryExpression::get_MetadataEntity()
0x32e40  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x32e45  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x32e4a  ldarg.2
0x32e4b  box      [mscorlib]System.Guid
0x32e50  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x32e55  ldarg.3
0x32e56  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Orders()
0x32e5b  ldstr    aOverwritetime_0// "overwritetime"
0x32e60  ldc.i4.0
0x32e61  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection::AddOrder(string attributeName, valuetype Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderOperator orderOperator)
0x32e66  ldarg.3
0x32e67  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Orders()
0x32e6c  ldstr    aComponentstate// "componentstate"
0x32e71  ldc.i4.0
0x32e72  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection::AddOrder(string attributeName, valuetype Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderOperator orderOperator)
0x32e77  ldarg.3
0x32e78  ldarg.s  4
0x32e7a  ldc.i4.0
0x32e7b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataQueryLibrary::RetrieveMultiple(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget)
0x32e80  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::.ctor()
0x32e85  stloc.1
0x32e86  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x32e8b  stloc.2
0x32e8c  br       loc_32F90
0x32e91  ldloc.2
0x32e92  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x32e97  stloc.3
0x32e98  ldloc.3
0x32e99  ldstr    aSolutionid_0// "solutionid"
0x32e9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x32ea3  unbox.any [mscorlib]System.Guid
0x32ea8  stloc.s  4
0x32eaa  ldloc.3
0x32eab  ldstr    aComponentstate// "componentstate"
0x32eb0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x32eb5  brtrue.s loc_32EC9
0x32eb7  ldloc.3
0x32eb8  ldstr    aComponentstate// "componentstate"
0x32ebd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x32ec2  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x32ec7  br.s     loc_32ECA
0x32ec9  ldc.i4.0
0x32eca  stloc.s  5
0x32ecc  ldloc.3
0x32ecd  ldarg.0
0x32ece  ldloc.s  4
0x32ed0  ldloc.s  5
0x32ed2  ldloc.3
0x32ed3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x32ed8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IsPublishable()
0x32edd  ldarg.s  4
0x32edf  call     instance valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateLoader::GetComponentRowState(valuetype [mscorlib]System.Guid solutionId, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState componentState, bool isPublishable, class [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext context)
0x32ee4  newobj   instance void Microsoft.Crm.Platform.SolutionAwareComponents.MetadataBusinessComponentInstance::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, valuetype Microsoft.Crm.Platform.ComponentStateNames instanceType)
0x32ee9  stloc.s  6
0x32eeb  ldloc.s  6
0x32eed  ldloc.s  4
0x32eef  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_SolutionId(valuetype [mscorlib]System.Guid value)
0x32ef4  ldloc.s  6
0x32ef6  ldloc.3
0x32ef7  ldloc.3
0x32ef8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x32efd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RowIdAttribute()
0x32f02  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x32f07  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x32f0c  unbox.any [mscorlib]System.Guid
0x32f11  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_RowGuidId(valuetype [mscorlib]System.Guid value)
0x32f16  ldloc.3
0x32f17  ldstr    aOverwritetime_0// "overwritetime"
0x32f1c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x32f21  brtrue.s loc_32F40
0x32f23  ldloc.s  6
0x32f25  ldloc.3
0x32f26  ldstr    aOverwritetime_0// "overwritetime"
0x32f2b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x32f30  unbox.any [mscorlib]System.DateTime
0x32f35  ldc.i4.1
0x32f36  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x32f3b  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_OverwriteTime(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime value)
0x32f40  ldloc.3
0x32f41  ldstr    aComponentstate// "componentstate"
0x32f46  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x32f4b  brtrue.s loc_32F64
0x32f4d  ldloc.s  6
0x32f4f  ldloc.3
0x32f50  ldstr    aComponentstate// "componentstate"
0x32f55  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x32f5a  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x32f5f  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_ComponentState(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState value)
0x32f64  ldloc.3
0x32f65  ldstr    aSupportingsolu// "supportingsolutionid"
0x32f6a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x32f6f  brtrue.s loc_32F88
0x32f71  ldloc.s  6
0x32f73  ldloc.3
0x32f74  ldstr    aSupportingsolu// "supportingsolutionid"
0x32f79  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x32f7e  unbox.any [mscorlib]System.Guid
0x32f83  callvirt instance void Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::set_SupportingSolutionId(valuetype [mscorlib]System.Guid value)
0x32f88  ldloc.1
0x32f89  ldloc.s  6
0x32f8b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::Add(var<u1>)
0x32f90  ldloc.2
0x32f91  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32f96  brtrue   loc_32E91
0x32f9b  leave.s  loc_32FA7
0x32f9d  ldloc.2
0x32f9e  brfalse.s loc_32FA6
0x32fa0  ldloc.2
0x32fa1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32fa6  endfinally
0x32fa7  ldloc.1
0x32fa8  ret
```
