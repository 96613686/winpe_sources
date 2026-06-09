# Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateExecutor::Execute

- ea: `0x262b0`
- end: `0x26470`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateExecutor::Execute`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x262b0`

## string_xrefs

- `0x2635d`: `CrmScaleGroupProvisioningService`
- `0x26398`: `CrmScaleGroupProvisioningService`
- `0x26306`: `databaseupdated`
- `0x26417`: `DBUpdates failed for organization {0}. Exception details: {1}.`
- `0x26449`: `DBUpdates succeeded for organization {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x262b0  ldnull
0x262b1  stloc.0
0x262b2  ldarg.1
0x262b3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x262b8  stloc.1
0x262b9  ldc.i4.3
0x262ba  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageReport::set_UIMode(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.UIMode)
0x262bf  ldloc.1
0x262c0  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x262c5  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::Deserialize(string)
0x262ca  stloc.0
0x262cb  ldloc.0
0x262cc  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_Uninstall()
0x262d1  brfalse.s loc_2632A
0x262d3  ldnull
0x262d4  stloc.2
0x262d5  ldloc.0
0x262d6  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_UninstallVersion()
0x262db  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x262e0  brtrue.s loc_262EE
0x262e2  ldloc.0
0x262e3  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_UninstallVersion()
0x262e8  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x262ed  stloc.2
0x262ee  ldloc.0
0x262ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x262f4  ldloc.2
0x262f5  call     void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdatesForUninstall(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x262fa  ldarg.0
0x262fb  ldfld    class [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateExecutor::orgLifecycleDataSyncNotificationService
0x26300  newobj   instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::.ctor()
0x26305  dup
0x26306  ldstr    aDatabaseupdate// "databaseupdated"
0x2630b  stfld    string [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::Name
0x26310  dup
0x26311  ldloc.0
0x26312  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x26317  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x2631c  dup
0x2631d  ldloc.2
0x2631e  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification::set_InstallDbVersion(class [mscorlib]System.Version)
0x26323  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotificationService::SendNotification(class [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrgLifecycleDataSyncNotification)
0x26328  br.s     loc_2634A
0x2632a  ldloc.0
0x2632b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x26330  ldc.i4.2
0x26331  ldc.i4.0
0x26332  newobj   instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::.ctor(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource, valuetype [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode)
0x26337  stloc.3
0x26338  ldloc.3
0x26339  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x2633e  leave.s  loc_2634A
0x26340  ldloc.3
0x26341  brfalse.s loc_26349
0x26343  ldloc.3
0x26344  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26349  endfinally
0x2634a  leave    loc_26443
0x2634f  stloc.s  4
0x26351  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x26356  stloc.s  5
0x26358  ldloc.0
0x26359  brtrue.s loc_26396
0x2635b  ldloc.s  5
0x2635d  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x26362  ldc.i4.1
0x26363  ldc.i4   0xC0004653
0x26368  conv.u8
0x26369  ldc.i4.3
0x2636a  newarr   [mscorlib]System.Object
0x2636f  dup
0x26370  ldc.i4.0
0x26371  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26376  box      [mscorlib]System.Guid
0x2637b  stelem.ref
0x2637c  dup
0x2637d  ldc.i4.1
0x2637e  ldloc.1
0x2637f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x26384  box      [mscorlib]System.Guid
0x26389  stelem.ref
0x2638a  dup
0x2638b  ldc.i4.2
0x2638c  ldloc.s  4
0x2638e  stelem.ref
0x2638f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x26394  br.s     loc_263D0
0x26396  ldloc.s  5
0x26398  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x2639d  ldc.i4.1
0x2639e  ldc.i4   0xC0004653
0x263a3  conv.u8
0x263a4  ldc.i4.3
0x263a5  newarr   [mscorlib]System.Object
0x263aa  dup
0x263ab  ldc.i4.0
0x263ac  ldloc.0
0x263ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x263b2  box      [mscorlib]System.Guid
0x263b7  stelem.ref
0x263b8  dup
0x263b9  ldc.i4.1
0x263ba  ldloc.1
0x263bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x263c0  box      [mscorlib]System.Guid
0x263c5  stelem.ref
0x263c6  dup
0x263c7  ldc.i4.2
0x263c8  ldloc.s  4
0x263ca  stelem.ref
0x263cb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x263d0  leave.s  loc_263DE
0x263d2  ldloc.s  5
0x263d4  brfalse.s loc_263DD
0x263d6  ldloc.s  5
0x263d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x263dd  endfinally
0x263de  call     class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::ConnectLivePlatformService()
0x263e3  stloc.s  6
0x263e5  ldloc.s  6
0x263e7  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x263ec  ldloc.0
0x263ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x263f2  ldarg.1
0x263f3  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x263f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x263fd  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::NotifyOrganizationDBUpdateFailure(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26402  leave.s  loc_26410
0x26404  ldloc.s  6
0x26406  brfalse.s loc_2640F
0x26408  ldloc.s  6
0x2640a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2640f  endfinally
0x26410  ldc.i4.s 0xB
0x26412  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26417  ldstr    aDbupdatesFaile// "DBUpdates failed for organization {0}. "...
0x2641c  ldc.i4.2
0x2641d  newarr   [mscorlib]System.Object
0x26422  dup
0x26423  ldc.i4.0
0x26424  ldloc.0
0x26425  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x2642a  box      [mscorlib]System.Guid
0x2642f  stelem.ref
0x26430  dup
0x26431  ldc.i4.1
0x26432  ldloc.s  4
0x26434  stelem.ref
0x26435  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2643a  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2643f  stloc.s  7
0x26441  leave.s  loc_2646D
0x26443  ldc.i4.4
0x26444  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26449  ldstr    aDbupdatesSucce// "DBUpdates succeeded for organization {0"...
0x2644e  ldc.i4.1
0x2644f  newarr   [mscorlib]System.Object
0x26454  dup
0x26455  ldc.i4.0
0x26456  ldloc.0
0x26457  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationDBUpdateInfo::get_OrganizationId()
0x2645c  box      [mscorlib]System.Guid
0x26461  stelem.ref
0x26462  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26467  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2646c  ret
0x2646d  ldloc.s  7
0x2646f  ret
```
