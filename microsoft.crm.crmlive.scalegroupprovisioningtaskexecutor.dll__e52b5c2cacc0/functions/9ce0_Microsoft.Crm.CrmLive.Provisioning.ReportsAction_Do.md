# Microsoft.Crm.CrmLive.Provisioning.ReportsAction::Do

- ea: `0x9ce0`
- end: `0x9f3f`
- name: `Microsoft.Crm.CrmLive.Provisioning.ReportsAction::Do`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x91b0`
- `0x9c60`
- `0x9ce0`
- `0x30550`
- `0x305a0`

## string_xrefs

- `0x9e34`: `Attempting to configure report server for the remote data center id: {0}`
- `0x9eb6`: `Error trying to configure report server for the remote data center id: {0}, report server: {1}. Details: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x9ce0  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x9ce5  stloc.0
0x9ce6  ldloc.0
0x9ce7  ldarg.0
0x9ce8  stfld    class Microsoft.Crm.CrmLive.Provisioning.ReportsAction <>c__DisplayClass8_0::<>4__this
0x9ced  ldarg.0
0x9cee  ldarg.0
0x9cef  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9cf4  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9cf9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9cfe  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x9d03  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x9d08  stloc.1
0x9d09  ldloc.1
0x9d0a  ldarg.0
0x9d0b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9d10  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9d15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9d1a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x9d1f  ldloc.1
0x9d20  ldc.i4.0
0x9d21  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_IsRemoteReportServerConfigured(bool)
0x9d26  ldloc.1
0x9d27  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_IsBackedByXdb()
0x9d2c  stloc.s  5
0x9d2e  ldloca.s 5
0x9d30  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x9d35  brfalse.s loc_9D48
0x9d37  ldloc.1
0x9d38  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_IsBackedByXdb()
0x9d3d  stloc.s  5
0x9d3f  ldloca.s 5
0x9d41  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x9d46  br.s     loc_9D49
0x9d48  ldc.i4.0
0x9d49  stloc.2
0x9d4a  ldloc.0
0x9d4b  ldloc.2
0x9d4c  brtrue.s loc_9D65
0x9d4e  ldarg.0
0x9d4f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9d54  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9d59  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SrsUrl()
0x9d5e  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IIsUtility::IsLocalUrl(string)
0x9d63  br.s     loc_9D66
0x9d65  ldc.i4.0
0x9d66  stfld    bool <>c__DisplayClass8_0::grantNetworkServiceAccess
0x9d6b  ldarg.0
0x9d6c  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9d71  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9d76  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SrsUrl()
0x9d7b  newobj   instance void [System]System.Uri::.ctor(string)
0x9d80  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x9d85  stloc.3
0x9d86  ldarg.0
0x9d87  call     instance string Microsoft.Crm.CrmLive.Provisioning.ReportsAction::get_ReportingPath()
0x9d8c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9d91  brfalse.s loc_9D9F
0x9d93  ldarg.0
0x9d94  call     instance string Microsoft.Crm.CrmLive.Provisioning.ReportsAction::get_ReportingPath()
0x9d99  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9d9e  throw
0x9d9f  ldloc.0
0x9da0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x9da5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x9daa  ldarg.0
0x9dab  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9db0  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9db5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9dba  call     class [System]System.Uri [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::GetReportServerUrl(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9dbf  stfld    class [System]System.Uri <>c__DisplayClass8_0::localSrsUrl
0x9dc4  ldarg.0
0x9dc5  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9dca  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9dcf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9dd4  ldloc.3
0x9dd5  ldloc.0
0x9dd6  ldftn    instance void <>c__DisplayClass8_0::<Do>b__0()
0x9ddc  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x9de1  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x9de6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x9deb  ldarg.0
0x9dec  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9df1  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9df6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9dfb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetOrganizationRemoteDatacenterId(valuetype [mscorlib]System.Guid)
0x9e00  stloc.s  4
0x9e02  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9e07  ldloc.s  4
0x9e09  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9e0e  brfalse  loc_9EE6
0x9e13  newobj   instance void <>c__DisplayClass8_1::.ctor()
0x9e18  stloc.s  6
0x9e1a  ldloc.s  6
0x9e1c  ldloc.0
0x9e1d  stfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x9e22  ldarg.0
0x9e23  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9e28  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9e2d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9e32  ldc.i4.s 0xA
0x9e34  ldstr    aAttemptingToCo// "Attempting to configure report server f"...
0x9e39  ldc.i4.1
0x9e3a  newarr   [mscorlib]System.Object
0x9e3f  dup
0x9e40  ldc.i4.0
0x9e41  ldloc.s  4
0x9e43  box      [mscorlib]System.Guid
0x9e48  stelem.ref
0x9e49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9e4e  ldloc.s  6
0x9e50  ldnull
0x9e51  stfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x9e56  ldloc.s  6
0x9e58  ldloc.s  4
0x9e5a  ldarg.0
0x9e5b  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9e60  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9e65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9e6a  call     class [System]System.Uri [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::GetReportServerUrl(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9e6f  stfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x9e74  ldarg.0
0x9e75  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9e7a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9e7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9e84  ldloc.3
0x9e85  ldloc.s  6
0x9e87  ldftn    instance void <>c__DisplayClass8_1::<Do>b__1()
0x9e8d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x9e92  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x9e97  ldloc.1
0x9e98  ldc.i4.1
0x9e99  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_IsRemoteReportServerConfigured(bool)
0x9e9e  leave.s  loc_9EE6
0x9ea0  stloc.s  7
0x9ea2  ldloc.s  7
0x9ea4  ldarg.0
0x9ea5  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9eaa  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9eaf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9eb4  ldc.i4.s 0xA
0x9eb6  ldstr    aErrorTryingToC// "Error trying to configure report server"...
0x9ebb  ldc.i4.3
0x9ebc  newarr   [mscorlib]System.Object
0x9ec1  dup
0x9ec2  ldc.i4.0
0x9ec3  ldloc.s  4
0x9ec5  box      [mscorlib]System.Guid
0x9eca  stelem.ref
0x9ecb  dup
0x9ecc  ldc.i4.1
0x9ecd  ldloc.s  6
0x9ecf  ldfld    class [System]System.Uri <>c__DisplayClass8_1::remoteSrsUrl
0x9ed4  stelem.ref
0x9ed5  dup
0x9ed6  ldc.i4.2
0x9ed7  ldloc.s  7
0x9ed9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x9ede  stelem.ref
0x9edf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9ee4  leave.s  loc_9EE6
0x9ee6  ldarg.0
0x9ee7  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9eec  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9ef1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9ef6  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ReportsUtility::MarkReportsPublishedForOrganization(valuetype [mscorlib]System.Guid)
0x9efb  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x9f00  ldloc.1
0x9f01  call     instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData)
0x9f06  ldarg.0
0x9f07  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9f0c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9f11  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9f16  ldloc.3
0x9f17  ldarg.0
0x9f18  ldftn    instance void Microsoft.Crm.CrmLive.Provisioning.ReportsAction::<Do>b__8_2()
0x9f1e  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x9f23  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.ReportsActionUtility::PerformReportsActionWithRetry(valuetype [mscorlib]System.Guid, string, class [mscorlib]System.Action)
0x9f28  ldarg.0
0x9f29  ldarg.0
0x9f2a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9f2f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9f34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9f39  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x9f3e  ret
```
