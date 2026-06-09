# Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Do

- ea: `0x4f70`
- end: `0x50cd`
- name: `Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Do`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x470`
- `0x4ee0`
- `0x4f40`
- `0x4f70`
- `0x51e0`
- `0x64b0`
- `0x9130`
- `0x91b0`
- `0x94e0`
- `0x15a10`
- `0x1bec0`
- `0x1c3b0`
- `0x24300`
- `0x24320`

## string_xrefs

- `0x4f90`: `No solution packages to install`
- `0x502e`: `Calling InstallPackage for : `

## pseudocode

```c

```

## disassembly

```asm
0x4f70  ldarg.0
0x4f71  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4f76  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PackagesToInstall()
0x4f7b  brfalse.s loc_4F8F
0x4f7d  ldarg.0
0x4f7e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4f83  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PackagesToInstall()
0x4f88  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage>::get_Count()
0x4f8d  brtrue.s loc_4F9B
0x4f8f  ldarg.0
0x4f90  ldstr    aNoSolutionPack// "No solution packages to install"
0x4f95  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x4f9a  ret
0x4f9b  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x4fa0  stloc.0
0x4fa1  ldarg.0
0x4fa2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::get_CrmUserIdOverride()
0x4fa7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4fac  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4fb1  brfalse.s loc_4FBC
0x4fb3  ldarg.0
0x4fb4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::get_CrmUserIdOverride()
0x4fb9  stloc.1
0x4fba  br.s     loc_4FD8
0x4fbc  ldloc.0
0x4fbd  ldarg.0
0x4fbe  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4fc3  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x4fc8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x4fcd  callvirt instance class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string> Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetInitialCrmSystemUserIdAndFullName(valuetype [mscorlib]System.Guid orgId)
0x4fd2  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>::get_Item1()
0x4fd7  stloc.1
0x4fd8  ldc.i4.0
0x4fd9  stloc.2
0x4fda  ldarg.0
0x4fdb  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x4fe0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage> Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PackagesToInstall()
0x4fe5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage>::GetEnumerator()
0x4fea  stloc.3
0x4feb  br       loc_509F
0x4ff0  ldloc.3
0x4ff1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage>::get_Current()
0x4ff6  stloc.s  4
0x4ff8  ldsfld   class [mscorlib]System.Lazy`1<class [System]System.Threading.Semaphore> Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::_semaphore
0x4ffd  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System]System.Threading.Semaphore>::get_Value()
0x5002  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x5007  pop
0x5008  ldarg.0
0x5009  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x500e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5013  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5018  ldarg.0
0x5019  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x501e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x5023  ldstr    asc_361CC// ""
0x5028  call     void Microsoft.Crm.CrmLive.ProvisioningOrgDBStateCollector::CollectAndSendToEventSource(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId, [opt] string additionalDetails)
0x502d  ldarg.0
0x502e  ldstr    aCallingInstall// "Calling InstallPackage for : "
0x5033  ldloc.s  4
0x5035  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage::get_PackageUrl()
0x503a  call     string [mscorlib]System.String::Concat(string, string)
0x503f  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x5044  ldarg.0
0x5045  ldloc.1
0x5046  ldloc.s  4
0x5048  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage::get_SolutionId()
0x504d  ldloc.s  4
0x504f  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisioningSolutionPackage::get_PackageUrl()
0x5054  call     instance class Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::InstallPackage(valuetype [mscorlib]System.Guid crmUserId, valuetype [mscorlib]System.Guid solutionId, string packageUrl)
0x5059  stloc.s  5
0x505b  ldloc.2
0x505c  ldloc.s  5
0x505e  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.ImportedRecord[] Microsoft.Crm.CrmLive.Provisioning.SolutionPackageDataReport::get_Records()
0x5063  ldlen
0x5064  conv.i4
0x5065  add
0x5066  stloc.2
0x5067  ldarg.0
0x5068  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x506d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5072  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5077  ldarg.0
0x5078  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x507d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x5082  ldstr    asc_361CC// ""
0x5087  call     void Microsoft.Crm.CrmLive.ProvisioningOrgDBStateCollector::CollectAndSendToEventSource(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid queueItemId, [opt] string additionalDetails)
0x508c  leave.s  loc_509F
0x508e  ldsfld   class [mscorlib]System.Lazy`1<class [System]System.Threading.Semaphore> Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::_semaphore
0x5093  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System]System.Threading.Semaphore>::get_Value()
0x5098  callvirt instance int32 [System]System.Threading.Semaphore::Release()
0x509d  pop
0x509e  endfinally
0x509f  ldloc.3
0x50a0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x50a5  brtrue   loc_4FF0
0x50aa  leave.s  loc_50B6
0x50ac  ldloc.3
0x50ad  brfalse.s loc_50B5
0x50af  ldloc.3
0x50b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50b5  endfinally
0x50b6  ldarg.0
0x50b7  ldstr    aTotalRecordsIm// "Total records imported : "
0x50bc  ldloc.2
0x50bd  box      [mscorlib]System.Int32
0x50c2  call     string [mscorlib]System.String::Concat(object, object)
0x50c7  call     instance void Microsoft.Crm.CrmLive.Provisioning.InstallSolutionPackagesAction::Log(string log)
0x50cc  ret
```
