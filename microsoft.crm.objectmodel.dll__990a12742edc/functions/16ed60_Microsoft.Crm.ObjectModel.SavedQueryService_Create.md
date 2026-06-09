# Microsoft.Crm.ObjectModel.SavedQueryService::Create

- ea: `0x16ed60`
- end: `0x16ef7c`
- name: `Microsoft.Crm.ObjectModel.SavedQueryService::Create`
- size: `540`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x317f0`
- `0x16e340`
- `0x16ed60`
- `0x16ef80`
- `0x16f270`
- `0x16f750`
- `0x16fb40`
- `0x16fef0`
- `0x16ff20`

## string_xrefs

- `0x16ef27`: `layoutjson`
- `0x16ef02`: `fetchxml`
- `0x16ef0f`: `fetchxml`
- `0x16ef4a`: `fetchxml`
- `0x16eed4`: `layoutxml`
- `0x16ef2e`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x16ed60  ldarg.0
0x16ed61  ldarg.1
0x16ed62  ldc.i4.0
0x16ed63  ldnull
0x16ed64  ldarg.2
0x16ed65  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateSavedQuery(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedquery, bool isForUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16ed6a  ldarg.1
0x16ed6b  ldstr    aIscustomizable// "iscustomizable"
0x16ed70  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16ed75  brfalse.s loc_16ED88
0x16ed77  ldarg.1
0x16ed78  ldstr    aIscustomizable// "iscustomizable"
0x16ed7d  ldc.i4.1
0x16ed7e  box      [mscorlib]System.Boolean
0x16ed83  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16ed88  ldarg.1
0x16ed89  ldstr    aIsdefault// "isdefault"
0x16ed8e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16ed93  brfalse.s loc_16EDA6
0x16ed95  ldarg.1
0x16ed96  ldstr    aIsdefault// "isdefault"
0x16ed9b  ldc.i4.0
0x16ed9c  box      [mscorlib]System.Boolean
0x16eda1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16eda6  ldarg.1
0x16eda7  ldstr    aIsquickfindque// "isquickfindquery"
0x16edac  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16edb1  brfalse.s loc_16EDC4
0x16edb3  ldarg.1
0x16edb4  ldstr    aIsquickfindque// "isquickfindquery"
0x16edb9  ldc.i4.0
0x16edba  box      [mscorlib]System.Boolean
0x16edbf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16edc4  ldarg.0
0x16edc5  ldarg.1
0x16edc6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x16edcb  ldarg.2
0x16edcc  call     instance bool Microsoft.Crm.ObjectModel.SavedQueryService::doesIsCustomAttributeExists(string savedQueryPlatformName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16edd1  brfalse.s loc_16EDF1
0x16edd3  ldarg.1
0x16edd4  ldstr    aIscustom_0// "iscustom"
0x16edd9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16edde  brfalse.s loc_16EDF1
0x16ede0  ldarg.1
0x16ede1  ldstr    aIscustom_0// "iscustom"
0x16ede6  ldc.i4.1
0x16ede7  box      [mscorlib]System.Boolean
0x16edec  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16edf1  ldarg.0
0x16edf2  ldarg.1
0x16edf3  ldarg.2
0x16edf4  ldnull
0x16edf5  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateQuickFindSavedQueryCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x16edfa  ldarg.1
0x16edfb  ldstr    aQuerytype// "querytype"
0x16ee00  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16ee05  brtrue.s loc_16EE86
0x16ee07  ldc.i4   0x100
0x16ee0c  ldarg.1
0x16ee0d  ldstr    aQuerytype// "querytype"
0x16ee12  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ee17  unbox.any [mscorlib]System.Int32
0x16ee1c  beq.s    loc_16EE32
0x16ee1e  ldc.i4.s 0x10
0x16ee20  ldarg.1
0x16ee21  ldstr    aQuerytype// "querytype"
0x16ee26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ee2b  unbox.any [mscorlib]System.Int32
0x16ee30  bne.un.s loc_16EE86
0x16ee32  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x16ee37  ldstr    aSystemfilterli// "SystemFilterLimit"
0x16ee3c  callvirt T0x2B00019D
0x16ee41  stloc.0
0x16ee42  ldloc.0
0x16ee43  ldc.i4.0
0x16ee44  blt.s    loc_16EE86
0x16ee46  ldarg.0
0x16ee47  ldarg.1
0x16ee48  ldstr    aReturnedtypeco// "returnedtypecode"
0x16ee4d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ee52  unbox.any [mscorlib]System.Int32
0x16ee57  ldarg.1
0x16ee58  ldstr    aQuerytype// "querytype"
0x16ee5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ee62  unbox.any [mscorlib]System.Int32
0x16ee67  ldarg.2
0x16ee68  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.SavedQueryService::RetrievePublishedSavedQuery(int32 returnedTypeCode, int32 queryType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16ee6d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x16ee72  ldloc.0
0x16ee73  blt.s    loc_16EE86
0x16ee75  ldc.i4   0x8004027C
0x16ee7a  ldc.i4.0
0x16ee7b  newarr   [mscorlib]System.Object
0x16ee80  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x16ee85  throw
0x16ee86  ldarg.1
0x16ee87  ldstr    aIsdefault// "isdefault"
0x16ee8c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ee91  unbox.any [mscorlib]System.Boolean
0x16ee96  brfalse.s loc_16EED3
0x16ee98  ldarg.0
0x16ee99  ldarg.1
0x16ee9a  ldstr    aQuerytype// "querytype"
0x16ee9f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16eea4  unbox.any [mscorlib]System.Int32
0x16eea9  ldarg.1
0x16eeaa  ldstr    aReturnedtypeco// "returnedtypecode"
0x16eeaf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16eeb4  unbox.any [mscorlib]System.Int32
0x16eeb9  ldc.i4.0
0x16eeba  ldarg.2
0x16eebb  call     instance bool Microsoft.Crm.ObjectModel.SavedQueryService::ValidateDefaultTemplate(int32 queryType, int32 returnedTypeCode, bool isDefault, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16eec0  brtrue.s loc_16EED3
0x16eec2  ldc.i4   0x8004027D
0x16eec7  ldc.i4.0
0x16eec8  newarr   [mscorlib]System.Object
0x16eecd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x16eed2  throw
0x16eed3  ldarg.1
0x16eed4  ldstr    aLayoutxml// "layoutxml"
0x16eed9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16eede  brtrue.s loc_16EF49
0x16eee0  ldarg.1
0x16eee1  ldstr    aReturnedtypeco// "returnedtypecode"
0x16eee6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16eeeb  brtrue.s loc_16EEFF
0x16eeed  ldarg.1
0x16eeee  ldstr    aReturnedtypeco// "returnedtypecode"
0x16eef3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16eef8  unbox.any [mscorlib]System.Int32
0x16eefd  br.s     loc_16EF00
0x16eeff  ldc.i4.m1
0x16ef00  stloc.1
0x16ef01  ldarg.1
0x16ef02  ldstr    aFetchxml// "fetchxml"
0x16ef07  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16ef0c  brtrue.s loc_16EF20
0x16ef0e  ldarg.1
0x16ef0f  ldstr    aFetchxml// "fetchxml"
0x16ef14  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ef19  callvirt instance string [mscorlib]System.Object::ToString()
0x16ef1e  br.s     loc_16EF25
0x16ef20  ldsfld   string [mscorlib]System.String::Empty
0x16ef25  stloc.2
0x16ef26  ldarg.1
0x16ef27  ldstr    aLayoutjson// "layoutjson"
0x16ef2c  ldloc.2
0x16ef2d  ldarg.1
0x16ef2e  ldstr    aLayoutxml// "layoutxml"
0x16ef33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16ef38  callvirt instance string [mscorlib]System.Object::ToString()
0x16ef3d  ldloc.1
0x16ef3e  ldarg.2
0x16ef3f  call     string Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::GetPopulatedLayoutJson(string fetchXml, string layoutXml, int32 primaryEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16ef44  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16ef49  ldarg.1
0x16ef4a  ldstr    aFetchxml// "fetchxml"
0x16ef4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16ef54  brtrue.s loc_16EF6B
0x16ef56  ldarg.1
0x16ef57  ldstr    aOfflinesqlquer// "offlinesqlquery"
0x16ef5c  ldarg.0
0x16ef5d  ldarg.1
0x16ef5e  ldc.i4.0
0x16ef5f  ldnull
0x16ef60  ldarg.2
0x16ef61  call     instance string Microsoft.Crm.ObjectModel.SavedQueryService::AddOfflineSqlQueryAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, bool isUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16ef66  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16ef6b  ldarg.0
0x16ef6c  ldarg.1
0x16ef6d  ldarg.2
0x16ef6e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x16ef73  ldarg.0
0x16ef74  ldarg.1
0x16ef75  ldarg.2
0x16ef76  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::CreateRuntimeDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedQuery, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16ef7b  ret
```
