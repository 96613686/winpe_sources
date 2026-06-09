# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::DeprovisionReports

- ea: `0x1c470`
- end: `0x1c5d1`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::DeprovisionReports`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x91b0`
- `0x1c470`
- `0x31fe0`
- `0x32020`

## string_xrefs

- `0x1c515`: `Attempting to delete reports from the remote data center id: {0}`
- `0x1c5a2`: `Error while trying to delete reports from the remote data center id: {0}, report server: {1}. Details: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1c470  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x1c475  stloc.0
0x1c476  ldloc.0
0x1c477  ldarg.1
0x1c478  stfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c47d  ldloc.0
0x1c47e  ldloc.0
0x1c47f  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c484  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c489  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SrsUrl()
0x1c48e  newobj   instance void [System]System.Uri::.ctor(string)
0x1c493  stfld    class [System]System.Uri <>c__DisplayClass8_0::srsUri
0x1c498  ldloc.0
0x1c499  ldfld    class [System]System.Uri <>c__DisplayClass8_0::srsUri
0x1c49e  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1c4a3  stloc.1
0x1c4a4  ldloc.0
0x1c4a5  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c4aa  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c4af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1c4b4  ldloc.1
0x1c4b5  ldloc.0
0x1c4b6  ldftn    instance void <>c__DisplayClass8_0::<DeprovisionReports>b__0()
0x1c4bc  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c4c1  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x1c4c6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x1c4cb  ldloc.0
0x1c4cc  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c4d1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c4d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1c4db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetOrganizationRemoteDatacenterId(valuetype [mscorlib]System.Guid)
0x1c4e0  stloc.2
0x1c4e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c4e6  ldloc.2
0x1c4e7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c4ec  brfalse  loc_1C5D0
0x1c4f1  newobj   instance void <>c__DisplayClass8_1::.ctor()
0x1c4f6  stloc.3
0x1c4f7  ldloc.3
0x1c4f8  ldloc.0
0x1c4f9  stfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x1c4fe  ldloc.3
0x1c4ff  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x1c504  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c509  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c50e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1c513  ldc.i4.s 0xA
0x1c515  ldstr    aAttemptingToDe// "Attempting to delete reports from the r"...
0x1c51a  ldc.i4.1
0x1c51b  newarr   [mscorlib]System.Object
0x1c520  dup
0x1c521  ldc.i4.0
0x1c522  ldloc.2
0x1c523  box      [mscorlib]System.Guid
0x1c528  stelem.ref
0x1c529  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c52e  ldloc.3
0x1c52f  ldnull
0x1c530  stfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x1c535  ldloc.3
0x1c536  ldloc.2
0x1c537  ldloc.3
0x1c538  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x1c53d  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c542  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c547  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1c54c  call     class [System]System.Uri [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::GetReportServerUrl(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c551  stfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x1c556  ldloc.3
0x1c557  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x1c55c  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c561  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c566  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1c56b  ldloc.3
0x1c56c  ldfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x1c571  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x1c576  ldloc.3
0x1c577  ldftn    instance void <>c__DisplayClass8_1::<DeprovisionReports>b__1()
0x1c57d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c582  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x1c587  leave.s  loc_1C5D0
0x1c589  stloc.s  4
0x1c58b  ldloc.3
0x1c58c  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x1c591  ldfld    class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties <>c__DisplayClass8_0::properties
0x1c596  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x1c59b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1c5a0  ldc.i4.s 0xA
0x1c5a2  ldstr    aErrorWhileTryi// "Error while trying to delete reports fr"...
0x1c5a7  ldc.i4.3
0x1c5a8  newarr   [mscorlib]System.Object
0x1c5ad  dup
0x1c5ae  ldc.i4.0
0x1c5af  ldloc.2
0x1c5b0  box      [mscorlib]System.Guid
0x1c5b5  stelem.ref
0x1c5b6  dup
0x1c5b7  ldc.i4.1
0x1c5b8  ldloc.3
0x1c5b9  ldfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x1c5be  stelem.ref
0x1c5bf  dup
0x1c5c0  ldc.i4.2
0x1c5c1  ldloc.s  4
0x1c5c3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1c5c8  stelem.ref
0x1c5c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c5ce  leave.s  loc_1C5D0
0x1c5d0  ret
```
