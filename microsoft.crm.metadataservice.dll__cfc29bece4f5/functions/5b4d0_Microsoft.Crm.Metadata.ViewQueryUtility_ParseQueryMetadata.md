# Microsoft.Crm.Metadata.ViewQueryUtility::ParseQueryMetadata

- ea: `0x5b4d0`
- end: `0x5ba1c`
- name: `Microsoft.Crm.Metadata.ViewQueryUtility::ParseQueryMetadata`
- size: `1356`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0xffd0`
- `0xfff0`

## callees

- `0x5b4d0`
- `0x5ba20`
- `0x5bad0`
- `0x5bf50`
- `0x5c400`
- `0x77f30`
- `0x77f80`

## string_xrefs

- `0x5b52a`: `componentstate`
- `0x5b563`: `fetchxml`
- `0x5b57e`: `layoutxml`
- `0x5b673`: `dependentcomponentobjectid`
- `0x5b69f`: `requiredcomponentobjectid`
- `0x5b6e6`: `requiredcomponentobjectid`
- `0x5b6a7`: `requiredcomponenttype`
- `0x5b6f8`: `requiredcomponenttype`
- `0x5b6af`: `requiredcomponentparentid`
- `0x5b709`: `requiredcomponentparentid`

## pseudocode

```c

```

## disassembly

```asm
0x5b4d0  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::.ctor()
0x5b4d5  stloc.0
0x5b4d6  ldloc.0
0x5b4d7  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b4dc  ldarga.s 1
0x5b4de  constrained. [mscorlib]System.Guid
0x5b4e4  callvirt instance string [mscorlib]System.Object::ToString()
0x5b4e9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_QueryId(string)
0x5b4ee  ldarg.0
0x5b4ef  ldstr    aReturnedtypeco// "returnedtypecode"
0x5b4f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b4f9  unbox.any [mscorlib]System.Int32
0x5b4fe  stloc.1
0x5b4ff  ldloc.0
0x5b500  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b505  ldarg.2
0x5b506  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b50b  ldloc.1
0x5b50c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x5b511  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5b516  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_ReturnedTypeCode(string)
0x5b51b  ldloc.0
0x5b51c  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b521  ldarg.0
0x5b522  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.UserQuery
0x5b527  brtrue.s loc_5B53B
0x5b529  ldarg.0
0x5b52a  ldstr    aComponentstate// "componentstate"
0x5b52f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b534  unbox.any [mscorlib]System.Int32
0x5b539  br.s     loc_5B53C
0x5b53b  ldc.i4.0
0x5b53c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_ComponentState(int32)
0x5b541  ldloc.0
0x5b542  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b547  ldarg.0
0x5b548  ldstr    aDescription_0// "description"
0x5b54d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b552  castclass [mscorlib]System.String
0x5b557  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_Description(string)
0x5b55c  ldloc.0
0x5b55d  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b562  ldarg.0
0x5b563  ldstr    aFetchxml// "fetchxml"
0x5b568  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b56d  castclass [mscorlib]System.String
0x5b572  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_FetchXml(string)
0x5b577  ldloc.0
0x5b578  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b57d  ldarg.0
0x5b57e  ldstr    aLayoutxml_0// "layoutxml"
0x5b583  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b588  castclass [mscorlib]System.String
0x5b58d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_LayoutXml(string)
0x5b592  ldloc.0
0x5b593  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b598  ldarg.0
0x5b599  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.UserQuery
0x5b59e  brtrue.s loc_5B5B2
0x5b5a0  ldarg.0
0x5b5a1  ldstr    aIsdefault// "isdefault"
0x5b5a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b5ab  unbox.any [mscorlib]System.Boolean
0x5b5b0  br.s     loc_5B5B3
0x5b5b2  ldc.i4.0
0x5b5b3  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_IsDefault(bool)
0x5b5b8  ldloc.0
0x5b5b9  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b5be  ldarg.0
0x5b5bf  ldstr    aModifiedon// "modifiedon"
0x5b5c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b5c9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x5b5ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_Value()
0x5b5d3  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_ModifiedOn(string)
0x5b5d8  ldloc.0
0x5b5d9  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b5de  ldarg.0
0x5b5df  ldstr    aName// "name"
0x5b5e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b5e9  castclass [mscorlib]System.String
0x5b5ee  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_Name(string)
0x5b5f3  ldloc.0
0x5b5f4  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b5f9  ldarg.0
0x5b5fa  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.UserQuery
0x5b5ff  brtrue.s loc_5B613
0x5b601  ldarg.0
0x5b602  ldstr    aQueryapi// "queryapi"
0x5b607  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b60c  castclass [mscorlib]System.String
0x5b611  br.s     loc_5B614
0x5b613  ldnull
0x5b614  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_QueryApi(string)
0x5b619  ldloc.0
0x5b61a  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b61f  ldarg.0
0x5b620  ldstr    aQuerytype// "querytype"
0x5b625  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b62a  unbox.any [mscorlib]System.Int32
0x5b62f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_QueryType(int32)
0x5b634  ldloc.0
0x5b635  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_QueryMetadata()
0x5b63a  ldarg.0
0x5b63b  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.UserQuery
0x5b640  brtrue.s loc_5B654
0x5b642  ldarg.0
0x5b643  ldstr    aIscustomizable// "iscustomizable"
0x5b648  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b64d  unbox.any [mscorlib]System.Boolean
0x5b652  br.s     loc_5B655
0x5b654  ldc.i4.1
0x5b655  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryMetadata::set_IsCustomizable(bool)
0x5b65a  ldstr    aDependency// "Dependency"
0x5b65f  ldarg.2
0x5b660  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5b665  stloc.2
0x5b666  ldstr    aDependency// "Dependency"
0x5b66b  ldarg.2
0x5b66c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b671  stloc.3
0x5b672  ldloc.3
0x5b673  ldstr    aDependentcompo_1// "dependentcomponentobjectid"
0x5b678  ldc.i4.0
0x5b679  ldarg.1
0x5b67a  box      [mscorlib]System.Guid
0x5b67f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5b684  pop
0x5b685  ldloc.2
0x5b686  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5b68b  ldloc.3
0x5b68c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x5b691  ldloc.2
0x5b692  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5b697  ldc.i4.3
0x5b698  newarr   [mscorlib]System.String
0x5b69d  dup
0x5b69e  ldc.i4.0
0x5b69f  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x5b6a4  stelem.ref
0x5b6a5  dup
0x5b6a6  ldc.i4.1
0x5b6a7  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x5b6ac  stelem.ref
0x5b6ad  dup
0x5b6ae  ldc.i4.2
0x5b6af  ldstr    aRequiredcompon_1// "requiredcomponentparentid"
0x5b6b4  stelem.ref
0x5b6b5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x5b6ba  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x5b6bf  ldloc.2
0x5b6c0  ldarg.2
0x5b6c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b6c6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x5b6cb  stloc.s  4
0x5b6cd  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5b6d2  stloc.s  5
0x5b6d4  br       loc_5B784
0x5b6d9  ldloc.s  5
0x5b6db  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b6e0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5b6e5  dup
0x5b6e6  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x5b6eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x5b6f0  unbox.any [mscorlib]System.Guid
0x5b6f5  stloc.s  6
0x5b6f7  dup
0x5b6f8  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x5b6fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x5b702  unbox.any [mscorlib]System.Int32
0x5b707  stloc.s  7
0x5b709  ldstr    aRequiredcompon_1// "requiredcomponentparentid"
0x5b70e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x5b713  unbox.any [mscorlib]System.Guid
0x5b718  stloc.s  8
0x5b71a  ldloc.s  7
0x5b71c  ldc.i4.2
0x5b71d  bne.un.s loc_5B766
0x5b71f  ldloc.s  4
0x5b721  ldloc.s  8
0x5b723  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x5b728  brfalse.s loc_5B74E
0x5b72a  ldloc.s  4
0x5b72c  ldloc.s  8
0x5b72e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x5b733  ldloc.s  6
0x5b735  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5b73a  brtrue.s loc_5B784
0x5b73c  ldloc.s  4
0x5b73e  ldloc.s  8
0x5b740  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x5b745  ldloc.s  6
0x5b747  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5b74c  br.s     loc_5B784
0x5b74e  ldloc.s  4
0x5b750  ldloc.s  8
0x5b752  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x5b757  dup
0x5b758  ldloc.s  6
0x5b75a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5b75f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x5b764  br.s     loc_5B784
0x5b766  ldloc.s  7
0x5b768  ldc.i4.1
0x5b769  bne.un.s loc_5B784
0x5b76b  ldloc.s  4
0x5b76d  ldloc.s  6
0x5b76f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x5b774  brtrue.s loc_5B784
0x5b776  ldloc.s  4
0x5b778  ldloc.s  6
0x5b77a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x5b77f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x5b784  ldloc.s  5
0x5b786  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5b78b  brtrue   loc_5B6D9
0x5b790  leave.s  loc_5B7A7
0x5b792  ldloc.s  5
0x5b794  isinst   [mscorlib]System.IDisposable
0x5b799  stloc.s  9
0x5b79b  ldloc.s  9
0x5b79d  brfalse.s loc_5B7A6
0x5b79f  ldloc.s  9
0x5b7a1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b7a6  endfinally
0x5b7a7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x5b7ac  pop
0x5b7ad  ldloc.s  4
0x5b7af  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Keys()
0x5b7b4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::GetEnumerator()
0x5b7b9  stloc.s  0xA
0x5b7bb  br       loc_5B9B1
0x5b7c0  ldloca.s 0xA
0x5b7c2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Current()
0x5b7c7  stloc.s  0xB
0x5b7c9  ldarg.2
0x5b7ca  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b7cf  ldloc.s  0xB
0x5b7d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x5b7d6  stloc.s  0xC
0x5b7d8  ldloc.s  0xC
0x5b7da  ldarg.2
0x5b7db  call     class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentEntityMetadata Microsoft.Crm.Metadata.ViewQueryUtility::ConvertEntityMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b7e0  stloc.s  0xD
0x5b7e2  ldloc.s  4
0x5b7e4  ldloc.s  0xB
0x5b7e6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x5b7eb  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x5b7f0  stloc.s  0xE
0x5b7f2  br       loc_5B966
0x5b7f7  ldloca.s 0xE
0x5b7f9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x5b7fe  stloc.s  0xF
0x5b800  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x5b805  stloc.s  0x10
0x5b807  ldloc.s  0x10
0x5b809  ldloc.s  0xC
0x5b80b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x5b810  ldloc.s  0xF
0x5b812  box      [mscorlib]System.Guid
0x5b817  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x5b81c  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata <>c__DisplayClass2_0::attribute
0x5b821  ldloc.s  0xC
0x5b823  ldloc.s  0x10
0x5b825  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata <>c__DisplayClass2_0::attribute
0x5b82a  ldloc.0
0x5b82b  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentEntityMetadataCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryWithEntityMetadata::get_DependantEntitiesCollection()
0x5b830  ldarg.2
0x5b831  call     class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentAttributeMetadata Microsoft.Crm.Metadata.ViewQueryUtility::ParseDependentAttributeMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentEntityMetadataCollection entityCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b836  stloc.s  0x11
0x5b838  ldloc.s  0xD
0x5b83a  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentAttributeMetadataCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentEntityMetadata::get_Attributes()
0x5b83f  ldloc.s  0x11
0x5b841  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentAttributeMetadataCollection::Add(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DependentAttributeMetadata)
0x5b846  ldloc.s  0x10
0x5b848  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata <>c__DisplayClass2_0::attribute
0x5b84d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x5b852  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x5b857  ldc.i4.7
0x5b858  bne.un   loc_5B966
0x5b85d  ldloc.s  0xC
0x5b85f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesFrom()
0x5b864  ldloc.s  0x10
0x5b866  ldftn    instance bool <>c__DisplayClass2_0::<ParseQueryMetadata>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship relationship)
0x5b86c  newobj   instance void RelationFilterDelegate::.ctor(object object, native int method)
0x5b871  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship> Microsoft.Crm.Metadata.ViewQueryUtility::Filter(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection relationshipCollection, class RelationFilterDelegate filterFunction)
0x5b876  call     T0x2B000022
0x5b87b  stloc.s  0x12
0x5b87d  ldloc.s  0x12
0x5b87f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Count()
0x5b884  ldc.i4.0
0x5b885  ble      loc_5B966
0x5b88a  ldloc.s  0x12
0x5b88c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::GetEnumerator()
0x5b891  stloc.s  0x13
0x5b893  br       loc_5B94A
0x5b898  ldloca.s 0x13
0x5b89a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Current()
0x5b89f  stloc.s  0x14
0x5b8a1  ldarg.2
0x5b8a2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
  ... truncated ...
```
