# Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::PrepareForProvisioningTemplate

- ea: `0x8a80`
- end: `0x8c5d`
- name: `Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::PrepareForProvisioningTemplate`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x870`
- `0x880`
- `0x8a40`
- `0x8a60`
- `0x8a80`
- `0x8f00`
- `0x8f60`
- `0x8fc0`
- `0x9000`
- `0x9180`
- `0x91b0`
- `0x91d0`
- `0x91e0`
- `0x9410`
- `0x9440`
- `0x94e0`
- `0x94f0`
- `0x24310`
- `0x24330`
- `0x24340`

## string_xrefs

- `0x8b38`: `Overriding PackagesToInstall from C:\CustomPackagesOverride`

## pseudocode

```c

```

## disassembly

```asm
0x8a80  ldarg.1
0x8a81  ldstr    aOrganizationpr// "organizationProperties"
0x8a86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8a8b  ldarg.1
0x8a8c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8a91  ldstr    aOrganizationpr_0// "organizationProperties.OrganizationData"
0x8a96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8a9b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8aa0  stloc.0
0x8aa1  ldnull
0x8aa2  stloc.1
0x8aa3  ldnull
0x8aa4  stloc.2
0x8aa5  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x8aaa  stloc.3
0x8aab  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x8ab0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x8ab5  stloc.0
0x8ab6  ldarg.2
0x8ab7  ldc.i4.0
0x8ab8  stind.i1
0x8ab9  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::CreatePlatformClient()
0x8abe  stloc.s  4
0x8ac0  ldloc.s  4
0x8ac2  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x8ac7  ldloc.0
0x8ac8  ldarg.1
0x8ac9  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8ace  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x8ad3  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningTemplateResult [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::PrepareForProvisioningTemplate(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ad8  stloc.1
0x8ad9  leave.s  loc_8AE7
0x8adb  ldloc.s  4
0x8add  brfalse.s loc_8AE6
0x8adf  ldloc.s  4
0x8ae1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ae6  endfinally
0x8ae7  ldarg.1
0x8ae8  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x8aed  brfalse.s loc_8AFD
0x8aef  ldarg.1
0x8af0  ldloc.1
0x8af1  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningTemplateResult::get_TemplateUniqueName()
0x8af6  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_XdbTemplateIdentifier(string value)
0x8afb  br.s     loc_8B12
0x8afd  ldloc.1
0x8afe  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningTemplateResult::get_TemplateUniqueName()
0x8b03  call     string Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::GetTemplatePath(string templateUniqueName)
0x8b08  stloc.s  5
0x8b0a  ldarg.1
0x8b0b  ldloc.s  5
0x8b0d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_OrganizationTemplateName(string value)
0x8b12  ldarg.1
0x8b13  ldloc.1
0x8b14  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage[] [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningTemplateResult::get_Packages()
0x8b19  call     class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::ToProvisioningSolutionPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage> packages)
0x8b1e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_PackagesToInstall(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> value)
0x8b23  ldarg.1
0x8b24  call     bool Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::TemplateDebuggingModeEnabled()
0x8b29  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_DoNotCleanUpOnException(bool value)
0x8b2e  call     bool Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::IsLocalCustomPackageOverrideSet()
0x8b33  brfalse  loc_8C0C
0x8b38  ldstr    aOverridingPack// "Overriding PackagesToInstall from C:\\C"...
0x8b3d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x8b42  ldarg.1
0x8b43  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage>::.ctor()
0x8b48  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::set_PackagesToInstall(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> value)
0x8b4d  ldstr    aCCustompackage// "C:\\CustomPackagesOverride"
0x8b52  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x8b57  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__2_0
0x8b5c  dup
0x8b5d  brtrue.s loc_8B76
0x8b5f  pop
0x8b60  ldsfld   class <>c <>c::<>9
0x8b65  ldftn    instance string <>c::<PrepareForProvisioningTemplate>b__2_0(string x)
0x8b6b  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x8b70  dup
0x8b71  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__2_0
0x8b76  call     T0x2B000029
0x8b7b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x8b80  stloc.s  6
0x8b82  br.s     loc_8BF5
0x8b84  ldloc.s  6
0x8b86  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x8b8b  stloc.s  7
0x8b8d  ldloc.s  7
0x8b8f  ldstr    aZip// "*.zip"
0x8b94  call     string[] [mscorlib]System.IO.Directory::GetFiles(string, string)
0x8b99  stloc.s  8
0x8b9b  ldloc.s  8
0x8b9d  ldlen
0x8b9e  conv.i4
0x8b9f  ldc.i4.1
0x8ba0  bne.un.s loc_8BDE
0x8ba2  ldloc.s  8
0x8ba4  ldc.i4.0
0x8ba5  ldelem.ref
0x8ba6  stloc.s  9
0x8ba8  ldstr    aAddingPackage// "Adding Package : "
0x8bad  ldloc.s  9
0x8baf  call     string [mscorlib]System.String::Concat(string, string)
0x8bb4  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x8bb9  ldarg.1
0x8bba  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PackagesToInstall()
0x8bbf  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage::.ctor()
0x8bc4  dup
0x8bc5  ldloc.s  9
0x8bc7  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage::set_PackageUrl(string value)
0x8bcc  dup
0x8bcd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x8bd2  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage::set_SolutionId(valuetype [mscorlib]System.Guid value)
0x8bd7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage>::Add(var<u1>)
0x8bdc  br.s     loc_8BF5
0x8bde  ldstr    aFolder// "Folder "
0x8be3  ldloc.s  7
0x8be5  ldstr    aDoesNotContain// " does not contain exactly one zip file"
0x8bea  call     string [mscorlib]System.String::Concat(string, string, string)
0x8bef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8bf4  throw
0x8bf5  ldloc.s  6
0x8bf7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8bfc  brtrue.s loc_8B84
0x8bfe  leave.s  loc_8C0C
0x8c00  ldloc.s  6
0x8c02  brfalse.s loc_8C0B
0x8c04  ldloc.s  6
0x8c06  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c0b  endfinally
0x8c0c  leave.s  loc_8C5C
0x8c0e  callvirt instance string [mscorlib]System.Object::ToString()
0x8c13  stloc.2
0x8c14  rethrow
0x8c16  ldnull
0x8c17  stloc.s  0xA
0x8c19  ldnull
0x8c1a  stloc.s  0xB
0x8c1c  ldloc.1
0x8c1d  brfalse.s loc_8C34
0x8c1f  ldloc.1
0x8c20  callvirt instance string [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningTemplateResult::get_TemplateUniqueName()
0x8c25  stloc.s  0xA
0x8c27  ldloc.1
0x8c28  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage[] [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.PrepareForProvisioningTemplateResult::get_Packages()
0x8c2d  call     string Microsoft.Crm.CrmLive.Provisioning.MtpOrganizationProvisioner::ToPackageUrlsString(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.ProvisioningPackage> packages)
0x8c32  stloc.s  0xB
0x8c34  call     class Microsoft.Crm.CrmLive.Telemetry.ProvisioningOrganizationScaleGroupEventSource Microsoft.Crm.CrmLive.Telemetry.ProvisioningOrganizationScaleGroupEventSource::get_Instance()
0x8c39  ldarg.1
0x8c3a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x8c3f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x8c44  ldloc.0
0x8c45  ldloc.s  0xA
0x8c47  ldloc.s  0xB
0x8c49  ldarg.1
0x8c4a  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationTemplateName()
0x8c4f  ldloc.2
0x8c50  ldloc.3
0x8c51  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x8c56  callvirt instance void Microsoft.Crm.CrmLive.Telemetry.ProvisioningOrganizationScaleGroupEventSource::ProvisionOrgSgPrepForTemplate(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scaleGroupId, string templateUniqueName, string packageUrls, string templatePath, string error, int64 durationMs)
0x8c5b  endfinally
0x8c5c  ret
```
