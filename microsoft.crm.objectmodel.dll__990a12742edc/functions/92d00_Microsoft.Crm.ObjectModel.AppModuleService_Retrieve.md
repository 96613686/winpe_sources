# Microsoft.Crm.ObjectModel.AppModuleService::Retrieve

- ea: `0x92d00`
- end: `0x92fc4`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::Retrieve`
- size: `708`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x25f80`
- `0x92d00`
- `0x969e0`

## string_xrefs

- `0x92d08`: `AppModuleService.Retrieve(): START`
- `0x92d20`: `AppModuleService.Retrieve(): [appmoduleid:{0}].`
- `0x92d7b`: `AppModuleService.Retrieve(): [appmoduleid:{0}], Feature [{1}] not enabled.`
- `0x92e00`: `AppModuleService.Retrieve(): [appmoduleid:{0}], User doesnt have [{1}] privilege on AppModule.`
- `0x92e90`: `AppModuleService.Retrieve(): [appmoduleid:{0}], User doesnt have [{1},{2}] privilege on AppModule.`
- `0x92f08`: `AppModuleService.Retrieve(): [appmoduleid:{0}], User's roles doesnt have any AppModules associated.`
- `0x92f7c`: `AppModuleService.Retrieve(): END`
- `0x92fa5`: `AppModuleService.Retrieve(): Exception ex: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x92d00  ldarg.3
0x92d01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92d06  ldc.i4.s 0x47
0x92d08  ldstr    aAppmoduleservi_60// "AppModuleService.Retrieve(): START"
0x92d0d  ldc.i4.0
0x92d0e  newarr   [mscorlib]System.Object
0x92d13  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92d18  ldarg.3
0x92d19  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92d1e  ldc.i4.s 0x47
0x92d20  ldstr    aAppmoduleservi_61// "AppModuleService.Retrieve(): [appmodule"...
0x92d25  ldc.i4.1
0x92d26  newarr   [mscorlib]System.Object
0x92d2b  dup
0x92d2c  ldc.i4.0
0x92d2d  ldarg.1
0x92d2e  brtrue.s loc_92D3B
0x92d30  ldloca.s 0
0x92d32  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92d38  ldloc.0
0x92d39  br.s     loc_92D46
0x92d3b  ldarg.1
0x92d3c  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x92d41  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x92d46  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92d4b  stelem.ref
0x92d4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92d51  ldarg.3
0x92d52  ldstr    aContext// "context"
0x92d57  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x92d5c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x92d61  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x92d66  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x92d6b  ldarg.3
0x92d6c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x92d71  brtrue.s loc_92DC5
0x92d73  ldarg.3
0x92d74  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92d79  ldc.i4.s 0x47
0x92d7b  ldstr    aAppmoduleservi_62// "AppModuleService.Retrieve(): [appmodule"...
0x92d80  ldc.i4.2
0x92d81  newarr   [mscorlib]System.Object
0x92d86  dup
0x92d87  ldc.i4.0
0x92d88  ldarg.1
0x92d89  brtrue.s loc_92D96
0x92d8b  ldloca.s 0
0x92d8d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92d93  ldloc.0
0x92d94  br.s     loc_92DA1
0x92d96  ldarg.1
0x92d97  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x92d9c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x92da1  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92da6  stelem.ref
0x92da7  dup
0x92da8  ldc.i4.1
0x92da9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x92dae  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x92db3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x92db8  stelem.ref
0x92db9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92dbe  ldarg.1
0x92dbf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker)
0x92dc4  throw
0x92dc5  ldarg.3
0x92dc6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x92dcb  ldstr    aAppmodule// "AppModule"
0x92dd0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x92dd5  stloc.1
0x92dd6  ldloc.1
0x92dd7  ldc.i4.1
0x92dd8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x92ddd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x92de2  stloc.2
0x92de3  ldarg.3
0x92de4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x92de9  ldloc.2
0x92dea  ldarg.3
0x92deb  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92df0  ldc.i4   0x80040220
0x92df5  bne.un.s loc_92E41
0x92df7  ldnull
0x92df8  ldarg.3
0x92df9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92dfe  ldc.i4.s 0x47
0x92e00  ldstr    aAppmoduleservi_63// "AppModuleService.Retrieve(): [appmodule"...
0x92e05  ldc.i4.2
0x92e06  newarr   [mscorlib]System.Object
0x92e0b  dup
0x92e0c  ldc.i4.0
0x92e0d  ldarg.1
0x92e0e  brtrue.s loc_92E1B
0x92e10  ldloca.s 0
0x92e12  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92e18  ldloc.0
0x92e19  br.s     loc_92E26
0x92e1b  ldarg.1
0x92e1c  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x92e21  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x92e26  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92e2b  stelem.ref
0x92e2c  dup
0x92e2d  ldc.i4.1
0x92e2e  ldc.i4.1
0x92e2f  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x92e34  stelem.ref
0x92e35  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92e3a  ldarg.1
0x92e3b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker)
0x92e40  throw
0x92e41  ldloc.1
0x92e42  ldc.i4.2
0x92e43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x92e48  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x92e4d  stloc.3
0x92e4e  ldloc.1
0x92e4f  ldc.i4.0
0x92e50  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x92e55  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x92e5a  stloc.s  4
0x92e5c  ldarg.3
0x92e5d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x92e62  ldloc.3
0x92e63  ldarg.3
0x92e64  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92e69  ldc.i4   0x80040220
0x92e6e  beq.s    loc_92E88
0x92e70  ldarg.3
0x92e71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x92e76  ldloc.s  4
0x92e78  ldarg.3
0x92e79  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92e7e  ldc.i4   0x80040220
0x92e83  bne.un   loc_92F74
0x92e88  ldarg.3
0x92e89  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92e8e  ldc.i4.s 0x47
0x92e90  ldstr    aAppmoduleservi_64// "AppModuleService.Retrieve(): [appmodule"...
0x92e95  ldc.i4.3
0x92e96  newarr   [mscorlib]System.Object
0x92e9b  dup
0x92e9c  ldc.i4.0
0x92e9d  ldarg.1
0x92e9e  brtrue.s loc_92EAB
0x92ea0  ldloca.s 0
0x92ea2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92ea8  ldloc.0
0x92ea9  br.s     loc_92EB6
0x92eab  ldarg.1
0x92eac  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x92eb1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x92eb6  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92ebb  stelem.ref
0x92ebc  dup
0x92ebd  ldc.i4.1
0x92ebe  ldc.i4.2
0x92ebf  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x92ec4  stelem.ref
0x92ec5  dup
0x92ec6  ldc.i4.2
0x92ec7  ldc.i4.0
0x92ec8  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x92ecd  stelem.ref
0x92ece  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92ed3  ldarg.0
0x92ed4  ldarg.3
0x92ed5  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsSystemAdministratorOrCustomizer(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92eda  brtrue   loc_92F74
0x92edf  ldarg.3
0x92ee0  call     valuetype [mscorlib]System.Guid[] Microsoft.Crm.Sdk.AppModuleCacheUtils::GetAppModuleIdsForUser(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92ee5  stloc.s  5
0x92ee7  ldloc.s  5
0x92ee9  ldlen
0x92eea  brtrue.s loc_92F60
0x92eec  ldarg.1
0x92eed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x92ef2  ldc.i4.1
0x92ef3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x92ef8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x92efd  stloc.s  6
0x92eff  ldnull
0x92f00  ldarg.3
0x92f01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92f06  ldc.i4.s 0x47
0x92f08  ldstr    aAppmoduleservi_65// "AppModuleService.Retrieve(): [appmodule"...
0x92f0d  ldc.i4.3
0x92f0e  newarr   [mscorlib]System.Object
0x92f13  dup
0x92f14  ldc.i4.0
0x92f15  ldarg.1
0x92f16  brtrue.s loc_92F23
0x92f18  ldloca.s 0
0x92f1a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92f20  ldloc.0
0x92f21  br.s     loc_92F2E
0x92f23  ldarg.1
0x92f24  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x92f29  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x92f2e  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x92f33  stelem.ref
0x92f34  dup
0x92f35  ldc.i4.1
0x92f36  ldc.i4.2
0x92f37  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x92f3c  stelem.ref
0x92f3d  dup
0x92f3e  ldc.i4.2
0x92f3f  ldc.i4.0
0x92f40  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType
0x92f45  stelem.ref
0x92f46  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92f4b  ldarg.3
0x92f4c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x92f51  ldloc.s  6
0x92f53  ldarg.3
0x92f54  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92f59  ldarg.1
0x92f5a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker)
0x92f5f  throw
0x92f60  ldarg.2
0x92f61  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x92f66  ldstr    aAppmoduleid// "appmoduleid"
0x92f6b  ldc.i4.8
0x92f6c  ldloc.s  5
0x92f6e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x92f73  pop
0x92f74  ldarg.3
0x92f75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92f7a  ldc.i4.s 0x47
0x92f7c  ldstr    aAppmoduleservi_66// "AppModuleService.Retrieve(): END"
0x92f81  ldc.i4.0
0x92f82  newarr   [mscorlib]System.Object
0x92f87  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92f8c  ldarg.0
0x92f8d  ldarg.1
0x92f8e  ldarg.2
0x92f8f  ldarg.3
0x92f90  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x92f95  stloc.s  7
0x92f97  leave.s  loc_92FC1
0x92f99  stloc.s  8
0x92f9b  ldloc.s  8
0x92f9d  ldarg.3
0x92f9e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92fa3  ldc.i4.s 0x47
0x92fa5  ldstr    aAppmoduleservi_67// "AppModuleService.Retrieve(): Exception "...
0x92faa  ldc.i4.1
0x92fab  newarr   [mscorlib]System.Object
0x92fb0  dup
0x92fb1  ldc.i4.0
0x92fb2  ldloc.s  8
0x92fb4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x92fb9  stelem.ref
0x92fba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92fbf  rethrow
0x92fc1  ldloc.s  7
0x92fc3  ret
```
