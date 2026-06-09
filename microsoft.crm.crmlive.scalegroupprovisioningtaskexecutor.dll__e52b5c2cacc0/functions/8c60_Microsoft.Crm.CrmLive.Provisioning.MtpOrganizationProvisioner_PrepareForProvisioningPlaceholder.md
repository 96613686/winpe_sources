# Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::PrepareForProvisioningPlaceholder

- ea: `0x8c60`
- end: `0x8ed1`
- name: `Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::PrepareForProvisioningPlaceholder`
- size: `625`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x870`
- `0x8f0`
- `0x8c60`
- `0x8f00`
- `0x8f60`
- `0x8fc0`
- `0x9000`
- `0x91b0`
- `0x91d0`
- `0x91e0`
- `0x92f0`
- `0x9410`
- `0x9440`
- `0x94f0`
- `0x1be10`
- `0x1c3b0`

## string_xrefs

- `0x8d81`: `Xdb Organization template not found for Azure SQL DB Server: '{0}', ScaleGroupId: {1}, Lcid: {2}, TemplateIdentifier: {3}, while provisioning organization (id): '{4}'`
- `0x8e00`: `Organization template not found: '{0}'. ScaleGroupId: {1}, Lcid: {2}, While provisioning organization '{3}'`

## pseudocode

```c

```

## disassembly

```asm
0x8c60  ldarg.1
0x8c61  ldstr    aOrganizationpr// "organizationProperties"
0x8c66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c6b  ldarg.1
0x8c6c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8c71  ldstr    aOrganizationpr_0// "organizationProperties.OrganizationData"
0x8c76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c7b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8c80  stloc.0
0x8c81  ldnull
0x8c82  stloc.1
0x8c83  ldnull
0x8c84  stloc.2
0x8c85  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x8c8a  stloc.3
0x8c8b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x8c90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x8c95  stloc.0
0x8c96  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::CreatePlatformClient()
0x8c9b  stloc.s  4
0x8c9d  ldloc.s  4
0x8c9f  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x8ca4  ldloc.0
0x8ca5  ldarg.1
0x8ca6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8cab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x8cb0  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::PrepareForProvisioningPlaceholder(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8cb5  stloc.1
0x8cb6  leave.s  loc_8CC4
0x8cb8  ldloc.s  4
0x8cba  brfalse.s loc_8CC3
0x8cbc  ldloc.s  4
0x8cbe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8cc3  endfinally
0x8cc4  ldloc.1
0x8cc5  callvirt instance valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderStatus [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_Status()
0x8cca  ldc.i4.2
0x8ccb  bne.un.s loc_8CE2
0x8ccd  ldarg.2
0x8cce  ldc.i4.0
0x8ccf  stind.i1
0x8cd0  ldloc.1
0x8cd1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_QueueItemId()
0x8cd6  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x8cdb  stloc.s  5
0x8cdd  leave    loc_8ECE
0x8ce2  ldloc.1
0x8ce3  callvirt instance valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderStatus [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_Status()
0x8ce8  ldc.i4.1
0x8ce9  bne.un.s loc_8CF0
0x8ceb  ldarg.2
0x8cec  ldc.i4.1
0x8ced  stind.i1
0x8cee  br.s     loc_8D19
0x8cf0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8cf5  ldstr    aUnexpectedPrep// "Unexpected PrepareForProvisioningPlaceh"...
0x8cfa  ldc.i4.1
0x8cfb  newarr   [mscorlib]System.Object
0x8d00  dup
0x8d01  ldc.i4.0
0x8d02  ldloc.1
0x8d03  callvirt instance valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderStatus [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_Status()
0x8d08  box      [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderStatus
0x8d0d  stelem.ref
0x8d0e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d13  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8d18  throw
0x8d19  ldarg.1
0x8d1a  ldloc.1
0x8d1b  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage[] [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_Packages()
0x8d20  call     class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::ToProvisioningSolutionPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage> packages)
0x8d25  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_PackagesToInstall(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> value)
0x8d2a  ldarg.1
0x8d2b  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x8d30  brfalse  loc_8DD8
0x8d35  ldarg.1
0x8d36  ldloc.1
0x8d37  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_TemplateUniqueName()
0x8d3c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_XdbTemplateIdentifier(string value)
0x8d41  call     T0x2B000019
0x8d46  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::GetSpartanAzureRegion()
0x8d4b  stloc.s  6
0x8d4d  ldloc.s  6
0x8d4f  ldloc.1
0x8d50  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_TemplateUniqueName()
0x8d55  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x8d5a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::DoesTemplateDatabaseExistAsync(string, string, valuetype [mscorlib]System.Threading.CancellationToken)
0x8d5f  ldc.i4.0
0x8d60  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x8d65  stloc.s  7
0x8d67  ldloca.s 7
0x8d69  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x8d6e  stloc.s  8
0x8d70  ldloca.s 8
0x8d72  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x8d77  brtrue   loc_8E45
0x8d7c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8d81  ldstr    aXdbOrganizatio// "Xdb Organization template not found for"...
0x8d86  ldc.i4.5
0x8d87  newarr   [mscorlib]System.Object
0x8d8c  dup
0x8d8d  ldc.i4.0
0x8d8e  ldarg.1
0x8d8f  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8d94  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0x8d99  stelem.ref
0x8d9a  dup
0x8d9b  ldc.i4.1
0x8d9c  ldloc.0
0x8d9d  box      [mscorlib]System.Guid
0x8da2  stelem.ref
0x8da3  dup
0x8da4  ldc.i4.2
0x8da5  ldarg.1
0x8da6  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_BaseLanguageCode()
0x8dab  box      [mscorlib]System.Int32
0x8db0  stelem.ref
0x8db1  dup
0x8db2  ldc.i4.3
0x8db3  ldloc.1
0x8db4  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_TemplateUniqueName()
0x8db9  stelem.ref
0x8dba  dup
0x8dbb  ldc.i4.4
0x8dbc  ldarg.1
0x8dbd  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8dc2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x8dc7  box      [mscorlib]System.Guid
0x8dcc  stelem.ref
0x8dcd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8dd2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8dd7  throw
0x8dd8  ldloc.1
0x8dd9  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_TemplateUniqueName()
0x8dde  call     string Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::GetTemplatePath(string templateUniqueName)
0x8de3  stloc.s  9
0x8de5  ldarg.1
0x8de6  ldloc.s  9
0x8de8  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_OrganizationTemplateName(string value)
0x8ded  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x8df2  ldloc.s  9
0x8df4  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::ValidateTemplateFiles(string templateFileBaseName)
0x8df9  brtrue.s loc_8E45
0x8dfb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e00  ldstr    aOrganizationTe// "Organization template not found: '{0}'."...
0x8e05  ldc.i4.4
0x8e06  newarr   [mscorlib]System.Object
0x8e0b  dup
0x8e0c  ldc.i4.0
0x8e0d  ldloc.s  9
0x8e0f  stelem.ref
0x8e10  dup
0x8e11  ldc.i4.1
0x8e12  ldloc.0
0x8e13  box      [mscorlib]System.Guid
0x8e18  stelem.ref
0x8e19  dup
0x8e1a  ldc.i4.2
0x8e1b  ldarg.1
0x8e1c  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_BaseLanguageCode()
0x8e21  box      [mscorlib]System.Int32
0x8e26  stelem.ref
0x8e27  dup
0x8e28  ldc.i4.3
0x8e29  ldarg.1
0x8e2a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8e2f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x8e34  box      [mscorlib]System.Guid
0x8e39  stelem.ref
0x8e3a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e3f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8e44  throw
0x8e45  ldloca.s 0xA
0x8e47  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x8e4d  ldloc.s  0xA
0x8e4f  stloc.s  5
0x8e51  leave.s  loc_8ECE
0x8e53  callvirt instance string [mscorlib]System.Object::ToString()
0x8e58  stloc.2
0x8e59  rethrow
0x8e5b  ldnull
0x8e5c  stloc.s  0xB
0x8e5e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8e63  stloc.s  0xC
0x8e65  ldnull
0x8e66  stloc.s  0xD
0x8e68  ldnull
0x8e69  stloc.s  0xE
0x8e6b  ldloc.1
0x8e6c  brfalse.s loc_8EA2
0x8e6e  ldloc.1
0x8e6f  callvirt instance valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderStatus [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_Status()
0x8e74  stloc.s  0xF
0x8e76  ldloca.s 0xF
0x8e78  constrained. [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderStatus
0x8e7e  callvirt instance string [mscorlib]System.Object::ToString()
0x8e83  stloc.s  0xB
0x8e85  ldloc.1
0x8e86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_QueueItemId()
0x8e8b  stloc.s  0xC
0x8e8d  ldloc.1
0x8e8e  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_TemplateUniqueName()
0x8e93  stloc.s  0xD
0x8e95  ldloc.1
0x8e96  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage[] [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningPlaceholderResult::get_Packages()
0x8e9b  call     string Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::ToPackageUrlsString(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage> packages)
0x8ea0  stloc.s  0xE
0x8ea2  call     class Microsoft.Crm.CrmLive.Telemetry.ProvisioningOrganizationScaleGroupEventSource Microsoft.Crm.CrmLive.Telemetry.ProvisioningOrganizationScaleGroupEventSource::get_Instance()
0x8ea7  ldarg.1
0x8ea8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8ead  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x8eb2  ldloc.0
0x8eb3  ldloc.s  0xB
0x8eb5  ldloc.s  0xC
0x8eb7  ldloc.s  0xD
0x8eb9  ldloc.s  0xE
0x8ebb  ldarg.1
0x8ebc  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationTemplateName()
0x8ec1  ldloc.2
0x8ec2  ldloc.3
0x8ec3  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x8ec8  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.ProvisioningOrganizationScaleGroupEventSource::ProvisionOrgSgPrepForPlaceholder(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scaleGroupId, string status, valuetype [mscorlib]System.Guid queueItemId, string templateUniqueName, string packageUrls, string templatePath, string error, int64 durationMs)
0x8ecd  endfinally
0x8ece  ldloc.s  5
0x8ed0  ret
```
