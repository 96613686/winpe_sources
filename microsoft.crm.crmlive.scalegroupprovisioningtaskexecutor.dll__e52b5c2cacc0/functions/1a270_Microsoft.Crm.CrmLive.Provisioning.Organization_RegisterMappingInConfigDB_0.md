# Microsoft.Crm.CrmLive.Provisioning.Organization::RegisterMappingInConfigDB_0

- ea: `0x1a270`
- end: `0x1a370`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::RegisterMappingInConfigDB_0`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x194f0`
- `0x1a250`

## callees

- `0x1a270`

## string_xrefs

- `0x1a28a`: `RegisterMappingInConfigDB(organizationId={0}, availability group ={1}, primarySqlServer={2}, secondarySqlServer={3}, scaleGroupId={4}, storageGroupId={5}, reportServerUrl={6},datacenterId={7}`
- `0x1a2da`: `Update org table entry`

## pseudocode

```c

```

## disassembly

```asm
0x1a270  ldarg.s  8
0x1a272  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a277  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a27c  brfalse.s loc_1A28A
0x1a27e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x1a283  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x1a288  starg.s  8
0x1a28a  ldstr    aRegistermappin// "RegisterMappingInConfigDB(organizationI"...
0x1a28f  ldc.i4.8
0x1a290  newarr   [mscorlib]System.Object
0x1a295  dup
0x1a296  ldc.i4.0
0x1a297  ldarg.0
0x1a298  box      [mscorlib]System.Guid
0x1a29d  stelem.ref
0x1a29e  dup
0x1a29f  ldc.i4.1
0x1a2a0  ldarg.1
0x1a2a1  stelem.ref
0x1a2a2  dup
0x1a2a3  ldc.i4.2
0x1a2a4  ldarg.2
0x1a2a5  stelem.ref
0x1a2a6  dup
0x1a2a7  ldc.i4.3
0x1a2a8  ldarg.3
0x1a2a9  stelem.ref
0x1a2aa  dup
0x1a2ab  ldc.i4.4
0x1a2ac  ldarg.s  4
0x1a2ae  box      [mscorlib]System.Guid
0x1a2b3  stelem.ref
0x1a2b4  dup
0x1a2b5  ldc.i4.5
0x1a2b6  ldarg.s  5
0x1a2b8  box      [mscorlib]System.Guid
0x1a2bd  stelem.ref
0x1a2be  dup
0x1a2bf  ldc.i4.6
0x1a2c0  ldarg.s  6
0x1a2c2  stelem.ref
0x1a2c3  dup
0x1a2c4  ldc.i4.7
0x1a2c5  ldarg.s  8
0x1a2c7  box      [mscorlib]System.Guid
0x1a2cc  stelem.ref
0x1a2cd  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace::.ctor(string, object[])
0x1a2d2  stloc.0
0x1a2d3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x1a2d8  stloc.1
0x1a2d9  ldloc.0
0x1a2da  ldstr    aUpdateOrgTable// "Update org table entry"
0x1a2df  ldc.i4.0
0x1a2e0  newarr   [mscorlib]System.Object
0x1a2e5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x1a2ea  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1a2ef  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x1a2f4  stloc.2
0x1a2f5  ldloc.2
0x1a2f6  ldarg.0
0x1a2f7  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x1a2fc  ldloc.2
0x1a2fd  ldarg.2
0x1a2fe  ldarg.s  7
0x1a300  call     string [Microsoft.Crm.DatabaseInstaller.Common]Microsoft.Crm.DatabaseInstaller.Common.SharedDatabaseUtility::GetConnectionString(string, string)
0x1a305  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ConnectionString(string)
0x1a30a  ldloc.2
0x1a30b  ldarg.3
0x1a30c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_MirroredSqlServerName(string)
0x1a311  ldloc.2
0x1a312  ldarg.s  6
0x1a314  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SrsUrl(string)
0x1a319  ldloc.2
0x1a31a  ldarg.s  4
0x1a31c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x1a321  ldloc.2
0x1a322  ldarg.s  5
0x1a324  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_StorageGroupId(valuetype [mscorlib]System.Guid)
0x1a329  ldloc.2
0x1a32a  ldarg.1
0x1a32b  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_AvailabilityGroupName(string)
0x1a330  ldloc.2
0x1a331  ldarg.2
0x1a332  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_SqlServerName(string)
0x1a337  ldloc.2
0x1a338  ldarg.s  7
0x1a33a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_DatabaseName(string)
0x1a33f  ldloc.2
0x1a340  ldarg.s  8
0x1a342  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x1a347  ldloc.2
0x1a348  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Update(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x1a34d  leave.s  loc_1A359
0x1a34f  ldloc.1
0x1a350  brfalse.s loc_1A358
0x1a352  ldloc.1
0x1a353  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a358  endfinally
0x1a359  leave.s  loc_1A36F
0x1a35b  stloc.3
0x1a35c  ldloc.0
0x1a35d  ldloc.3
0x1a35e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Fail(class [mscorlib]System.Exception)
0x1a363  rethrow
0x1a365  ldloc.0
0x1a366  brfalse.s loc_1A36E
0x1a368  ldloc.0
0x1a369  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a36e  endfinally
0x1a36f  ret
```
