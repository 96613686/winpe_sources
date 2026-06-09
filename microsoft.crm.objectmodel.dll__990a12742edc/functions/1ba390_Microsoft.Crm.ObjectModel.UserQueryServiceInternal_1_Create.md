# Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1::Create

- ea: `0x1ba390`
- end: `0x1ba6f0`
- name: `Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1::Create`
- size: `864`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x317f0`
- `0x159720`
- `0x15a490`
- `0x16dd90`
- `0x16de40`
- `0x1ba390`

## string_xrefs

- `0x1ba637`: `layoutjson`
- `0x1ba406`: `fetchxml`
- `0x1ba428`: `fetchxml`
- `0x1ba455`: `fetchxml`
- `0x1ba5b1`: `fetchxml`
- `0x1ba5c7`: `fetchxml`
- `0x1ba611`: `fetchxml`
- `0x1ba61e`: `fetchxml`
- `0x1ba462`: `layoutxml`
- `0x1ba4a4`: `layoutxml`
- `0x1ba4aa`: `layoutxml`
- `0x1ba4c6`: `layoutxml`
- `0x1ba5e2`: `layoutxml`
- `0x1ba63f`: `layoutxml`
- `0x1ba3f5`: `Cannot create address book filters`

## pseudocode

```c

```

## disassembly

```asm
0x1ba390  ldarg.1
0x1ba391  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1ba396  stloc.0
0x1ba397  ldc.i4.m1
0x1ba398  stloc.1
0x1ba399  ldloc.0
0x1ba39a  ldstr    aQuerytype// "querytype"
0x1ba39f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba3a4  brtrue.s loc_1BA3B7
0x1ba3a6  ldloc.0
0x1ba3a7  ldstr    aQuerytype// "querytype"
0x1ba3ac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba3b1  unbox.any [mscorlib]System.Int32
0x1ba3b6  stloc.1
0x1ba3b7  ldc.i4.0
0x1ba3b8  stloc.2
0x1ba3b9  ldloc.0
0x1ba3ba  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba3bf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba3c4  brtrue.s loc_1BA3D7
0x1ba3c6  ldloc.0
0x1ba3c7  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba3cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba3d1  unbox.any [mscorlib]System.Int32
0x1ba3d6  stloc.2
0x1ba3d7  ldloc.2
0x1ba3d8  brfalse.s loc_1BA3ED
0x1ba3da  ldarg.0
0x1ba3db  ldloc.1
0x1ba3dc  ldarg.2
0x1ba3dd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba3e2  ldloc.2
0x1ba3e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1ba3e8  call     instance void class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::ValidateEntityForFilterCreateOrUpdate(valuetype Microsoft.Crm.ObjectModel.SavedQueryType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x1ba3ed  ldc.i4   0x200
0x1ba3f2  ldloc.1
0x1ba3f3  bne.un.s loc_1BA405
0x1ba3f5  ldstr    aCannotCreateAd// "Cannot create address book filters"
0x1ba3fa  ldc.i4   0x80048447
0x1ba3ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1ba404  throw
0x1ba405  ldloc.0
0x1ba406  ldstr    aFetchxml// "fetchxml"
0x1ba40b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba410  brtrue.s loc_1BA461
0x1ba412  ldloc.1
0x1ba413  ldc.i4.m1
0x1ba414  bne.un.s loc_1BA426
0x1ba416  ldstr    aTheQueryTypeIs// "The query type is missing."
0x1ba41b  ldc.i4   0x80040235
0x1ba420  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1ba425  throw
0x1ba426  ldarg.0
0x1ba427  ldloc.0
0x1ba428  ldstr    aFetchxml// "fetchxml"
0x1ba42d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba432  castclass [mscorlib]System.String
0x1ba437  ldloc.2
0x1ba438  ldarg.2
0x1ba439  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::ValidateFetchAndReturnTypeCode(string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba43e  stloc.s  4
0x1ba440  ldarg.0
0x1ba441  ldloc.s  4
0x1ba443  ldloc.1
0x1ba444  call     instance string class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::UpdateFetchXmlForOfflineFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, int32)
0x1ba449  stloc.s  5
0x1ba44b  ldloc.s  5
0x1ba44d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ba452  brtrue.s loc_1BA461
0x1ba454  ldloc.0
0x1ba455  ldstr    aFetchxml// "fetchxml"
0x1ba45a  ldloc.s  5
0x1ba45c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1ba461  ldloc.0
0x1ba462  ldstr    aLayoutxml// "layoutxml"
0x1ba467  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba46c  brtrue.s loc_1BA4DA
0x1ba46e  ldarg.2
0x1ba46f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x1ba474  brfalse.s loc_1BA4C5
0x1ba476  ldarg.0
0x1ba477  ldarg.2
0x1ba478  call     instance int32 class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::GetYearFromEndPoint(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba47d  ldc.i4   0x7D9
0x1ba482  bge.s    loc_1BA4C5
0x1ba484  ldloc.0
0x1ba485  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba48a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba48f  brtrue.s loc_1BA4C5
0x1ba491  ldloc.0
0x1ba492  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba497  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba49c  unbox.any [mscorlib]System.Int32
0x1ba4a1  stloc.s  6
0x1ba4a3  ldloc.0
0x1ba4a4  ldstr    aLayoutxml// "layoutxml"
0x1ba4a9  ldloc.0
0x1ba4aa  ldstr    aLayoutxml// "layoutxml"
0x1ba4af  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba4b4  castclass [mscorlib]System.String
0x1ba4b9  ldloc.s  6
0x1ba4bb  call     string Microsoft.Crm.ObjectModel.LayoutXmlValidator::AddNewAttributesToLayoutXml(string layoutXml, int32 returnedTypeCode)
0x1ba4c0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1ba4c5  ldloc.0
0x1ba4c6  ldstr    aLayoutxml// "layoutxml"
0x1ba4cb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba4d0  castclass [mscorlib]System.String
0x1ba4d5  call     void Microsoft.Crm.ObjectModel.LayoutXmlValidator::ValidateLayoutXml(string layoutXml)
0x1ba4da  ldc.i4   0x100
0x1ba4df  ldloc.1
0x1ba4e0  beq.s    loc_1BA4EA
0x1ba4e2  ldc.i4.s 0x10
0x1ba4e4  ldloc.1
0x1ba4e5  bne.un   loc_1BA5B0
0x1ba4ea  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1ba4ef  ldstr    aUserfilterlimi// "UserFilterLimit"
0x1ba4f4  callvirt T0x2B00019D
0x1ba4f9  stloc.s  7
0x1ba4fb  ldloc.s  7
0x1ba4fd  ldc.i4.0
0x1ba4fe  blt      loc_1BA5B0
0x1ba503  ldarg.2
0x1ba504  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1ba509  stloc.s  8
0x1ba50b  ldloc.0
0x1ba50c  ldstr    aOwnerid// "ownerid"
0x1ba511  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba516  brtrue.s loc_1BA52A
0x1ba518  ldloc.0
0x1ba519  ldstr    aOwnerid// "ownerid"
0x1ba51e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba523  unbox.any [mscorlib]System.Guid
0x1ba528  stloc.s  8
0x1ba52a  ldarg.0
0x1ba52b  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1ba530  ldarg.2
0x1ba531  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1ba536  stloc.s  9
0x1ba538  ldloc.s  9
0x1ba53a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1ba53f  ldc.i4.0
0x1ba540  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1ba545  dup
0x1ba546  ldstr    aQuerytype// "querytype"
0x1ba54b  ldc.i4.0
0x1ba54c  ldloc.1
0x1ba54d  box      [mscorlib]System.Int32
0x1ba552  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1ba557  pop
0x1ba558  dup
0x1ba559  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba55e  ldc.i4.0
0x1ba55f  ldloc.0
0x1ba560  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba565  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba56a  unbox.any [mscorlib]System.Int32
0x1ba56f  box      [mscorlib]System.Int32
0x1ba574  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1ba579  pop
0x1ba57a  ldstr    aOwnerid// "ownerid"
0x1ba57f  ldc.i4.0
0x1ba580  ldloc.s  8
0x1ba582  box      [mscorlib]System.Guid
0x1ba587  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1ba58c  pop
0x1ba58d  ldarg.0
0x1ba58e  ldloc.s  9
0x1ba590  ldarg.2
0x1ba591  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba596  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1ba59b  ldloc.s  7
0x1ba59d  blt.s    loc_1BA5B0
0x1ba59f  ldc.i4   0x8004027C
0x1ba5a4  ldc.i4.0
0x1ba5a5  newarr   [mscorlib]System.Object
0x1ba5aa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1ba5af  throw
0x1ba5b0  ldarg.1
0x1ba5b1  ldstr    aFetchxml// "fetchxml"
0x1ba5b6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba5bb  brtrue.s loc_1BA5E1
0x1ba5bd  ldarg.1
0x1ba5be  ldstr    aOfflinesqlquer// "offlinesqlquery"
0x1ba5c3  ldarg.0
0x1ba5c4  ldloc.1
0x1ba5c5  ldloc.2
0x1ba5c6  ldarg.1
0x1ba5c7  ldstr    aFetchxml// "fetchxml"
0x1ba5cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba5d1  castclass [mscorlib]System.String
0x1ba5d6  ldarg.2
0x1ba5d7  call     instance string class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::PopulateOfflineSqlQueryAttribute(int32, int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba5dc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1ba5e1  ldarg.1
0x1ba5e2  ldstr    aLayoutxml// "layoutxml"
0x1ba5e7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba5ec  brtrue.s loc_1BA65B
0x1ba5ee  ldarg.1
0x1ba5ef  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba5f4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba5f9  brtrue.s loc_1BA60D
0x1ba5fb  ldarg.1
0x1ba5fc  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba601  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba606  unbox.any [mscorlib]System.Int32
0x1ba60b  br.s     loc_1BA60E
0x1ba60d  ldc.i4.m1
0x1ba60e  stloc.s  0xA
0x1ba610  ldarg.1
0x1ba611  ldstr    aFetchxml// "fetchxml"
0x1ba616  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba61b  brtrue.s loc_1BA62F
0x1ba61d  ldarg.1
0x1ba61e  ldstr    aFetchxml// "fetchxml"
0x1ba623  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba628  callvirt instance string [mscorlib]System.Object::ToString()
0x1ba62d  br.s     loc_1BA634
0x1ba62f  ldsfld   string [mscorlib]System.String::Empty
0x1ba634  stloc.s  0xB
0x1ba636  ldarg.1
0x1ba637  ldstr    aLayoutjson// "layoutjson"
0x1ba63c  ldloc.s  0xB
0x1ba63e  ldarg.1
0x1ba63f  ldstr    aLayoutxml// "layoutxml"
0x1ba644  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba649  callvirt instance string [mscorlib]System.Object::ToString()
0x1ba64e  ldloc.s  0xA
0x1ba650  ldarg.2
0x1ba651  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetPopulatedLayoutJson(string fetchXml, string layoutXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ba656  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1ba65b  ldnull
0x1ba65c  stloc.3
0x1ba65d  ldloc.0
0x1ba65e  ldstr    aOwnerid// "ownerid"
0x1ba663  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba668  brtrue.s loc_1BA6B0
0x1ba66a  ldarg.2
0x1ba66b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1ba670  ldloc.0
0x1ba671  ldstr    aOwnerid// "ownerid"
0x1ba676  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba67b  unbox.any [mscorlib]System.Guid
0x1ba680  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ba685  brfalse.s loc_1BA6B0
0x1ba687  ldarg.0
0x1ba688  ldloc.1
0x1ba689  ldarg.2
0x1ba68a  call     instance bool class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::NeedsSystemUserContextForFilterManagement(valuetype Microsoft.Crm.ObjectModel.SavedQueryType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba68f  brfalse.s loc_1BA6B0
0x1ba691  ldarg.2
0x1ba692  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba697  stloc.s  0xC
0x1ba699  ldarg.0
0x1ba69a  ldarg.1
0x1ba69b  ldarg.2
0x1ba69c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba6a1  stloc.3
0x1ba6a2  leave.s  loc_1BA6B9
0x1ba6a4  ldloc.s  0xC
0x1ba6a6  brfalse.s loc_1BA6AF
0x1ba6a8  ldloc.s  0xC
0x1ba6aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ba6af  endfinally
0x1ba6b0  ldarg.0
0x1ba6b1  ldarg.1
0x1ba6b2  ldarg.2
0x1ba6b3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba6b8  stloc.3
0x1ba6b9  ldc.i4.s 0x10
0x1ba6bb  ldloc.1
0x1ba6bc  beq.s    loc_1BA6C6
0x1ba6be  ldc.i4   0x100
0x1ba6c3  ldloc.1
0x1ba6c4  bne.un.s loc_1BA6E6
0x1ba6c6  ldloc.0
0x1ba6c7  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba6cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba6d1  unbox.any [mscorlib]System.Int32
0x1ba6d6  stloc.s  0xD
0x1ba6d8  newobj   instance void Microsoft.Crm.ObjectModel.SubscriptionService::.ctor()
0x1ba6dd  ldloc.1
0x1ba6de  ldloc.s  0xD
0x1ba6e0  ldarg.2
0x1ba6e1  callvirt instance void Microsoft.Crm.ObjectModel.SubscriptionService::UpdateFilterStatistics(int32 queryType, int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ba6e6  ldarg.0
0x1ba6e7  ldloc.0
0x1ba6e8  ldarg.2
0x1ba6e9  call     instance void class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::CreateRuntimeDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba6ee  ldloc.3
0x1ba6ef  ret
```
