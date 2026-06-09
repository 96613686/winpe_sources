# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::OnAfterOrgDBUpdate

- ea: `0x28bb0`
- end: `0x28c46`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::OnAfterOrgDBUpdate`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x28a90`

## callees

- `0x28a70`
- `0x28bb0`
- `0x28d80`
- `0x28e20`

## string_xrefs

- `0x28bcc`: `Org DB Update queue item Id is not valid`
- `0x28beb`: `Child upgrade task item is still active:  Current task should not be called.`
- `0x28c0d`: `Org DB Update failed for child queue item:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x28bb0  ldarg.0
0x28bb1  call     instance class Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateRuntimeData Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::get_RuntimeData()
0x28bb6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateRuntimeData::get_OrgDBUpdateItemId()
0x28bbb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28bc0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28bc5  brfalse.s loc_28BE2
0x28bc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x28bcc  ldstr    aOrgDbUpdateQue// "Org DB Update queue item Id is not vali"...
0x28bd1  ldc.i4.0
0x28bd2  newarr   [mscorlib]System.Object
0x28bd7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28bdc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x28be1  throw
0x28be2  ldarg.1
0x28be3  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::IsActive()
0x28be8  ldc.i4.0
0x28be9  ceq
0x28beb  ldstr    aChildUpgradeTa// "Child upgrade task item is still active"...
0x28bf0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x28bf5  ldarg.1
0x28bf6  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::IsFailed()
0x28bfb  brfalse.s loc_28C31
0x28bfd  ldarg.0
0x28bfe  ldc.i4.5
0x28bff  ldc.i4.1
0x28c00  ldc.i4.0
0x28c01  call     instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::RefreshUpdateHistory(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OperationStatus status, [opt] bool failedOnDbUpdate, [opt] bool failedOnSolutionUpdate)
0x28c06  ldc.i4.s 0xB
0x28c08  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28c0d  ldstr    aOrgDbUpdateFai// "Org DB Update failed for child queue it"...
0x28c12  ldc.i4.1
0x28c13  newarr   [mscorlib]System.Object
0x28c18  dup
0x28c19  ldc.i4.0
0x28c1a  ldarg.1
0x28c1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_QueueItemId()
0x28c20  box      [mscorlib]System.Guid
0x28c25  stelem.ref
0x28c26  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x28c2b  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x28c30  ret
0x28c31  ldarg.0
0x28c32  ldc.i4.6
0x28c33  ldc.i4.0
0x28c34  ldc.i4.0
0x28c35  call     instance void Microsoft.Crm.CrmLive.Provisioning.ScaleGroupUpdateExecutor::RefreshUpdateHistory(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OperationStatus status, [opt] bool failedOnDbUpdate, [opt] bool failedOnSolutionUpdate)
0x28c3a  ldc.i4.4
0x28c3b  ldstr    aSuccess// "success"
0x28c40  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x28c45  ret
```
