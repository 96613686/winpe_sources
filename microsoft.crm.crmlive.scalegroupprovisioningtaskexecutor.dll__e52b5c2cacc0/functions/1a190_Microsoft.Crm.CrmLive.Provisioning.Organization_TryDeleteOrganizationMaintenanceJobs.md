# Microsoft.Crm.CrmLive.Provisioning.Organization::TryDeleteOrganizationMaintenanceJobs

- ea: `0x1a190`
- end: `0x1a241`
- name: `Microsoft.Crm.CrmLive.Provisioning.Organization::TryDeleteOrganizationMaintenanceJobs`
- size: `177`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x181b0`
- `0x18550`
- `0x192e0`
- `0x194f0`

## callees

- `0x1a190`

## string_xrefs

- `0x1a1b4`: `Failed to delete organization maintenance jobs in primary dc, but ignored. Exception: {0}`
- `0x1a20e`: `Failed to delete organization maintenance jobs in secondary dc, but ignored. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a190  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1a195  stloc.0
0x1a196  call     class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x1a19b  stloc.1
0x1a19c  ldloc.0
0x1a19d  ldarg.0
0x1a19e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetDatacenterId(valuetype [mscorlib]System.Guid)
0x1a1a3  stloc.2
0x1a1a4  ldloc.1
0x1a1a5  ldarg.0
0x1a1a6  ldloc.2
0x1a1a7  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::DeleteJobs(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a1ac  leave.s  loc_1A1E4
0x1a1ae  stloc.3
0x1a1af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a1b4  ldstr    aFailedToDelete_0// "Failed to delete organization maintenan"...
0x1a1b9  ldc.i4.1
0x1a1ba  newarr   [mscorlib]System.Object
0x1a1bf  dup
0x1a1c0  ldc.i4.0
0x1a1c1  ldloc.3
0x1a1c2  stelem.ref
0x1a1c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a1c8  stloc.s  4
0x1a1ca  ldloc.s  4
0x1a1cc  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1a1d1  ldloc.3
0x1a1d2  ldarg.0
0x1a1d3  ldc.i4.s 0xA
0x1a1d5  ldloc.s  4
0x1a1d7  ldc.i4.0
0x1a1d8  newarr   [mscorlib]System.Object
0x1a1dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a1e2  leave.s  loc_1A1E4
0x1a1e4  nop
0x1a1e5  ldloc.0
0x1a1e6  ldarg.0
0x1a1e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetSecondaryDatacenterId(valuetype [mscorlib]System.Guid)
0x1a1ec  stloc.s  5
0x1a1ee  ldloc.s  5
0x1a1f0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a1f5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a1fa  brfalse.s loc_1A205
0x1a1fc  ldloc.1
0x1a1fd  ldarg.0
0x1a1fe  ldloc.s  5
0x1a200  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::DeleteJobs(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a205  leave.s  loc_1A240
0x1a207  stloc.s  6
0x1a209  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a20e  ldstr    aFailedToDelete_1// "Failed to delete organization maintenan"...
0x1a213  ldc.i4.1
0x1a214  newarr   [mscorlib]System.Object
0x1a219  dup
0x1a21a  ldc.i4.0
0x1a21b  ldloc.s  6
0x1a21d  stelem.ref
0x1a21e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a223  stloc.s  7
0x1a225  ldloc.s  7
0x1a227  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1a22c  ldloc.s  6
0x1a22e  ldarg.0
0x1a22f  ldc.i4.s 0xA
0x1a231  ldloc.s  7
0x1a233  ldc.i4.0
0x1a234  newarr   [mscorlib]System.Object
0x1a239  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a23e  leave.s  loc_1A240
0x1a240  ret
```
