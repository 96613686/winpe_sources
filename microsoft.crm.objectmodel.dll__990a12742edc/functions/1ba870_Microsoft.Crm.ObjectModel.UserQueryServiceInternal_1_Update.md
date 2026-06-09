# Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1::Update

- ea: `0x1ba870`
- end: `0x1bac43`
- name: `Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1::Update`
- size: `979`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x317f0`
- `0x159720`
- `0x15a490`
- `0x16dd90`
- `0x16de40`
- `0x1ba870`

## string_xrefs

- `0x1bab4b`: `layoutjson`
- `0x1ba8dd`: `fetchxml`
- `0x1ba91d`: `fetchxml`
- `0x1ba94a`: `fetchxml`
- `0x1baa30`: `fetchxml`
- `0x1baa3e`: `fetchxml`
- `0x1bab25`: `fetchxml`
- `0x1bab32`: `fetchxml`
- `0x1bab70`: `fetchxml`
- `0x1bab87`: `fetchxml`
- `0x1babe0`: `fetchxml`
- `0x1ba957`: `layoutxml`
- `0x1ba97a`: `layoutxml`
- `0x1ba980`: `layoutxml`
- `0x1ba99b`: `layoutxml`
- `0x1baaf6`: `layoutxml`
- `0x1bab53`: `layoutxml`
- `0x1ba8cc`: `Cannot update address book filters`

## pseudocode

```c

```

## disassembly

```asm
0x1ba870  ldarg.1
0x1ba871  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1ba876  stloc.0
0x1ba877  ldc.i4.0
0x1ba878  stloc.1
0x1ba879  ldarg.0
0x1ba87a  ldloc.0
0x1ba87b  ldstr    aUserqueryid// "userqueryid"
0x1ba880  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba885  unbox.any [mscorlib]System.Guid
0x1ba88a  ldloca.s 1
0x1ba88c  ldarg.2
0x1ba88d  call     instance int32 class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::RetrieveQueryType(valuetype [mscorlib]System.Guid, int32&, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba892  stloc.2
0x1ba893  ldarg.1
0x1ba894  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba899  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba89e  brtrue.s loc_1BA8C4
0x1ba8a0  ldarg.1
0x1ba8a1  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba8a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba8ab  unbox.any [mscorlib]System.Int32
0x1ba8b0  stloc.1
0x1ba8b1  ldarg.0
0x1ba8b2  ldloc.2
0x1ba8b3  ldarg.2
0x1ba8b4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba8b9  ldloc.1
0x1ba8ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1ba8bf  call     instance void class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::ValidateEntityForFilterCreateOrUpdate(valuetype Microsoft.Crm.ObjectModel.SavedQueryType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x1ba8c4  ldc.i4   0x200
0x1ba8c9  ldloc.2
0x1ba8ca  bne.un.s loc_1BA8DC
0x1ba8cc  ldstr    aCannotUpdateAd// "Cannot update address book filters"
0x1ba8d1  ldc.i4   0x8004022E
0x1ba8d6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1ba8db  throw
0x1ba8dc  ldloc.0
0x1ba8dd  ldstr    aFetchxml// "fetchxml"
0x1ba8e2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba8e7  brtrue.s loc_1BA956
0x1ba8e9  ldloc.0
0x1ba8ea  ldstr    aQuerytype// "querytype"
0x1ba8ef  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba8f4  brtrue.s loc_1BA907
0x1ba8f6  ldloc.0
0x1ba8f7  ldstr    aQuerytype// "querytype"
0x1ba8fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba901  unbox.any [mscorlib]System.Int32
0x1ba906  stloc.2
0x1ba907  ldloc.2
0x1ba908  ldc.i4.m1
0x1ba909  bne.un.s loc_1BA91B
0x1ba90b  ldstr    aTheQueryTypeIs// "The query type is missing."
0x1ba910  ldc.i4   0x80040235
0x1ba915  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1ba91a  throw
0x1ba91b  ldarg.0
0x1ba91c  ldloc.0
0x1ba91d  ldstr    aFetchxml// "fetchxml"
0x1ba922  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba927  castclass [mscorlib]System.String
0x1ba92c  ldloc.1
0x1ba92d  ldarg.2
0x1ba92e  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::ValidateFetchAndReturnTypeCode(string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba933  stloc.s  6
0x1ba935  ldarg.0
0x1ba936  ldloc.s  6
0x1ba938  ldloc.2
0x1ba939  call     instance string class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::UpdateFetchXmlForOfflineFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, int32)
0x1ba93e  stloc.s  7
0x1ba940  ldloc.s  7
0x1ba942  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ba947  brtrue.s loc_1BA956
0x1ba949  ldloc.0
0x1ba94a  ldstr    aFetchxml// "fetchxml"
0x1ba94f  ldloc.s  7
0x1ba951  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1ba956  ldloc.0
0x1ba957  ldstr    aLayoutxml// "layoutxml"
0x1ba95c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba961  brtrue.s loc_1BA9AF
0x1ba963  ldarg.2
0x1ba964  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x1ba969  brfalse.s loc_1BA99A
0x1ba96b  ldarg.0
0x1ba96c  ldarg.2
0x1ba96d  call     instance int32 class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::GetYearFromEndPoint(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba972  ldc.i4   0x7D9
0x1ba977  bge.s    loc_1BA99A
0x1ba979  ldloc.0
0x1ba97a  ldstr    aLayoutxml// "layoutxml"
0x1ba97f  ldloc.0
0x1ba980  ldstr    aLayoutxml// "layoutxml"
0x1ba985  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba98a  castclass [mscorlib]System.String
0x1ba98f  ldloc.1
0x1ba990  call     string Microsoft.Crm.ObjectModel.LayoutXmlValidator::AddNewAttributesToLayoutXml(string layoutXml, int32 returnedTypeCode)
0x1ba995  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1ba99a  ldloc.0
0x1ba99b  ldstr    aLayoutxml// "layoutxml"
0x1ba9a0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba9a5  castclass [mscorlib]System.String
0x1ba9aa  call     void Microsoft.Crm.ObjectModel.LayoutXmlValidator::ValidateLayoutXml(string layoutXml)
0x1ba9af  ldloc.2
0x1ba9b0  stloc.3
0x1ba9b1  ldloc.1
0x1ba9b2  stloc.s  4
0x1ba9b4  ldloc.0
0x1ba9b5  ldstr    aQuerytype// "querytype"
0x1ba9ba  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba9bf  brtrue.s loc_1BA9D2
0x1ba9c1  ldloc.0
0x1ba9c2  ldstr    aQuerytype// "querytype"
0x1ba9c7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba9cc  unbox.any [mscorlib]System.Int32
0x1ba9d1  stloc.3
0x1ba9d2  ldloc.0
0x1ba9d3  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba9d8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ba9dd  brtrue.s loc_1BA9F1
0x1ba9df  ldloc.0
0x1ba9e0  ldstr    aReturnedtypeco// "returnedtypecode"
0x1ba9e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba9ea  unbox.any [mscorlib]System.Int32
0x1ba9ef  stloc.s  4
0x1ba9f1  ldloc.2
0x1ba9f2  ldloc.3
0x1ba9f3  beq      loc_1BAAF5
0x1ba9f8  ldloc.3
0x1ba9f9  ldc.i4.s 0x10
0x1ba9fb  beq.s    loc_1BAA08
0x1ba9fd  ldloc.3
0x1ba9fe  ldc.i4   0x100
0x1baa03  bne.un   loc_1BAAF5
0x1baa08  ldarg.2
0x1baa09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x1baa0e  stloc.s  8
0x1baa10  ldloc.0
0x1baa11  ldstr    aOwnerid// "ownerid"
0x1baa16  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1baa1b  brtrue.s loc_1BAA2F
0x1baa1d  ldloc.0
0x1baa1e  ldstr    aOwnerid// "ownerid"
0x1baa23  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1baa28  unbox.any [mscorlib]System.Guid
0x1baa2d  stloc.s  8
0x1baa2f  ldloc.0
0x1baa30  ldstr    aFetchxml// "fetchxml"
0x1baa35  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1baa3a  brtrue.s loc_1BAA53
0x1baa3c  ldarg.0
0x1baa3d  ldloc.0
0x1baa3e  ldstr    aFetchxml// "fetchxml"
0x1baa43  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1baa48  castclass [mscorlib]System.String
0x1baa4d  ldarg.2
0x1baa4e  call     instance void class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::LiveChecksForFetchXml(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1baa53  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1baa58  ldstr    aUserfilterlimi// "UserFilterLimit"
0x1baa5d  callvirt T0x2B00019D
0x1baa62  stloc.s  9
0x1baa64  ldloc.s  9
0x1baa66  ldc.i4.0
0x1baa67  blt      loc_1BAAF5
0x1baa6c  ldarg.0
0x1baa6d  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1baa72  ldarg.2
0x1baa73  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1baa78  stloc.s  0xA
0x1baa7a  ldloc.s  0xA
0x1baa7c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1baa81  ldc.i4.0
0x1baa82  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x1baa87  ldloc.s  0xA
0x1baa89  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1baa8e  ldstr    aUserqueryid// "userqueryid"
0x1baa93  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x1baa98  dup
0x1baa99  ldstr    aQuerytype// "querytype"
0x1baa9e  ldc.i4.0
0x1baa9f  ldloc.3
0x1baaa0  box      [mscorlib]System.Int32
0x1baaa5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1baaaa  pop
0x1baaab  dup
0x1baaac  ldstr    aReturnedtypeco// "returnedtypecode"
0x1baab1  ldc.i4.0
0x1baab2  ldloc.s  4
0x1baab4  box      [mscorlib]System.Int32
0x1baab9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1baabe  pop
0x1baabf  ldstr    aOwnerid// "ownerid"
0x1baac4  ldc.i4.0
0x1baac5  ldloc.s  8
0x1baac7  box      [mscorlib]System.Guid
0x1baacc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1baad1  pop
0x1baad2  ldarg.0
0x1baad3  ldloc.s  0xA
0x1baad5  ldarg.2
0x1baad6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1baadb  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1baae0  ldloc.s  9
0x1baae2  ble.s    loc_1BAAF5
0x1baae4  ldc.i4   0x8004027C
0x1baae9  ldc.i4.0
0x1baaea  newarr   [mscorlib]System.Object
0x1baaef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1baaf4  throw
0x1baaf5  ldarg.1
0x1baaf6  ldstr    aLayoutxml// "layoutxml"
0x1baafb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1bab00  brtrue.s loc_1BAB6F
0x1bab02  ldarg.1
0x1bab03  ldstr    aReturnedtypeco// "returnedtypecode"
0x1bab08  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1bab0d  brtrue.s loc_1BAB21
0x1bab0f  ldarg.1
0x1bab10  ldstr    aReturnedtypeco// "returnedtypecode"
0x1bab15  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1bab1a  unbox.any [mscorlib]System.Int32
0x1bab1f  br.s     loc_1BAB22
0x1bab21  ldc.i4.m1
0x1bab22  stloc.s  0xB
0x1bab24  ldarg.1
0x1bab25  ldstr    aFetchxml// "fetchxml"
0x1bab2a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1bab2f  brtrue.s loc_1BAB43
0x1bab31  ldarg.1
0x1bab32  ldstr    aFetchxml// "fetchxml"
0x1bab37  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1bab3c  callvirt instance string [mscorlib]System.Object::ToString()
0x1bab41  br.s     loc_1BAB48
0x1bab43  ldsfld   string [mscorlib]System.String::Empty
0x1bab48  stloc.s  0xC
0x1bab4a  ldarg.1
0x1bab4b  ldstr    aLayoutjson// "layoutjson"
0x1bab50  ldloc.s  0xC
0x1bab52  ldarg.1
0x1bab53  ldstr    aLayoutxml// "layoutxml"
0x1bab58  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1bab5d  callvirt instance string [mscorlib]System.Object::ToString()
0x1bab62  ldloc.s  0xB
0x1bab64  ldarg.2
0x1bab65  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetPopulatedLayoutJson(string fetchXml, string layoutXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1bab6a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1bab6f  ldarg.1
0x1bab70  ldstr    aFetchxml// "fetchxml"
0x1bab75  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1bab7a  brtrue.s loc_1BABA1
0x1bab7c  ldarg.1
0x1bab7d  ldstr    aOfflinesqlquer// "offlinesqlquery"
0x1bab82  ldarg.0
0x1bab83  ldloc.3
0x1bab84  ldloc.s  4
0x1bab86  ldarg.1
0x1bab87  ldstr    aFetchxml// "fetchxml"
0x1bab8c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1bab91  castclass [mscorlib]System.String
0x1bab96  ldarg.2
0x1bab97  call     instance string class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::PopulateOfflineSqlQueryAttribute(int32, int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1bab9c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1baba1  ldarg.0
0x1baba2  ldloc.2
0x1baba3  ldarg.2
0x1baba4  call     instance bool class Microsoft.Crm.ObjectModel.UserQueryServiceInternal`1<var<u1>>::NeedsSystemUserContextForFilterManagement(valuetype Microsoft.Crm.ObjectModel.SavedQueryType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1baba9  brfalse.s loc_1BABC9
0x1babab  ldarg.2
0x1babac  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1babb1  stloc.s  0xD
0x1babb3  ldarg.0
0x1babb4  ldarg.1
0x1babb5  ldarg.2
0x1babb6  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1babbb  leave.s  loc_1BABD1
0x1babbd  ldloc.s  0xD
0x1babbf  brfalse.s loc_1BABC8
0x1babc1  ldloc.s  0xD
0x1babc3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1babc8  endfinally
0x1babc9  ldarg.0
0x1babca  ldarg.1
0x1babcb  ldarg.2
0x1babcc  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1babd1  ldc.i4.s 0x10
0x1babd3  ldloc.2
0x1babd4  beq.s    loc_1BABDF
0x1babd6  ldc.i4   0x100
0x1babdb  ldloc.2
0x1babdc  beq.s    loc_1BABDF
0x1babde  ret
0x1babdf  ldloc.0
0x1babe0  ldstr    aFetchxml// "fetchxml"
0x1babe5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1babea  brfalse.s loc_1BABFA
0x1babec  ldloc.0
0x1babed  ldstr    aReturnedtypeco// "returnedtypecode"
0x1babf2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1babf7  brfalse.s loc_1BABFA
  ... truncated ...
```
