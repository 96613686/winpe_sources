# Microsoft.Crm.ObjectModel.AppModuleService::ValidateApp

- ea: `0x92240`
- end: `0x92663`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::ValidateApp`
- size: `1059`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x19b50`
- `0x8f9b0`
- `0x92240`
- `0x94a50`
- `0x958c0`
- `0x95d60`
- `0x95ec0`
- `0x95fd0`
- `0x96140`

## string_xrefs

- `0x92328`: `componenttype`
- `0x92404`: `componenttype`
- `0x922ff`: `AppModuleComponent`
- `0x925d6`: `RibbonCommand`
- `0x9235c`: `NoAppModuleComponentReferred`
- `0x922ce`: `AppModuleService.ValidateApp(): For AppModule with [appmoduleid:{0}] no entity found.`
- `0x92385`: `AppModuleService.ValidateApp(): For AppModule with [appmoduleid:{0}] no components found.`
- `0x924ac`: `AppModuleService.ValidateApp(): For AppModule with [appmoduleid:{0}] no Sitemap found.`
- `0x92525`: `AppModuleService.ValidateApp(): For AppModule with [appmoduleid:{0}] no Entity components found.`

## pseudocode

```c

```

## disassembly

```asm
0x92240  ldarg.0
0x92241  ldarg.2
0x92242  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92247  ldarg.1
0x92248  ldstr    aAppmoduleid// "appmoduleid"
0x9224d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x92252  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppValidationResponse::.ctor()
0x92257  stloc.0
0x92258  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::.ctor()
0x9225d  stloc.1
0x9225e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleEntity>::.ctor()
0x92263  stloc.2
0x92264  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x92269  stloc.3
0x9226a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [mscorlib]System.Guid>::.ctor()
0x9226f  stloc.s  4
0x92271  ldarg.0
0x92272  ldstr    aAppmodule// "AppModule"
0x92277  ldstr    aAppmoduleid// "appmoduleid"
0x9227c  ldc.i4.1
0x9227d  newarr   [mscorlib]System.Guid
0x92282  dup
0x92283  ldc.i4.0
0x92284  ldarg.1
0x92285  stelem   [mscorlib]System.Guid
0x9228a  ldc.i4.1
0x9228b  newarr   [mscorlib]System.String
0x92290  dup
0x92291  ldc.i4.0
0x92292  ldstr    aUniquename// "uniquename"
0x92297  stelem.ref
0x92298  ldarg.2
0x92299  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9229e  stloc.s  6
0x922a0  ldarg.0
0x922a1  ldloc.s  6
0x922a3  ldarg.2
0x922a4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x922a9  stloc.s  7
0x922ab  ldnull
0x922ac  stloc.s  8
0x922ae  ldloc.s  7
0x922b0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x922b5  brtrue.s loc_922E1
0x922b7  ldstr    aAppmodule// "AppModule"
0x922bc  ldarg.1
0x922bd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string, valuetype [mscorlib]System.Guid)
0x922c2  stloc.s  0xE
0x922c4  ldloc.s  0xE
0x922c6  ldarg.2
0x922c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x922cc  ldc.i4.s 0x47
0x922ce  ldstr    aAppmoduleservi_51// "AppModuleService.ValidateApp(): For App"...
0x922d3  ldc.i4.0
0x922d4  newarr   [mscorlib]System.Object
0x922d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x922de  ldloc.s  0xE
0x922e0  throw
0x922e1  ldloc.s  7
0x922e3  ldc.i4.0
0x922e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x922e9  stloc.s  8
0x922eb  ldloc.s  8
0x922ed  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x922f2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x922f7  unbox.any [mscorlib]System.Guid
0x922fc  stloc.s  9
0x922fe  ldarg.0
0x922ff  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x92304  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x92309  ldc.i4.1
0x9230a  newarr   [mscorlib]System.Guid
0x9230f  dup
0x92310  ldc.i4.0
0x92311  ldloc.s  9
0x92313  stelem   [mscorlib]System.Guid
0x92318  ldc.i4.2
0x92319  newarr   [mscorlib]System.String
0x9231e  dup
0x9231f  ldc.i4.0
0x92320  ldstr    aObjectid// "objectid"
0x92325  stelem.ref
0x92326  dup
0x92327  ldc.i4.1
0x92328  ldstr    aComponenttype// "componenttype"
0x9232d  stelem.ref
0x9232e  ldarg.2
0x9232f  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92334  stloc.s  0xA
0x92336  newobj   instance void Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x9233b  ldloc.s  0xA
0x9233d  ldarg.2
0x9233e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92343  stloc.s  0xB
0x92345  ldloc.s  0xB
0x92347  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x9234c  brtrue.s loc_9239E
0x9234e  ldloc.1
0x9234f  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x92354  dup
0x92355  ldc.i4.2
0x92356  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x9235b  dup
0x9235c  ldstr    aNoappmodulecom// "NoAppModuleComponentReferred"
0x92361  ldarg.2
0x92362  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x92367  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_Message(string)
0x9236c  dup
0x9236d  ldc.i4   0x8005011B
0x92372  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_CRMErrorCode(int32)
0x92377  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x9237c  ldnull
0x9237d  ldarg.2
0x9237e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92383  ldc.i4.s 0x47
0x92385  ldstr    aAppmoduleservi_52// "AppModuleService.ValidateApp(): For App"...
0x9238a  ldc.i4.1
0x9238b  newarr   [mscorlib]System.Object
0x92390  dup
0x92391  ldc.i4.0
0x92392  ldarg.1
0x92393  box      [mscorlib]System.Guid
0x92398  stelem.ref
0x92399  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9239e  ldloc.s  0xB
0x923a0  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionExtensions::ToCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection)
0x923a5  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__97_0
0x923aa  dup
0x923ab  brtrue.s loc_923C4
0x923ad  pop
0x923ae  ldsfld   class <>c <>c::<>9
0x923b3  ldftn    instance valuetype [mscorlib]System.Guid <>c::<ValidateApp>b__97_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModuleComponent)
0x923b9  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x923be  dup
0x923bf  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__97_0
0x923c4  call     T0x2B000073
0x923c9  stloc.s  5
0x923cb  ldc.i4.0
0x923cc  stloc.s  0xC
0x923ce  ldc.i4.0
0x923cf  stloc.s  0xD
0x923d1  ldloc.s  8
0x923d3  ldstr    aClienttype// "clienttype"
0x923d8  ldloca.s 0xD
0x923da  callvirt T0x2B00003C
0x923df  brfalse.s loc_923E9
0x923e1  ldloc.s  0xD
0x923e3  ldc.i4.4
0x923e4  bne.un.s loc_923E9
0x923e6  ldc.i4.1
0x923e7  stloc.s  0xC
0x923e9  ldloc.s  0xB
0x923eb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x923f0  stloc.s  0xF
0x923f2  br.s     loc_9244B
0x923f4  ldloc.s  0xF
0x923f6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x923fb  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x92400  stloc.s  0x10
0x92402  ldloc.s  0x10
0x92404  ldstr    aComponenttype// "componenttype"
0x92409  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x9240e  unbox.any [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x92413  stloc.s  0x11
0x92415  ldloc.3
0x92416  ldloc.s  0x11
0x92418  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x9241d  brtrue.s loc_9242C
0x9241f  ldloc.3
0x92420  ldloc.s  0x11
0x92422  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x92427  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>, !!T0)
0x9242c  ldloc.3
0x9242d  ldloc.s  0x11
0x9242f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92434  ldloc.s  0x10
0x92436  ldstr    aObjectid// "objectid"
0x9243b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x92440  unbox.any [mscorlib]System.Guid
0x92445  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x9244a  pop
0x9244b  ldloc.s  0xF
0x9244d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x92452  brtrue.s loc_923F4
0x92454  leave.s  loc_9246B
0x92456  ldloc.s  0xF
0x92458  isinst   [mscorlib]System.IDisposable
0x9245d  stloc.s  0x12
0x9245f  ldloc.s  0x12
0x92461  brfalse.s loc_9246A
0x92463  ldloc.s  0x12
0x92465  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9246a  endfinally
0x9246b  ldloc.3
0x9246c  ldc.i4.s 0x3E
0x9246e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x92473  brtrue.s loc_924CE
0x92475  ldloc.1
0x92476  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x9247b  dup
0x9247c  ldc.i4.1
0x9247d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x92482  dup
0x92483  ldstr    aNositemaprefer// "NoSiteMapReferenceInAppModule"
0x92488  ldarg.2
0x92489  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9248e  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_Message(string)
0x92493  dup
0x92494  ldc.i4   0x8005011C
0x92499  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_CRMErrorCode(int32)
0x9249e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x924a3  ldnull
0x924a4  ldarg.2
0x924a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x924aa  ldc.i4.s 0x47
0x924ac  ldstr    aAppmoduleservi_53// "AppModuleService.ValidateApp(): For App"...
0x924b1  ldc.i4.1
0x924b2  newarr   [mscorlib]System.Object
0x924b7  dup
0x924b8  ldc.i4.0
0x924b9  ldarg.1
0x924ba  box      [mscorlib]System.Guid
0x924bf  stelem.ref
0x924c0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x924c5  ldloc.0
0x924c6  ldc.i4.0
0x924c7  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppValidationResponse::set_ValidationSuccess(bool)
0x924cc  br.s     loc_924E5
0x924ce  ldarg.0
0x924cf  ldstr    aSitemap// "SiteMap"
0x924d4  ldloc.3
0x924d5  ldc.i4.s 0x3E
0x924d7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x924dc  ldloc.s  5
0x924de  ldloc.1
0x924df  ldarg.2
0x924e0  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ValidateForUnresolvedDependencies(string componentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> objectIds, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> appModuleComponentIds, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue> validationIssueList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x924e5  ldloc.3
0x924e6  ldc.i4.1
0x924e7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x924ec  brtrue.s loc_92540
0x924ee  ldloc.1
0x924ef  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x924f4  dup
0x924f5  ldc.i4.2
0x924f6  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x924fb  dup
0x924fc  ldstr    aAppmodulenotre// "AppModuleNotReferEntity"
0x92501  ldarg.2
0x92502  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x92507  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_Message(string)
0x9250c  dup
0x9250d  ldc.i4   0x8005011D
0x92512  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_CRMErrorCode(int32)
0x92517  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x9251c  ldnull
0x9251d  ldarg.2
0x9251e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92523  ldc.i4.s 0x47
0x92525  ldstr    aAppmoduleservi_54// "AppModuleService.ValidateApp(): For App"...
0x9252a  ldc.i4.1
0x9252b  newarr   [mscorlib]System.Object
0x92530  dup
0x92531  ldc.i4.0
0x92532  ldarg.1
0x92533  box      [mscorlib]System.Guid
0x92538  stelem.ref
0x92539  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9253e  br.s     loc_92564
0x92540  ldloc.3
0x92541  ldc.i4   0xA1
0x92546  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x9254b  stloc.s  0x13
0x9254d  ldarg.0
0x9254e  ldloc.3
0x9254f  ldc.i4.1
0x92550  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92555  ldloc.2
0x92556  ldarg.1
0x92557  ldloc.s  0xC
0x92559  ldloc.s  0x13
0x9255b  ldloc.1
0x9255c  ldarg.2
0x9255d  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::ValidateForEntity(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> entityIds, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleEntity> appModuleEntities, valuetype [mscorlib]System.Guid appModuleId, bool isUCIEnabledAppModule, bool isAppModuleOfflineEnabled, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue> validationIssueList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92562  stloc.s  4
0x92564  ldloc.3
0x92565  ldc.i4.s 0x3C
0x92567  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x9256c  brfalse.s loc_92592
0x9256e  ldarg.0
0x9256f  ldstr    aSystemform// "SystemForm"
0x92574  ldloc.3
0x92575  ldc.i4.s 0x3C
0x92577  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x9257c  ldstr    aFormid// "formid"
0x92581  ldstr    aObjecttypecode// "objecttypecode"
0x92586  ldloc.s  4
0x92588  ldloc.s  5
0x9258a  ldloc.2
0x9258b  ldloc.1
  ... truncated ...
```
