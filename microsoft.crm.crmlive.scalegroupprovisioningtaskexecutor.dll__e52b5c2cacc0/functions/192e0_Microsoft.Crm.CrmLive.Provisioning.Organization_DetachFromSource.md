# Microsoft.Crm.CrmLive.Provisioning.Organization::DetachFromSource

- ea: `0x192e0`
- end: `0x19405`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::DetachFromSource`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x12dc0`
- `0x19280`

## callees

- `0x192e0`
- `0x1a190`
- `0x1c250`
- `0x1c3b0`

## string_xrefs

- `0x19341`: `Detach -- Marking LastTaskStatus=OrganizationTaskStatus.Started`
- `0x19391`: `DetachDeleteReport`
- `0x193c5`: `DetachDeleteReport`

## pseudocode

```c

```

## disassembly

```asm
0x192e0  ldarg.1
0x192e1  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminContext)
0x192e6  stloc.0
0x192e7  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x192ec  stloc.1
0x192ed  ldstr    aAdminApiDetach// "Admin.Api.DetachFromSource(data.name={0"...
0x192f2  ldc.i4.3
0x192f3  newarr   [mscorlib]System.Object
0x192f8  dup
0x192f9  ldc.i4.0
0x192fa  ldarg.2
0x192fb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_New()
0x19300  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiData::get_Name()
0x19305  stelem.ref
0x19306  dup
0x19307  ldc.i4.1
0x19308  ldarg.3
0x19309  stelem.ref
0x1930a  dup
0x1930b  ldc.i4.2
0x1930c  ldarg.s  4
0x1930e  stelem.ref
0x1930f  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.AdminApiTrace::.ctor(string, object[])
0x19314  stloc.2
0x19315  ldloc.2
0x19316  ldstr    aDetachAssertTh// "Detach -- assert that org {0} is disabl"...
0x1931b  ldc.i4.1
0x1931c  newarr   [mscorlib]System.Object
0x19321  dup
0x19322  ldc.i4.0
0x19323  ldarg.2
0x19324  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19329  box      [mscorlib]System.Guid
0x1932e  stelem.ref
0x1932f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19334  ldloc.0
0x19335  ldarg.2
0x19336  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x1933b  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::AssertDisabled(valuetype [mscorlib]System.Guid)
0x19340  ldloc.2
0x19341  ldstr    aDetachMarkingL// "Detach -- Marking LastTaskStatus=Organi"...
0x19346  ldc.i4.0
0x19347  newarr   [mscorlib]System.Object
0x1934c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x19351  ldloc.0
0x19352  ldarg.2
0x19353  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19358  ldc.i4.1
0x19359  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationService::SetLastTaskStatus(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationTaskStatus)
0x1935e  ldarg.2
0x1935f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OldScaleGroup()
0x19364  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19369  ldarg.2
0x1936a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_NewScaleGroup()
0x1936f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_Id()
0x19374  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19379  brfalse.s loc_19386
0x1937b  ldarg.2
0x1937c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x19381  call     void Microsoft.Crm.CrmLive.Provisioning.Organization::TryDeleteOrganizationMaintenanceJobs(valuetype [mscorlib]System.Guid organizationId)
0x19386  ldarg.2
0x19387  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x1938c  ldstr    aOrganization// "Organization"
0x19391  ldstr    aDetachdeletere// "DetachDeleteReport"
0x19396  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateStartEntry(valuetype [mscorlib]System.Guid, string, string)
0x1939b  ldarg.2
0x1939c  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_MoveSG()
0x193a1  brfalse.s loc_193BA
0x193a3  ldloc.1
0x193a4  ldarg.2
0x193a5  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_UniqueName()
0x193aa  ldarg.2
0x193ab  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OldScaleGroup()
0x193b0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x193b5  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::DeleteReports(string organizationUniqueName, string reportsUri)
0x193ba  ldarg.2
0x193bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_OrganizationId()
0x193c0  ldstr    aOrganization// "Organization"
0x193c5  ldstr    aDetachdeletere// "DetachDeleteReport"
0x193ca  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEndEntry(valuetype [mscorlib]System.Guid, string, string)
0x193cf  ldloc.2
0x193d0  ldstr    aDetachDb0// "Detach -- db={0}"
0x193d5  ldc.i4.1
0x193d6  newarr   [mscorlib]System.Object
0x193db  dup
0x193dc  ldc.i4.0
0x193dd  ldarg.2
0x193de  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationMoveData::get_Old()
0x193e3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.Api.OrganizationDBData::get_DBName()
0x193e8  stelem.ref
0x193e9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Comment(string, object[])
0x193ee  leave.s  loc_19404
0x193f0  stloc.3
0x193f1  ldloc.2
0x193f2  ldloc.3
0x193f3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceContext::Fail(class [mscorlib]System.Exception)
0x193f8  rethrow
0x193fa  ldloc.2
0x193fb  brfalse.s loc_19403
0x193fd  ldloc.2
0x193fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19403  endfinally
0x19404  ret
```
