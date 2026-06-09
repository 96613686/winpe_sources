# Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::Do

- ea: `0x11b70`
- end: `0x11da4`
- name: `Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::Do`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x7020`
- `0x91b0`
- `0x92b0`
- `0x9310`
- `0x9330`
- `0x9350`
- `0x9410`
- `0x11b70`
- `0x11db0`

## string_xrefs

- `0x11b9d`: `ProvisionUpdateLifeCycleDo`
- `0x11c1f`: `Not changing organization lifecycle status because org {0} is already in the Enabled State`
- `0x11d52`: `OrganizationDatabaseLocationService.MakeAvailableForRestore() error:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x11b70  ldarg.0
0x11b71  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11b76  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11b7b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x11b80  stloc.0
0x11b81  ldarg.0
0x11b82  ldarg.0
0x11b83  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11b88  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11b8d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11b92  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x11b97  ldarg.0
0x11b98  call     instance void Microsoft.Crm.CrmLive.Provisioning.UpdateLifecycleAction::CreateOrganizationLifecycleEntryIfDoesNotExist()
0x11b9d  ldstr    aProvisionupdat// "ProvisionUpdateLifeCycleDo"
0x11ba2  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::.ctor(string)
0x11ba7  stloc.2
0x11ba8  ldloc.2
0x11ba9  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext)
0x11bae  stloc.3
0x11baf  ldloc.3
0x11bb0  ldloc.0
0x11bb1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::GetOrganizationLifecycleStatus(string)
0x11bb6  stloc.1
0x11bb7  leave.s  loc_11BBE
0x11bb9  pop
0x11bba  ldc.i4.0
0x11bbb  stloc.1
0x11bbc  leave.s  loc_11BBE
0x11bbe  ldloc.1
0x11bbf  ldc.i4.7
0x11bc0  beq.s    loc_11C0D
0x11bc2  ldc.i4.1
0x11bc3  stloc.s  4
0x11bc5  ldarg.0
0x11bc6  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11bcb  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_EnableInOrgLifecycle()
0x11bd0  brfalse.s loc_11BD5
0x11bd2  ldc.i4.7
0x11bd3  stloc.s  4
0x11bd5  ldarg.0
0x11bd6  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11bdb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11be0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x11be5  ldc.i4.8
0x11be6  bne.un.s loc_11BEC
0x11be8  ldc.i4.s 0xC
0x11bea  stloc.s  4
0x11bec  ldloc.2
0x11bed  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::BeginTransaction()
0x11bf2  ldloc.3
0x11bf3  ldloc.s  4
0x11bf5  ldloc.1
0x11bf6  ldloc.0
0x11bf7  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::SwitchOrganizationLifecycleStatus(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus, string)
0x11bfc  ldloc.2
0x11bfd  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::CommitTransaction()
0x11c02  leave.s  loc_11C53
0x11c04  pop
0x11c05  ldloc.2
0x11c06  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.CrmLiveContext::RollbackTransaction()
0x11c0b  rethrow
0x11c0d  ldarg.0
0x11c0e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c13  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11c18  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11c1d  ldc.i4.s 0xA
0x11c1f  ldstr    aNotChangingOrg// "Not changing organization lifecycle sta"...
0x11c24  ldc.i4.1
0x11c25  newarr   [mscorlib]System.Object
0x11c2a  dup
0x11c2b  ldc.i4.0
0x11c2c  ldarg.0
0x11c2d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c32  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11c37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11c3c  box      [mscorlib]System.Guid
0x11c41  stelem.ref
0x11c42  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11c47  leave.s  loc_11C53
0x11c49  ldloc.2
0x11c4a  brfalse.s loc_11C52
0x11c4c  ldloc.2
0x11c4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11c52  endfinally
0x11c53  ldarg.0
0x11c54  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c59  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11c5e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11c63  ldarg.0
0x11c64  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c69  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11c6e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x11c73  ldc.i4.8
0x11c74  ceq
0x11c76  ldc.i4.0
0x11c77  ceq
0x11c79  call     void Microsoft.Crm.CrmLive.Provisioning.EnableOrganizationAction::EnableAsyncProcessing(valuetype [mscorlib]System.Guid organizationId, bool enabled)
0x11c7e  ldarg.0
0x11c7f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c84  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyCode()
0x11c89  brfalse.s loc_11D07
0x11c8b  ldarg.0
0x11c8c  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c91  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencyName()
0x11c96  brfalse.s loc_11D07
0x11c98  ldarg.0
0x11c99  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11c9e  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_CurrencySymbol()
0x11ca3  brfalse.s loc_11D07
0x11ca5  ldarg.0
0x11ca6  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11cab  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_EnableInOrgLifecycle()
0x11cb0  brfalse.s loc_11D07
0x11cb2  ldarg.0
0x11cb3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11cb8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11cbd  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x11cc2  ldc.i4.8
0x11cc3  beq.s    loc_11D07
0x11cc5  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x11cca  stloc.s  5
0x11ccc  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ConfigurationCompletedRequest::.ctor()
0x11cd1  stloc.s  6
0x11cd3  ldloc.s  6
0x11cd5  ldarg.0
0x11cd6  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11cdb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11ce0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11ce5  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ConfigurationCompletedRequest::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x11cea  ldloc.s  5
0x11cec  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x11cf1  ldloc.s  6
0x11cf3  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceResponseMessage [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::Execute(class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ServiceRequestMessage)
0x11cf8  pop
0x11cf9  leave.s  loc_11D07
0x11cfb  ldloc.s  5
0x11cfd  brfalse.s loc_11D06
0x11cff  ldloc.s  5
0x11d01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11d06  endfinally
0x11d07  ldarg.0
0x11d08  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11d0d  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x11d12  brfalse.s loc_11D8D
0x11d14  ldarg.0
0x11d15  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11d1a  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_EnableInOrgLifecycle()
0x11d1f  brfalse.s loc_11D8D
0x11d21  ldarg.0
0x11d22  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11d27  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11d2c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Type()
0x11d31  ldc.i4.8
0x11d32  beq.s    loc_11D8D
0x11d34  call     T0x2B00001A
0x11d39  ldarg.0
0x11d3a  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11d3f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11d44  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11d49  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::MakeAvailableForRestore(valuetype [mscorlib]System.Guid)
0x11d4e  leave.s  loc_11D8D
0x11d50  stloc.s  7
0x11d52  ldstr    aOrganizationda_1// "OrganizationDatabaseLocationService.Mak"...
0x11d57  ldc.i4.1
0x11d58  newarr   [mscorlib]System.Object
0x11d5d  dup
0x11d5e  ldc.i4.0
0x11d5f  ldloc.s  7
0x11d61  callvirt instance string [mscorlib]System.Exception::get_Message()
0x11d66  stelem.ref
0x11d67  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string, object[])
0x11d6c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x11d71  ldstr    aSpartanenviron// "SpartanEnvironment"
0x11d76  ldc.i4.1
0x11d77  callvirt T0x2B000011
0x11d7c  ldstr    aTest// "test"
0x11d81  ldc.i4.5
0x11d82  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x11d87  brtrue.s loc_11D8B
0x11d89  rethrow
0x11d8b  leave.s  loc_11D8D
0x11d8d  ldarg.0
0x11d8e  ldarg.0
0x11d8f  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x11d94  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x11d99  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x11d9e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x11da3  ret
```
