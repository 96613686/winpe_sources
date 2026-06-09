# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::Execute

- ea: `0x250c0`
- end: `0x2543f`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::Execute`
- size: `895`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x250c0`
- `0x25440`
- `0x25530`
- `0x25550`
- `0x255c0`

## string_xrefs

- `0x250e9`: `task.QueueItem.OrganizationId`
- `0x25210`: `Error '{0}' on attempt {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x250c0  ldarg.1
0x250c1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x250c6  stloc.0
0x250c7  ldloc.0
0x250c8  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x250cd  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::Deserialize(string)
0x250d2  stloc.1
0x250d3  ldloc.1
0x250d4  ldstr    aItemdata// "itemData"
0x250d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x250de  ldarg.1
0x250df  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x250e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x250e9  ldstr    aTaskQueueitemO// "task.QueueItem.OrganizationId"
0x250ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x250f3  call     T0x2B000036
0x250f8  ldarg.1
0x250f9  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x250fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x25103  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid)
0x25108  stloc.2
0x25109  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2510e  stloc.3
0x2510f  ldc.i4.0
0x25110  stloc.s  4
0x25112  ldloc.1
0x25113  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_OldSecurityGroup()
0x25118  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2511d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x25122  brfalse.s loc_2513B
0x25124  ldloc.1
0x25125  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x2512a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2512f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x25134  brfalse.s loc_2513B
0x25136  ldc.i4.1
0x25137  stloc.s  4
0x25139  br.s     loc_251A2
0x2513b  ldloc.1
0x2513c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_OldSecurityGroup()
0x25141  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25146  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2514b  brfalse.s loc_2517B
0x2514d  ldloc.1
0x2514e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x25153  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25158  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2515d  brfalse.s loc_2517B
0x2515f  ldloc.3
0x25160  ldloc.1
0x25161  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_OldSecurityGroup()
0x25166  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2516b  pop
0x2516c  ldloc.3
0x2516d  ldloc.1
0x2516e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x25173  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x25178  pop
0x25179  br.s     loc_251A2
0x2517b  ldloc.1
0x2517c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_OldSecurityGroup()
0x25181  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25186  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2518b  brfalse.s loc_251A2
0x2518d  ldloc.1
0x2518e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x25193  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25198  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2519d  brfalse.s loc_251A2
0x2519f  ldc.i4.1
0x251a0  stloc.s  4
0x251a2  ldc.i4.0
0x251a3  stloc.s  5
0x251a5  br       loc_25297
0x251aa  nop
0x251ab  ldloc.1
0x251ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x251b1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x251b6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x251bb  brfalse.s loc_251E9
0x251bd  ldloc.2
0x251be  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::get_UseCloudChanges()
0x251c3  brfalse.s loc_251DE
0x251c5  ldloc.1
0x251c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x251cb  ldarg.1
0x251cc  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x251d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x251d6  ldloc.2
0x251d7  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SetIsToBeAppliedFromCloud(valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider)
0x251dc  br.s     loc_251E9
0x251de  ldloc.1
0x251df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupData::get_NewSecurityGroup()
0x251e4  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SetIsToBeAppliedInConfigDb(valuetype [mscorlib]System.Guid directoryObjectId)
0x251e9  leave    loc_2529F
0x251ee  stloc.s  8
0x251f0  ldloc.s  5
0x251f2  ldc.i4.1
0x251f3  add
0x251f4  stloc.s  5
0x251f6  ldloc.0
0x251f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x251fc  ldc.i4.s 0xA
0x251fe  ldstr    a0// "{0}"
0x25203  ldc.i4.1
0x25204  newarr   [mscorlib]System.Object
0x25209  dup
0x2520a  ldc.i4.0
0x2520b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25210  ldstr    aError0OnAttemp// "Error '{0}' on attempt {1}."
0x25215  ldc.i4.2
0x25216  newarr   [mscorlib]System.Object
0x2521b  dup
0x2521c  ldc.i4.0
0x2521d  ldloc.s  8
0x2521f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25224  stelem.ref
0x25225  dup
0x25226  ldc.i4.1
0x25227  ldloc.s  5
0x25229  box      [mscorlib]System.Int32
0x2522e  stelem.ref
0x2522f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25234  stelem.ref
0x25235  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2523a  ldloc.s  5
0x2523c  ldc.i4.3
0x2523d  bne.un.s loc_25295
0x2523f  ldloc.s  8
0x25241  isinst   [System]System.Net.WebException
0x25246  stloc.s  9
0x25248  ldloc.s  9
0x2524a  brfalse.s loc_25293
0x2524c  ldloc.s  9
0x2524e  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x25253  brfalse.s loc_25293
0x25255  ldloc.s  9
0x25257  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x2525c  isinst   [System]System.Net.HttpWebResponse
0x25261  stloc.s  0xA
0x25263  ldloc.s  0xA
0x25265  brfalse.s loc_25293
0x25267  ldloc.s  0xA
0x25269  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x2526e  ldc.i4   0x194
0x25273  bne.un.s loc_25293
0x25275  ldstr    aRetrying// "Retrying"
0x2527a  ldloc.s  8
0x2527c  ldarg.1
0x2527d  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x25282  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x25287  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x2528c  stloc.s  0xB
0x2528e  leave    loc_2543C
0x25293  rethrow
0x25295  leave.s  loc_25297
0x25297  ldloc.s  5
0x25299  ldc.i4.3
0x2529a  blt      loc_251AA
0x2529f  ldnull
0x252a0  stloc.s  6
0x252a2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x252a7  ldstr    aMsonlinesyncus// "MsOnlineSyncUserBatchSize"
0x252ac  ldc.i4.0
0x252ad  callvirt T0x2B000013
0x252b2  stloc.s  7
0x252b4  ldloc.s  4
0x252b6  brfalse  loc_253A9
0x252bb  ldc.i8   0x8000000000000000
0x252c4  stloc.s  0xC
0x252c6  ldloc.2
0x252c7  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::get_UseCloudChanges()
0x252cc  brfalse.s loc_252DF
0x252ce  ldarg.1
0x252cf  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x252d4  ldloc.2
0x252d5  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SyncUserObjectsFromCloud(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem queueItem, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider)
0x252da  br       loc_2536F
0x252df  ldloc.2
0x252e0  ldarg.1
0x252e1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x252e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x252eb  callvirt instance class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::GetOrganizationContextAndRevision(valuetype [mscorlib]System.Guid)
0x252f0  stloc.s  0xD
0x252f2  ldloc.2
0x252f3  ldloc.s  0xD
0x252f5  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::get_Item1()
0x252fa  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x252ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25304  ldloc.s  0xC
0x25306  ldloc.s  0xD
0x25308  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::get_Item2()
0x2530d  ldloc.s  7
0x2530f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveActiveObjectsForContext(valuetype [mscorlib]System.Guid, class [mscorlib]System.Type, int64, int64, int32)
0x25314  call     T0x2B0000A6
0x25319  stloc.s  6
0x2531b  br.s     loc_25366
0x2531d  ldloc.0
0x2531e  ldloc.s  6
0x25320  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SyncUserObjects(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem queueItem, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> userObjects)
0x25325  ldloc.s  6
0x25327  call     T0x2B0000A7
0x2532c  ldstr    aRevision// "Revision"
0x25331  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x25336  unbox.any [mscorlib]System.Int64
0x2533b  stloc.s  0xC
0x2533d  ldloc.2
0x2533e  ldloc.s  0xD
0x25340  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::get_Item1()
0x25345  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x2534a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2534f  ldloc.s  0xC
0x25351  ldloc.s  0xD
0x25353  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::get_Item2()
0x25358  ldloc.s  7
0x2535a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveActiveObjectsForContext(valuetype [mscorlib]System.Guid, class [mscorlib]System.Type, int64, int64, int32)
0x2535f  call     T0x2B0000A6
0x25364  stloc.s  6
0x25366  ldloc.s  6
0x25368  call     T0x2B0000A8
0x2536d  brtrue.s loc_2531D
0x2536f  ldc.i4.4
0x25370  ldstr    aSuccess_0// "Success"
0x25375  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x2537a  stloc.s  0xB
0x2537c  leave    loc_2543C
0x25381  stloc.s  0xE
0x25383  ldc.i4.s 0xB
0x25385  ldstr    aRetrying_0// "retrying"
0x2538a  ldloc.s  0xE
0x2538c  ldarg.1
0x2538d  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x25392  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x25397  ldc.i4   0x12C
0x2539c  ldc.i4.5
0x2539d  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception, int32, int32, int32)
0x253a2  stloc.s  0xB
0x253a4  leave    loc_2543C
0x253a9  ldloc.2
0x253aa  ldarg.1
0x253ab  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x253b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x253b5  ldloc.3
0x253b6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveObjectsForOrganizationLinks(valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>)
0x253bb  call     T0x2B0000A6
0x253c0  stloc.s  6
0x253c2  ldloc.s  6
0x253c4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x253c9  ldc.i4.0
0x253ca  ble.s    loc_25408
0x253cc  ldloc.s  6
0x253ce  ldloc.s  7
0x253d0  call     T0x2B0000A9
0x253d5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[]>::GetEnumerator()
0x253da  stloc.s  0xF
0x253dc  br.s     loc_253EF
0x253de  ldloca.s 0xF
0x253e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[]>::get_Current()
0x253e5  stloc.s  0x10
0x253e7  ldloc.0
0x253e8  ldloc.s  0x10
0x253ea  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SyncUserObjects(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem queueItem, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> userObjects)
0x253ef  ldloca.s 0xF
0x253f1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[]>::MoveNext()
0x253f6  brtrue.s loc_253DE
0x253f8  leave.s  loc_25408
0x253fa  ldloca.s 0xF
0x253fc  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[]>
0x25402  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25407  endfinally
0x25408  ldc.i4.4
0x25409  ldstr    aSuccess_0// "Success"
0x2540e  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x25413  stloc.s  0xB
0x25415  leave.s  loc_2543C
0x25417  stloc.s  0x11
0x25419  ldc.i4.s 0xB
0x2541b  ldstr    aRetrying_0// "retrying"
0x25420  ldloc.s  0x11
0x25422  ldarg.1
0x25423  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x25428  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x2542d  ldc.i4   0x12C
0x25432  ldc.i4.5
0x25433  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string, class [mscorlib]System.Exception, int32, int32, int32)
0x25438  stloc.s  0xB
0x2543a  leave.s  loc_2543C
0x2543c  ldloc.s  0xB
0x2543e  ret
```
