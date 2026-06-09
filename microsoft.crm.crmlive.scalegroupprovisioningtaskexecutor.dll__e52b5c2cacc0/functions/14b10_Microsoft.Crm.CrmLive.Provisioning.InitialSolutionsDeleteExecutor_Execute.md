# Microsoft.Crm.CrmLive.Provisioning.InitialSolutionsDeleteExecutor::Execute

- ea: `0x14b10`
- end: `0x14bc5`
- name: `Microsoft.Crm.CrmLive.Provisioning.InitialSolutionsDeleteExecutor::Execute`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14b10`
- `0x310f0`

## string_xrefs

- `0x14b95`: `Uninstalled initial solutions`
- `0x14ba4`: `Error uninstalling initial solutions`

## pseudocode

```c

```

## disassembly

```asm
0x14b10  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x14b15  stloc.0
0x14b16  ldloc.0
0x14b17  ldarg.1
0x14b18  stfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass1_0::task
0x14b1d  ldloc.0
0x14b1e  ldloc.0
0x14b1f  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass1_0::task
0x14b24  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x14b29  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x14b2e  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass1_0::orgId
0x14b33  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x14b38  ldloc.0
0x14b39  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass1_0::orgId
0x14b3e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14b43  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x14b48  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0x14b4d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x14b52  ldnull
0x14b53  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x14b58  stloc.1
0x14b59  ldloc.0
0x14b5a  ldftn    instance void <>c__DisplayClass1_0::<Execute>b__0(string msg)
0x14b60  newobj   instance void class [mscorlib]System.Action`1<string>::.ctor(object, native int)
0x14b65  stloc.2
0x14b66  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Data.InitialSolutionDataManager::.ctor()
0x14b6b  ldloc.0
0x14b6c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass1_0::orgId
0x14b71  ldloc.1
0x14b72  ldloc.2
0x14b73  ldloc.0
0x14b74  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass1_0::task
0x14b79  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x14b7e  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x14b83  call     instance void [Microsoft.Crm]Microsoft.Crm.Data.InitialSolutionDataManager::TryDeleteInitialSolutions(valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService, class [mscorlib]System.Action`1<string>, string)
0x14b88  leave.s  loc_14B94
0x14b8a  ldloc.1
0x14b8b  brfalse.s loc_14B93
0x14b8d  ldloc.1
0x14b8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14b93  endfinally
0x14b94  ldc.i4.4
0x14b95  ldstr    aUninstalledIni// "Uninstalled initial solutions"
0x14b9a  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x14b9f  stloc.3
0x14ba0  leave.s  loc_14BC3
0x14ba2  stloc.s  4
0x14ba4  ldstr    aErrorUninstall// "Error uninstalling initial solutions"
0x14ba9  ldloc.s  4
0x14bab  ldloc.0
0x14bac  ldfld    class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask <>c__DisplayClass1_0::task
0x14bb1  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x14bb6  callvirt instance int32 [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_RetryCount()
0x14bbb  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::BuildRetry(string, class [mscorlib]System.Exception, int32)
0x14bc0  stloc.3
0x14bc1  leave.s  loc_14BC3
0x14bc3  ldloc.3
0x14bc4  ret
```
