# Microsoft.Crm.ObjectModel.AppModuleService::RetrieveAppContext

- ea: `0x91820`
- end: `0x91dee`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::RetrieveAppContext`
- size: `1486`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x91820`
- `0x93c30`
- `0x93ca0`
- `0x94930`
- `0x949a0`
- `0x94b90`

## string_xrefs

- `0x91861`: `welcomepageid`
- `0x91a40`: `welcomepageid`
- `0x91a62`: `welcomepageid`
- `0x91a88`: `welcomepageid`
- `0x91b57`: `welcomepageid`
- `0x91b61`: `welcomepageid`
- `0x91c79`: `welcomepageid`
- `0x91c83`: `welcomepageid`
- `0x91849`: `componentstate`
- `0x91986`: `componentstate`
- `0x91b33`: `AppModuleService.RetrieveAppContext(): WelcomePage Webresource not found for AppModule [{0}:{1}] [{2}:{3}]`
- `0x91c55`: `AppModuleService.RetrieveAppContext(): Icon Webresource not found for AppModule [{0}:{1}] [{2}:{3}]`
- `0x91cd2`: `Error while retreiving components for App with id {0}`
- `0x91d22`: `AppModuleService.RetrieveAppContext(): Error while retreiving components [{0}:{1}]`
- `0x91daa`: `AppModuleService.RetrieveAppContext(): AppModule with [appmoduleid:{0}] not found, Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x91820  ldc.i4.s 0xA
0x91822  newarr   [mscorlib]System.String
0x91827  dup
0x91828  ldc.i4.0
0x91829  ldstr    aAppmoduleid// "appmoduleid"
0x9182e  stelem.ref
0x9182f  dup
0x91830  ldc.i4.1
0x91831  ldstr    aName// "name"
0x91836  stelem.ref
0x91837  dup
0x91838  ldc.i4.2
0x91839  ldstr    aDescription// "description"
0x9183e  stelem.ref
0x9183f  dup
0x91840  ldc.i4.3
0x91841  ldstr    aClienttype// "clienttype"
0x91846  stelem.ref
0x91847  dup
0x91848  ldc.i4.4
0x91849  ldstr    aComponentstate_0// "componentstate"
0x9184e  stelem.ref
0x9184f  dup
0x91850  ldc.i4.5
0x91851  ldstr    aModifiedon_0// "modifiedon"
0x91856  stelem.ref
0x91857  dup
0x91858  ldc.i4.6
0x91859  ldstr    aWebresourceid// "webresourceid"
0x9185e  stelem.ref
0x9185f  dup
0x91860  ldc.i4.7
0x91861  ldstr    aWelcomepageid// "welcomepageid"
0x91866  stelem.ref
0x91867  dup
0x91868  ldc.i4.8
0x91869  ldstr    aUrl// "url"
0x9186e  stelem.ref
0x9186f  dup
0x91870  ldc.i4.s 9
0x91872  ldstr    aUniquename// "uniquename"
0x91877  stelem.ref
0x91878  stloc.0
0x91879  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::.ctor()
0x9187e  stloc.1
0x9187f  ldnull
0x91880  stloc.2
0x91881  ldnull
0x91882  stloc.3
0x91883  ldarg.0
0x91884  ldstr    aAppmodule// "AppModule"
0x91889  ldarg.1
0x9188a  ldstr    aAppmoduleid// "appmoduleid"
0x9188f  ldloc.0
0x91890  ldloca.s 2
0x91892  ldarg.2
0x91893  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::TryRetrieveData(string platformName, valuetype [mscorlib]System.Guid objectId, string AttrNameObjectID, string[] columns, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection& collection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91898  brfalse  loc_91D6F
0x9189d  ldloc.2
0x9189e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x918a3  stloc.s  4
0x918a5  br       loc_91D49
0x918aa  ldloc.s  4
0x918ac  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x918b1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x918b6  stloc.s  5
0x918b8  ldloc.1
0x918b9  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x918be  ldloc.s  5
0x918c0  ldstr    aAppmoduleid// "appmoduleid"
0x918c5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x918ca  callvirt instance string [mscorlib]System.Object::ToString()
0x918cf  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_AppId(string)
0x918d4  ldloc.1
0x918d5  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x918da  ldloc.s  5
0x918dc  ldstr    aName// "name"
0x918e1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x918e6  callvirt instance string [mscorlib]System.Object::ToString()
0x918eb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_Title(string)
0x918f0  ldloc.1
0x918f1  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x918f6  ldloc.s  5
0x918f8  ldstr    aUniquename// "uniquename"
0x918fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91902  callvirt instance string [mscorlib]System.Object::ToString()
0x91907  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_UniqueName(string)
0x9190c  ldloc.1
0x9190d  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91912  ldloc.s  5
0x91914  ldstr    aClienttype// "clienttype"
0x91919  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9191e  unbox.any [mscorlib]System.Int32
0x91923  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_ClientType(int32)
0x91928  ldloc.1
0x91929  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x9192e  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_ClientType()
0x91933  ldc.i4.0
0x91934  bgt.s    loc_91942
0x91936  ldloc.1
0x91937  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x9193c  ldc.i4.2
0x9193d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_ClientType(int32)
0x91942  ldloc.s  5
0x91944  ldstr    aDescription// "description"
0x91949  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x9194e  brfalse.s loc_9196E
0x91950  ldloc.1
0x91951  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91956  ldloc.s  5
0x91958  ldstr    aDescription// "description"
0x9195d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91962  callvirt instance string [mscorlib]System.Object::ToString()
0x91967  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_Description(string)
0x9196c  br.s     loc_9197E
0x9196e  ldloc.1
0x9196f  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91974  ldsfld   string [mscorlib]System.String::Empty
0x91979  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_Description(string)
0x9197e  ldloc.1
0x9197f  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91984  ldloc.s  5
0x91986  ldstr    aComponentstate_0// "componentstate"
0x9198b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91990  unbox.any [mscorlib]System.Int32
0x91995  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_Status(int32)
0x9199a  ldloc.1
0x9199b  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x919a0  ldloc.s  5
0x919a2  ldstr    aModifiedon_0// "modifiedon"
0x919a7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x919ac  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x919b1  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UserOrUniversalTime()
0x919b6  stloc.s  7
0x919b8  ldloca.s 7
0x919ba  call     instance string [mscorlib]System.DateTime::ToString()
0x919bf  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_LastModifiedOn(string)
0x919c4  ldloc.s  5
0x919c6  ldstr    aUrl// "url"
0x919cb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x919d0  brfalse.s loc_919F0
0x919d2  ldloc.1
0x919d3  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x919d8  ldloc.s  5
0x919da  ldstr    aUrl// "url"
0x919df  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x919e4  callvirt instance string [mscorlib]System.Object::ToString()
0x919e9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_AppUrl(string)
0x919ee  br.s     loc_91A00
0x919f0  ldloc.1
0x919f1  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x919f6  ldsfld   string [mscorlib]System.String::Empty
0x919fb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::set_AppUrl(string)
0x91a00  ldarg.0
0x91a01  ldloc.s  5
0x91a03  call     instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::GetListOfWebResourceIds(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModule)
0x91a08  stloc.s  6
0x91a0a  ldarg.0
0x91a0b  ldloc.s  6
0x91a0d  ldarg.2
0x91a0e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppModuleService::GetWebResources(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> webResIdList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91a13  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x91a18  stloc.s  8
0x91a1a  br       loc_91C93
0x91a1f  ldloc.s  8
0x91a21  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x91a26  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x91a2b  stloc.s  9
0x91a2d  ldloc.s  9
0x91a2f  ldstr    aWebresourceid// "webresourceid"
0x91a34  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91a39  brfalse  loc_91C93
0x91a3e  ldloc.s  5
0x91a40  ldstr    aWelcomepageid// "welcomepageid"
0x91a45  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91a4a  brfalse  loc_91B2B
0x91a4f  ldloc.s  9
0x91a51  ldstr    aWebresourceid// "webresourceid"
0x91a56  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91a5b  callvirt instance string [mscorlib]System.Object::ToString()
0x91a60  ldloc.s  5
0x91a62  ldstr    aWelcomepageid// "welcomepageid"
0x91a67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91a6c  callvirt instance string [mscorlib]System.Object::ToString()
0x91a71  callvirt instance bool [mscorlib]System.String::Equals(string)
0x91a76  brfalse  loc_91B2B
0x91a7b  ldloc.1
0x91a7c  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91a81  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_welcomePageInfo()
0x91a86  ldloc.s  5
0x91a88  ldstr    aWelcomepageid// "welcomepageid"
0x91a8d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91a92  callvirt instance string [mscorlib]System.Object::ToString()
0x91a97  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_Guid(string)
0x91a9c  ldloc.s  9
0x91a9e  ldstr    aDisplayname_0// "displayname"
0x91aa3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91aa8  brfalse.s loc_91ACB
0x91aaa  ldloc.1
0x91aab  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91ab0  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_welcomePageInfo()
0x91ab5  ldloc.s  9
0x91ab7  ldstr    aDisplayname_0// "displayname"
0x91abc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91ac1  callvirt instance string [mscorlib]System.Object::ToString()
0x91ac6  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_DisplayName(string)
0x91acb  ldloc.s  9
0x91acd  ldstr    aName// "name"
0x91ad2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91ad7  brfalse.s loc_91AFA
0x91ad9  ldloc.1
0x91ada  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91adf  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_welcomePageInfo()
0x91ae4  ldloc.s  9
0x91ae6  ldstr    aName// "name"
0x91aeb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91af0  callvirt instance string [mscorlib]System.Object::ToString()
0x91af5  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_Name(string)
0x91afa  ldloc.s  9
0x91afc  ldstr    aWebresourcetyp// "webresourcetype"
0x91b01  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91b06  brfalse.s loc_91B71
0x91b08  ldloc.1
0x91b09  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91b0e  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_welcomePageInfo()
0x91b13  ldloc.s  9
0x91b15  ldstr    aWebresourcetyp// "webresourcetype"
0x91b1a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91b1f  unbox.any [mscorlib]System.Int32
0x91b24  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_WebResourceType(int32)
0x91b29  br.s     loc_91B71
0x91b2b  ldarg.2
0x91b2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x91b31  ldc.i4.s 0x47
0x91b33  ldstr    aAppmoduleservi_43// "AppModuleService.RetrieveAppContext(): "...
0x91b38  ldc.i4.4
0x91b39  newarr   [mscorlib]System.Object
0x91b3e  dup
0x91b3f  ldc.i4.0
0x91b40  ldstr    aAppmoduleid// "appmoduleid"
0x91b45  stelem.ref
0x91b46  dup
0x91b47  ldc.i4.1
0x91b48  ldloc.s  5
0x91b4a  ldstr    aAppmoduleid// "appmoduleid"
0x91b4f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91b54  stelem.ref
0x91b55  dup
0x91b56  ldc.i4.2
0x91b57  ldstr    aWelcomepageid// "welcomepageid"
0x91b5c  stelem.ref
0x91b5d  dup
0x91b5e  ldc.i4.3
0x91b5f  ldloc.s  5
0x91b61  ldstr    aWelcomepageid// "welcomepageid"
0x91b66  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91b6b  stelem.ref
0x91b6c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x91b71  ldloc.s  9
0x91b73  ldstr    aWebresourceid// "webresourceid"
0x91b78  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91b7d  callvirt instance string [mscorlib]System.Object::ToString()
0x91b82  ldloc.s  5
0x91b84  ldstr    aWebresourceid// "webresourceid"
0x91b89  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91b8e  callvirt instance string [mscorlib]System.Object::ToString()
0x91b93  callvirt instance bool [mscorlib]System.String::Equals(string)
0x91b98  brfalse  loc_91C4D
0x91b9d  ldloc.1
0x91b9e  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91ba3  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_webResourceInfo()
0x91ba8  ldloc.s  5
0x91baa  ldstr    aWebresourceid// "webresourceid"
0x91baf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91bb4  callvirt instance string [mscorlib]System.Object::ToString()
0x91bb9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_Guid(string)
0x91bbe  ldloc.s  9
0x91bc0  ldstr    aDisplayname_0// "displayname"
0x91bc5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91bca  brfalse.s loc_91BED
0x91bcc  ldloc.1
0x91bcd  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91bd2  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_webResourceInfo()
0x91bd7  ldloc.s  9
0x91bd9  ldstr    aDisplayname_0// "displayname"
0x91bde  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91be3  callvirt instance string [mscorlib]System.Object::ToString()
0x91be8  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_DisplayName(string)
0x91bed  ldloc.s  9
0x91bef  ldstr    aName// "name"
0x91bf4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91bf9  brfalse.s loc_91C1C
0x91bfb  ldloc.1
0x91bfc  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_appInfo()
0x91c01  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppInfo::get_webResourceInfo()
0x91c06  ldloc.s  9
0x91c08  ldstr    aName// "name"
0x91c0d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x91c12  callvirt instance string [mscorlib]System.Object::ToString()
0x91c17  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInfo::set_Name(string)
  ... truncated ...
```
