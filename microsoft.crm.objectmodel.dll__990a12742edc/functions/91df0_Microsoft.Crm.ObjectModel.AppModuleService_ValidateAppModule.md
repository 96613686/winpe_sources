# Microsoft.Crm.ObjectModel.AppModuleService::ValidateAppModule

- ea: `0x91df0`
- end: `0x9223e`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::ValidateAppModule`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x926d0`

## callees

- `0x19b50`
- `0x8f9b0`
- `0x91df0`
- `0x94a50`
- `0x958c0`
- `0x95d60`
- `0x95ec0`
- `0x95fd0`
- `0x96140`

## string_xrefs

- `0x91f03`: `componenttype`
- `0x91fdf`: `componenttype`
- `0x91eda`: `AppModuleComponent`
- `0x921b1`: `RibbonCommand`
- `0x91ea0`: `AppModuleService.ValidateAppModule(): AppModule with [appmoduleid:{0}] not found, Exception: {0}`
- `0x91f37`: `NoAppModuleComponentReferred`
- `0x91f60`: `AppModuleService.ValidateAppModule(): AppModule with [appmoduleid:{0}], No componenets found.`
- `0x92087`: `AppModuleService.ValidateAppModule():  No sitemap component found for AppModule with [appmoduleid:{0}].`
- `0x92100`: `AppModuleService.ValidateAppModule(): For AppModule with [appmoduleid:{0}] no Entity component found.`

## pseudocode

```c

```

## disassembly

```asm
0x91df0  ldarg.0
0x91df1  ldarg.2
0x91df2  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91df7  ldarg.1
0x91df8  ldstr    aAppmoduleid// "appmoduleid"
0x91dfd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x91e02  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleValidationResponse::.ctor()
0x91e07  stloc.0
0x91e08  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::.ctor()
0x91e0d  stloc.1
0x91e0e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleEntity>::.ctor()
0x91e13  stloc.2
0x91e14  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x91e19  stloc.3
0x91e1a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [mscorlib]System.Guid>::.ctor()
0x91e1f  stloc.s  4
0x91e21  ldstr    aAppmodule// "AppModule"
0x91e26  ldarg.2
0x91e27  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x91e2c  stloc.s  6
0x91e2e  ldloc.s  6
0x91e30  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x91e35  ldc.i4.2
0x91e36  newarr   [mscorlib]System.String
0x91e3b  dup
0x91e3c  ldc.i4.0
0x91e3d  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x91e42  stelem.ref
0x91e43  dup
0x91e44  ldc.i4.1
0x91e45  ldstr    aClienttype// "clienttype"
0x91e4a  stelem.ref
0x91e4b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x91e50  ldloc.s  6
0x91e52  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x91e57  ldstr    aAppmoduleid// "appmoduleid"
0x91e5c  ldc.i4.0
0x91e5d  ldarg.1
0x91e5e  box      [mscorlib]System.Guid
0x91e63  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x91e68  pop
0x91e69  ldarg.0
0x91e6a  ldarg.1
0x91e6b  ldstr    aAppmodule// "AppModule"
0x91e70  ldarg.2
0x91e71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x91e76  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x91e7b  ldloc.s  6
0x91e7d  ldarg.2
0x91e7e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x91e83  stloc.s  7
0x91e85  ldloc.s  7
0x91e87  brtrue.s loc_91EC6
0x91e89  ldstr    aAppmodule// "AppModule"
0x91e8e  ldarg.1
0x91e8f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string, valuetype [mscorlib]System.Guid)
0x91e94  stloc.s  0xD
0x91e96  ldloc.s  0xD
0x91e98  ldarg.2
0x91e99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x91e9e  ldc.i4.s 0x47
0x91ea0  ldstr    aAppmoduleservi_47// "AppModuleService.ValidateAppModule(): A"...
0x91ea5  ldc.i4.2
0x91ea6  newarr   [mscorlib]System.Object
0x91eab  dup
0x91eac  ldc.i4.0
0x91ead  ldarg.1
0x91eae  box      [mscorlib]System.Guid
0x91eb3  stelem.ref
0x91eb4  dup
0x91eb5  ldc.i4.1
0x91eb6  ldloc.s  0xD
0x91eb8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x91ebd  stelem.ref
0x91ebe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x91ec3  ldloc.s  0xD
0x91ec5  throw
0x91ec6  ldloc.s  7
0x91ec8  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x91ecd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x91ed2  unbox.any [mscorlib]System.Guid
0x91ed7  stloc.s  8
0x91ed9  ldarg.0
0x91eda  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x91edf  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x91ee4  ldc.i4.1
0x91ee5  newarr   [mscorlib]System.Guid
0x91eea  dup
0x91eeb  ldc.i4.0
0x91eec  ldloc.s  8
0x91eee  stelem   [mscorlib]System.Guid
0x91ef3  ldc.i4.2
0x91ef4  newarr   [mscorlib]System.String
0x91ef9  dup
0x91efa  ldc.i4.0
0x91efb  ldstr    aObjectid// "objectid"
0x91f00  stelem.ref
0x91f01  dup
0x91f02  ldc.i4.1
0x91f03  ldstr    aComponenttype// "componenttype"
0x91f08  stelem.ref
0x91f09  ldarg.2
0x91f0a  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91f0f  stloc.s  9
0x91f11  newobj   instance void Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x91f16  ldloc.s  9
0x91f18  ldarg.2
0x91f19  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x91f1e  stloc.s  0xA
0x91f20  ldloc.s  0xA
0x91f22  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x91f27  brtrue.s loc_91F79
0x91f29  ldloc.1
0x91f2a  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x91f2f  dup
0x91f30  ldc.i4.2
0x91f31  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x91f36  dup
0x91f37  ldstr    aNoappmodulecom// "NoAppModuleComponentReferred"
0x91f3c  ldarg.2
0x91f3d  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x91f42  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_Message(string)
0x91f47  dup
0x91f48  ldc.i4   0x8005011B
0x91f4d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_CRMErrorCode(int32)
0x91f52  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x91f57  ldnull
0x91f58  ldarg.2
0x91f59  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x91f5e  ldc.i4.s 0x47
0x91f60  ldstr    aAppmoduleservi_48// "AppModuleService.ValidateAppModule(): A"...
0x91f65  ldc.i4.1
0x91f66  newarr   [mscorlib]System.Object
0x91f6b  dup
0x91f6c  ldc.i4.0
0x91f6d  ldarg.1
0x91f6e  box      [mscorlib]System.Guid
0x91f73  stelem.ref
0x91f74  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x91f79  ldloc.s  0xA
0x91f7b  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionExtensions::ToCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection)
0x91f80  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__96_0
0x91f85  dup
0x91f86  brtrue.s loc_91F9F
0x91f88  pop
0x91f89  ldsfld   class <>c <>c::<>9
0x91f8e  ldftn    instance valuetype [mscorlib]System.Guid <>c::<ValidateAppModule>b__96_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModuleComponent)
0x91f94  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x91f99  dup
0x91f9a  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__96_0
0x91f9f  call     T0x2B000073
0x91fa4  stloc.s  5
0x91fa6  ldc.i4.0
0x91fa7  stloc.s  0xB
0x91fa9  ldc.i4.0
0x91faa  stloc.s  0xC
0x91fac  ldloc.s  7
0x91fae  ldstr    aClienttype// "clienttype"
0x91fb3  ldloca.s 0xC
0x91fb5  callvirt T0x2B00003C
0x91fba  brfalse.s loc_91FC4
0x91fbc  ldloc.s  0xC
0x91fbe  ldc.i4.4
0x91fbf  bne.un.s loc_91FC4
0x91fc1  ldc.i4.1
0x91fc2  stloc.s  0xB
0x91fc4  ldloc.s  0xA
0x91fc6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x91fcb  stloc.s  0xE
0x91fcd  br.s     loc_92026
0x91fcf  ldloc.s  0xE
0x91fd1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x91fd6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x91fdb  stloc.s  0xF
0x91fdd  ldloc.s  0xF
0x91fdf  ldstr    aComponenttype// "componenttype"
0x91fe4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x91fe9  unbox.any [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x91fee  stloc.s  0x10
0x91ff0  ldloc.3
0x91ff1  ldloc.s  0x10
0x91ff3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x91ff8  brtrue.s loc_92007
0x91ffa  ldloc.3
0x91ffb  ldloc.s  0x10
0x91ffd  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x92002  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x92007  ldloc.3
0x92008  ldloc.s  0x10
0x9200a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x9200f  ldloc.s  0xF
0x92011  ldstr    aObjectid// "objectid"
0x92016  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x9201b  unbox.any [mscorlib]System.Guid
0x92020  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x92025  pop
0x92026  ldloc.s  0xE
0x92028  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9202d  brtrue.s loc_91FCF
0x9202f  leave.s  loc_92046
0x92031  ldloc.s  0xE
0x92033  isinst   [mscorlib]System.IDisposable
0x92038  stloc.s  0x11
0x9203a  ldloc.s  0x11
0x9203c  brfalse.s loc_92045
0x9203e  ldloc.s  0x11
0x92040  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92045  endfinally
0x92046  ldloc.3
0x92047  ldc.i4.s 0x3E
0x92049  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x9204e  brtrue.s loc_920A9
0x92050  ldloc.1
0x92051  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x92056  dup
0x92057  ldc.i4.1
0x92058  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x9205d  dup
0x9205e  ldstr    aNositemaprefer// "NoSiteMapReferenceInAppModule"
0x92063  ldarg.2
0x92064  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x92069  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_Message(string)
0x9206e  dup
0x9206f  ldc.i4   0x8005011C
0x92074  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_CRMErrorCode(int32)
0x92079  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x9207e  ldnull
0x9207f  ldarg.2
0x92080  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92085  ldc.i4.s 0x47
0x92087  ldstr    aAppmoduleservi_49// "AppModuleService.ValidateAppModule():  "...
0x9208c  ldc.i4.1
0x9208d  newarr   [mscorlib]System.Object
0x92092  dup
0x92093  ldc.i4.0
0x92094  ldarg.1
0x92095  box      [mscorlib]System.Guid
0x9209a  stelem.ref
0x9209b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x920a0  ldloc.0
0x920a1  ldc.i4.0
0x920a2  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleValidationResponse::set_CanBeActivated(bool)
0x920a7  br.s     loc_920C0
0x920a9  ldarg.0
0x920aa  ldstr    aSitemap// "SiteMap"
0x920af  ldloc.3
0x920b0  ldc.i4.s 0x3E
0x920b2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x920b7  ldloc.s  5
0x920b9  ldloc.1
0x920ba  ldarg.2
0x920bb  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ValidateForUnresolvedDependencies(string componentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> objectIds, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> appModuleComponentIds, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue> validationIssueList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x920c0  ldloc.3
0x920c1  ldc.i4.1
0x920c2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x920c7  brtrue.s loc_9211B
0x920c9  ldloc.1
0x920ca  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x920cf  dup
0x920d0  ldc.i4.2
0x920d1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x920d6  dup
0x920d7  ldstr    aAppmodulenotre// "AppModuleNotReferEntity"
0x920dc  ldarg.2
0x920dd  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x920e2  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_Message(string)
0x920e7  dup
0x920e8  ldc.i4   0x8005011D
0x920ed  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_CRMErrorCode(int32)
0x920f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x920f7  ldnull
0x920f8  ldarg.2
0x920f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x920fe  ldc.i4.s 0x47
0x92100  ldstr    aAppmoduleservi_50// "AppModuleService.ValidateAppModule(): F"...
0x92105  ldc.i4.1
0x92106  newarr   [mscorlib]System.Object
0x9210b  dup
0x9210c  ldc.i4.0
0x9210d  ldarg.1
0x9210e  box      [mscorlib]System.Guid
0x92113  stelem.ref
0x92114  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92119  br.s     loc_9213F
0x9211b  ldloc.3
0x9211c  ldc.i4   0xA1
0x92121  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x92126  stloc.s  0x12
0x92128  ldarg.0
0x92129  ldloc.3
0x9212a  ldc.i4.1
0x9212b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92130  ldloc.2
0x92131  ldarg.1
0x92132  ldloc.s  0xB
0x92134  ldloc.s  0x12
0x92136  ldloc.1
0x92137  ldarg.2
0x92138  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::ValidateForEntity(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> entityIds, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleEntity> appModuleEntities, valuetype [mscorlib]System.Guid appModuleId, bool isUCIEnabledAppModule, bool isAppModuleOfflineEnabled, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue> validationIssueList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9213d  stloc.s  4
  ... truncated ...
```
