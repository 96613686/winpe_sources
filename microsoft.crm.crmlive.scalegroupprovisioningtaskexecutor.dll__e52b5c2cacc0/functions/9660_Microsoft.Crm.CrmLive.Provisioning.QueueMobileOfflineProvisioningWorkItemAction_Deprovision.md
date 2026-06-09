# Microsoft.Crm.CrmLive.Provisioning.QueueMobileOfflineProvisioningWorkItemAction::Deprovision

- ea: `0x9660`
- end: `0x9764`
- name: `Microsoft.Crm.CrmLive.Provisioning.QueueMobileOfflineProvisioningWorkItemAction::Deprovision`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x64b0`
- `0x91b0`
- `0x9660`

## string_xrefs

- `0x96ce`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\QueueMobileOfflineProvisioningWorkItemAction.cs`
- `0x96d9`: `OrganizationDelete`

## pseudocode

```c

```

## disassembly

```asm
0x9660  ldc.i4.2
0x9661  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x9666  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x966b  bne.un   loc_9747
0x9670  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x9675  stloc.0
0x9676  ldarg.0
0x9677  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x967c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9681  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x9686  stloc.1
0x9687  ldloc.0
0x9688  ldstr    aOrganizationid_0// "OrganizationId"
0x968d  ldloc.1
0x968e  box      [mscorlib]System.Guid
0x9693  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x9698  ldloc.0
0x9699  ldstr    aOrgapplication// "OrgApplicationType"
0x969e  ldloc.1
0x969f  call     valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OrgApplicationType [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::GetOrgApplicationType(valuetype [mscorlib]System.Guid)
0x96a4  box      [Microsoft.Crm.Constants]Microsoft.Crm.OrgApplicationType
0x96a9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x96ae  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x96b3  ldstr    aOrgapplication_0// "OrgApplicationMap"
0x96b8  ldc.i4.1
0x96b9  newarr   [mscorlib]System.String
0x96be  dup
0x96bf  ldc.i4.0
0x96c0  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0x96c5  stelem.ref
0x96c6  ldloc.0
0x96c7  ldc.i4.s 0x23
0x96c9  ldstr    aDeprovision// "Deprovision"
0x96ce  ldstr    aDDbsShDccm2110_11// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x96d3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x96d8  stloc.2
0x96d9  ldstr    aOrganizationde// "OrganizationDelete"
0x96de  stloc.3
0x96df  ldloc.2
0x96e0  brfalse.s loc_9747
0x96e2  ldloc.2
0x96e3  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0x96e8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x96ed  unbox.any [mscorlib]System.Int32
0x96f2  ldc.i4.2
0x96f3  beq.s    loc_971B
0x96f5  ldloc.2
0x96f6  ldstr    aOrgapplication_2// "\tOrgApplicationStatus"
0x96fb  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x9700  unbox.any [mscorlib]System.Int32
0x9705  ldc.i4.6
0x9706  beq.s    loc_971B
0x9708  ldloc.2
0x9709  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0x970e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x9713  unbox.any [mscorlib]System.Int32
0x9718  ldc.i4.3
0x9719  bne.un.s loc_9747
0x971b  ldarg.0
0x971c  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9721  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9726  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x972b  ldloc.3
0x972c  ldarg.0
0x972d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x9732  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x9737  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x973c  newobj   instance void [Microsoft.Crm.AzureWorkItem]Microsoft.Crm.AzureWorkItem.WorkItemHelper::.ctor(valuetype [mscorlib]System.Guid, string, string)
0x9741  ldc.i4.2
0x9742  callvirt instance void [Microsoft.Crm.AzureWorkItem]Microsoft.Crm.AzureWorkItem.WorkItemHelper::Execute(valuetype [Microsoft.Xrm.Sync.WorkItems]Microsoft.Xrm.Sync.WorkItems.WorkItemType)
0x9747  leave.s  loc_9763
0x9749  stloc.s  4
0x974b  ldstr    aFailedToQueueM// "Failed to Queue Mobile Offline Deprovis"...
0x9750  ldloc.s  4
0x9752  callvirt instance string [mscorlib]System.Object::ToString()
0x9757  call     string [mscorlib]System.String::Concat(string, string)
0x975c  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x9761  leave.s  loc_9763
0x9763  ret
```
