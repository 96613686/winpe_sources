# Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SyncNewObjectsAndLinksFromCloud

- ea: `0x2a150`
- end: `0x2a4ae`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SyncNewObjectsAndLinksFromCloud`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x29cb0`

## callees

- `0x16f0`
- `0x1720`
- `0xe7a0`
- `0xf3d0`
- `0x21a10`
- `0x2a140`
- `0x2a150`
- `0x2a4b0`
- `0x2a600`
- `0x333f0`
- `0x33410`
- `0x33430`
- `0x33450`

## string_xrefs

- `0x2a368`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncDataExecutor.cs`
- `0x2a2e3`: `Unexpected link when an object was expected`
- `0x2a363`: `SyncNewObjectsAndLinksFromCloud`

## pseudocode

```c

```

## disassembly

```asm
0x2a150  ldarg.0
0x2a151  ldarg.1
0x2a152  ldarg.3
0x2a153  call     instance void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::InitializeForOrg(valuetype [mscorlib]System.Guid organizationId, bool isOrgDisabled)
0x2a158  ldarg.0
0x2a159  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a15e  ldarg.1
0x2a15f  ldarg.3
0x2a160  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveCloudChangesForOrganization(valuetype [mscorlib]System.Guid, bool)
0x2a165  stloc.0
0x2a166  ldarg.1
0x2a167  ldarg.0
0x2a168  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a16d  newobj   instance void GroupIdsOfInterest::.ctor(valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider dataProvider)
0x2a172  stloc.1
0x2a173  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a178  stloc.2
0x2a179  br       loc_2A483
0x2a17e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2a183  stloc.3
0x2a184  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser>::.ctor()
0x2a189  stloc.s  4
0x2a18b  ldloc.0
0x2a18c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges::get_ReceivedObjectsAndLinks()
0x2a191  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink>::GetEnumerator()
0x2a196  stloc.s  5
0x2a198  br       loc_2A377
0x2a19d  ldloc.s  5
0x2a19f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink>::get_Current()
0x2a1a4  stloc.s  6
0x2a1a6  ldloc.s  6
0x2a1a8  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_IsLink()
0x2a1ad  brfalse  loc_2A253
0x2a1b2  ldarg.3
0x2a1b3  brtrue   loc_2A377
0x2a1b8  ldarg.0
0x2a1b9  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a1be  ldloc.s  6
0x2a1c0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectUrl()
0x2a1c5  ldloca.s 7
0x2a1c7  call     bool Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.MainDirectoryData.ObjectAndLinkRetriever::TryRetrieveLink(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider provider, string objectUrl, [out] class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag& bag)
0x2a1cc  brfalse  loc_2A377
0x2a1d1  ldloc.s  7
0x2a1d3  ldstr    aSourceid// "SourceId"
0x2a1d8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a1dd  unbox.any [mscorlib]System.Guid
0x2a1e2  stloc.s  8
0x2a1e4  ldloc.s  7
0x2a1e6  brfalse  loc_2A377
0x2a1eb  ldloc.s  7
0x2a1ed  ldstr    aSourceclass// "SourceClass"
0x2a1f2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a1f7  castclass [mscorlib]System.String
0x2a1fc  ldstr    aGroup// "Group"
0x2a201  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a206  brfalse  loc_2A377
0x2a20b  ldloc.s  7
0x2a20d  ldstr    aTargetclass// "TargetClass"
0x2a212  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2a217  castclass [mscorlib]System.String
0x2a21c  ldstr    aUser_0// "User"
0x2a221  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a226  brfalse  loc_2A377
0x2a22b  ldloc.1
0x2a22c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> GroupIdsOfInterest::RetrieveList()
0x2a231  ldloc.s  8
0x2a233  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x2a238  brfalse  loc_2A377
0x2a23d  ldloc.s  7
0x2a23f  ldloc.s  4
0x2a241  ldloc.1
0x2a242  ldloc.s  8
0x2a244  callvirt instance bool GroupIdsOfInterest::IsGroupAnAdminGroup(valuetype [mscorlib]System.Guid groupObjectId)
0x2a249  call     void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::AddDirectoryLinkToUsersToProcessForCloud(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag linkData, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser> usersToProcess, bool isAdminGroup)
0x2a24e  br       loc_2A377
0x2a253  ldc.i4.2
0x2a254  ldloc.s  6
0x2a256  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_Subtype()
0x2a25b  bne.un.s loc_2A29B
0x2a25d  ldarg.3
0x2a25e  brtrue   loc_2A377
0x2a263  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::.ctor()
0x2a268  stloc.s  9
0x2a26a  ldloc.s  9
0x2a26c  ldloc.s  6
0x2a26e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectId()
0x2a273  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::set_ObjectId(valuetype [mscorlib]System.Guid)
0x2a278  ldloc.s  9
0x2a27a  ldarg.s  4
0x2a27c  brtrue.s loc_2A287
0x2a27e  ldloc.s  6
0x2a280  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectUrl()
0x2a285  br.s     loc_2A288
0x2a287  ldnull
0x2a288  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::set_ObjectUrl(string)
0x2a28d  ldloc.s  4
0x2a28f  ldloc.s  9
0x2a291  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser>::Add(var<u1>)
0x2a296  br       loc_2A377
0x2a29b  ldc.i4.3
0x2a29c  ldloc.s  6
0x2a29e  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_Subtype()
0x2a2a3  bne.un.s loc_2A2DA
0x2a2a5  ldarg.3
0x2a2a6  brtrue   loc_2A377
0x2a2ab  ldloc.1
0x2a2ac  callvirt instance void GroupIdsOfInterest::RegenerateList()
0x2a2b1  ldloc.1
0x2a2b2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> GroupIdsOfInterest::RetrieveList()
0x2a2b7  ldloc.s  6
0x2a2b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectId()
0x2a2be  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x2a2c3  brfalse  loc_2A377
0x2a2c8  ldloc.3
0x2a2c9  ldloc.s  6
0x2a2cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectId()
0x2a2d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2a2d5  br       loc_2A377
0x2a2da  ldloc.s  6
0x2a2dc  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_IsLink()
0x2a2e1  brfalse.s loc_2A2EE
0x2a2e3  ldstr    aUnexpectedLink// "Unexpected link when an object was expe"...
0x2a2e8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2a2ed  throw
0x2a2ee  ldtoken  [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ObjectsOfInterest
0x2a2f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a2f8  ldloc.s  6
0x2a2fa  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_Subtype()
0x2a2ff  box      [mscorlib]System.Int32
0x2a304  call     string [mscorlib]System.Enum::GetName(class [mscorlib]System.Type, object)
0x2a309  call     class Microsoft.Crm.CrmLive.Provisioning.ISyncDataAction Microsoft.Crm.CrmLive.Provisioning.SyncDataActionFactory::GetAction(string type)
0x2a30e  stloc.s  0xA
0x2a310  ldloc.s  0xA
0x2a312  brfalse.s loc_2A343
0x2a314  ldarg.0
0x2a315  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a31a  ldarg.1
0x2a31b  ldloc.s  6
0x2a31d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectId()
0x2a322  ldarg.s  4
0x2a324  brtrue.s loc_2A32F
0x2a326  ldloc.s  6
0x2a328  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_ObjectUrl()
0x2a32d  br.s     loc_2A330
0x2a32f  ldnull
0x2a330  ldloca.s 0xB
0x2a332  call     bool Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.MainDirectoryData.ObjectAndLinkRetriever::TryRetrieveObject(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider provider, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid objectId, string objectUrl, [out] class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag& bag)
0x2a337  brfalse.s loc_2A343
0x2a339  ldloc.s  0xA
0x2a33b  ldarg.2
0x2a33c  ldloc.s  0xB
0x2a33e  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ISyncDataAction::SyncObject(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record)
0x2a343  ldloc.s  6
0x2a345  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink::get_Subtype()
0x2a34a  brtrue.s loc_2A377
0x2a34c  ldarg.s  4
0x2a34e  brfalse.s loc_2A358
0x2a350  ldarg.1
0x2a351  ldc.i4.s 0xA
0x2a353  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::UpdateOrganizationLifecycleStatus(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationLifecycleStatus)
0x2a358  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x2a35d  ldarg.1
0x2a35e  ldc.i4   0x184
0x2a363  ldstr    aSyncnewobjects// "SyncNewObjectsAndLinksFromCloud"
0x2a368  ldstr    aDDbsShDccm2110_42// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2a36d  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationState(valuetype [mscorlib]System.Guid, int32, string, string)
0x2a372  ldc.i4.0
0x2a373  ceq
0x2a375  starg.s  3
0x2a377  ldloc.s  5
0x2a379  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a37e  brtrue   loc_2A19D
0x2a383  leave.s  loc_2A391
0x2a385  ldloc.s  5
0x2a387  brfalse.s loc_2A390
0x2a389  ldloc.s  5
0x2a38b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a390  endfinally
0x2a391  ldloc.3
0x2a392  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x2a397  stloc.s  0xC
0x2a399  br.s     loc_2A3E8
0x2a39b  ldloca.s 0xC
0x2a39d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x2a3a2  stloc.s  0xD
0x2a3a4  ldarg.0
0x2a3a5  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a3aa  ldarg.1
0x2a3ab  ldloc.s  0xD
0x2a3ad  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveDirectoryUserLinksFromGroup(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a3b2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x2a3b7  stloc.s  0xE
0x2a3b9  br.s     loc_2A3D1
0x2a3bb  ldloc.s  0xE
0x2a3bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x2a3c2  ldloc.s  4
0x2a3c4  ldloc.1
0x2a3c5  ldloc.s  0xD
0x2a3c7  callvirt instance bool GroupIdsOfInterest::IsGroupAnAdminGroup(valuetype [mscorlib]System.Guid groupObjectId)
0x2a3cc  call     void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::AddDirectoryLinkToUsersToProcessForCloud(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag linkData, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser> usersToProcess, bool isAdminGroup)
0x2a3d1  ldloc.s  0xE
0x2a3d3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a3d8  brtrue.s loc_2A3BB
0x2a3da  leave.s  loc_2A3E8
0x2a3dc  ldloc.s  0xE
0x2a3de  brfalse.s loc_2A3E7
0x2a3e0  ldloc.s  0xE
0x2a3e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a3e7  endfinally
0x2a3e8  ldloca.s 0xC
0x2a3ea  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x2a3ef  brtrue.s loc_2A39B
0x2a3f1  leave.s  loc_2A401
0x2a3f3  ldloca.s 0xC
0x2a3f5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x2a3fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a400  endfinally
0x2a401  ldarg.s  4
0x2a403  brfalse.s loc_2A40D
0x2a405  ldarg.1
0x2a406  ldloc.s  4
0x2a408  call     void Microsoft.Crm.CrmLive.Provisioning.ConvertSubscriptionUserDecorator::DecorateDirectoryObjectUsersWithSubscriptionMappingInfo(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser> users)
0x2a40d  ldloc.s  4
0x2a40f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser>::get_Count()
0x2a414  ldc.i4.0
0x2a415  ble.s    loc_2A45B
0x2a417  ldloc.s  4
0x2a419  ldc.i4.s 0x14
0x2a41b  call     T0x2B00005E
0x2a420  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser[]>::GetEnumerator()
0x2a425  stloc.s  0xF
0x2a427  br.s     loc_2A442
0x2a429  ldloca.s 0xF
0x2a42b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser[]>::get_Current()
0x2a430  ldarg.2
0x2a431  ldc.i4.0
0x2a432  ldloca.s 0x10
0x2a434  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x2a43a  ldloc.s  0x10
0x2a43c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.ProvisioningEngine.Sync.SyncDataQueueItemCreator::CreateUserBatchQueueItem(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser>, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase, valuetype [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.UserProvisioningTrigger, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x2a441  stloc.2
0x2a442  ldloca.s 0xF
0x2a444  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser[]>::MoveNext()
0x2a449  brtrue.s loc_2A429
0x2a44b  leave.s  loc_2A45B
0x2a44d  ldloca.s 0xF
0x2a44f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser[]>
0x2a455  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a45a  endfinally
0x2a45b  ldarg.0
0x2a45c  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a461  ldarg.1
0x2a462  ldloc.0
0x2a463  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.PersistData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges::get_ChangesPersistData()
0x2a468  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::PersistCloudChanges(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.PersistData)
0x2a46d  ldloc.0
0x2a46e  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges::get_More()
0x2a473  brfalse.s loc_2A49E
0x2a475  ldarg.0
0x2a476  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::_directoryProvider
0x2a47b  ldarg.1
0x2a47c  ldarg.3
0x2a47d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveCloudChangesForOrganization(valuetype [mscorlib]System.Guid, bool)
0x2a482  stloc.0
0x2a483  ldloc.0
0x2a484  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges::get_More()
0x2a489  brtrue   loc_2A17E
0x2a48e  ldloc.0
0x2a48f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.ReceivedObjectOrLink> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges::get_ReceivedObjectsAndLinks()
0x2a494  call     T0x2B0000AD
0x2a499  brtrue   loc_2A17E
0x2a49e  ldloc.0
0x2a49f  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.CloudChanges::get_More()
0x2a4a4  brtrue.s loc_2A4AC
0x2a4a6  ldarg.1
0x2a4a7  call     void Microsoft.Crm.CrmLive.Provisioning.SyncDataExecutor::SetMultiGeoIsPendingServiceInstanceMove(valuetype [mscorlib]System.Guid organizationId)
0x2a4ac  ldloc.2
0x2a4ad  ret
```
