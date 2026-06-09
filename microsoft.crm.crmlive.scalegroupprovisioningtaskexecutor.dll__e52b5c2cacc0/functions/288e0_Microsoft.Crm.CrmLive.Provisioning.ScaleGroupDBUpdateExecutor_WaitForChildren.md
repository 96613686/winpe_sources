# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::WaitForChildren

- ea: `0x288e0`
- end: `0x289db`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::WaitForChildren`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x28680`

## callees

- `0x288e0`
- `0x289e0`

## string_xrefs

- `0x289a8`: `OrganizationDBUpdate queueItem failed for {0} organizations:\n{1}\n\nStatusDetail for the FIRST failure in the list:\n\n {2}`
- `0x289d0`: `OrganizationDBUpdate queueItem succeeded for all organizations!`

## pseudocode

```c

```

## disassembly

```asm
0x288e0  ldc.i4.0
0x288e1  stloc.0
0x288e2  ldsfld   string [mscorlib]System.String::Empty
0x288e7  stloc.1
0x288e8  ldsfld   string [mscorlib]System.String::Empty
0x288ed  stloc.2
0x288ee  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::.ctor()
0x288f3  ldarg.0
0x288f4  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem[] [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueManager::PeekItemsByParent(valuetype [mscorlib]System.Guid)
0x288f9  stloc.3
0x288fa  ldc.i4.0
0x288fb  stloc.s  4
0x288fd  br       loc_28993
0x28902  ldloc.3
0x28903  ldloc.s  4
0x28905  ldelem.ref
0x28906  stloc.s  5
0x28908  ldloc.s  5
0x2890a  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::IsFailed()
0x2890f  brtrue.s loc_28928
0x28911  ldloc.s  5
0x28913  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_Status()
0x28918  ldc.i4.4
0x28919  beq.s    loc_28928
0x2891b  ldc.i4.s 0xC
0x2891d  ldstr    aWaiting// "Waiting"
0x28922  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x28927  ret
0x28928  ldloc.s  5
0x2892a  callvirt instance bool [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem::IsFailed()
0x2892f  brfalse.s loc_2898D
0x28931  ldloc.0
0x28932  ldc.i4.1
0x28933  add
0x28934  stloc.0
0x28935  ldc.i4.5
0x28936  newarr   [mscorlib]System.String
0x2893b  dup
0x2893c  ldc.i4.0
0x2893d  ldloc.1
0x2893e  stelem.ref
0x2893f  dup
0x28940  ldc.i4.1
0x28941  ldloc.s  5
0x28943  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x28948  stloc.s  6
0x2894a  ldloca.s 6
0x2894c  constrained. [mscorlib]System.Guid
0x28952  callvirt instance string [mscorlib]System.Object::ToString()
0x28957  stelem.ref
0x28958  dup
0x28959  ldc.i4.2
0x2895a  ldstr    asc_35406// " "
0x2895f  stelem.ref
0x28960  dup
0x28961  ldc.i4.3
0x28962  ldloc.s  5
0x28964  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_OrganizationId()
0x28969  call     string Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::TryGetOrganizationUrlName(valuetype [mscorlib]System.Guid organizationId)
0x2896e  stelem.ref
0x2896f  dup
0x28970  ldc.i4.4
0x28971  ldstr    asc_42BDE// "\n"
0x28976  stelem.ref
0x28977  call     string [mscorlib]System.String::Concat(string[])
0x2897c  stloc.1
0x2897d  ldloc.2
0x2897e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28983  brfalse.s loc_2898D
0x28985  ldloc.s  5
0x28987  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_StatusDetail()
0x2898c  stloc.2
0x2898d  ldloc.s  4
0x2898f  ldc.i4.1
0x28990  add
0x28991  stloc.s  4
0x28993  ldloc.s  4
0x28995  ldloc.3
0x28996  ldlen
0x28997  conv.i4
0x28998  blt      loc_28902
0x2899d  ldloc.0
0x2899e  ldc.i4.0
0x2899f  ble.s    loc_289CF
0x289a1  ldc.i4.s 0xB
0x289a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x289a8  ldstr    aOrganizationdb// "OrganizationDBUpdate queueItem failed f"...
0x289ad  ldc.i4.3
0x289ae  newarr   [mscorlib]System.Object
0x289b3  dup
0x289b4  ldc.i4.0
0x289b5  ldloc.0
0x289b6  box      [mscorlib]System.Int32
0x289bb  stelem.ref
0x289bc  dup
0x289bd  ldc.i4.1
0x289be  ldloc.1
0x289bf  stelem.ref
0x289c0  dup
0x289c1  ldc.i4.2
0x289c2  ldloc.2
0x289c3  stelem.ref
0x289c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x289c9  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x289ce  ret
0x289cf  ldc.i4.4
0x289d0  ldstr    aOrganizationdb_0// "OrganizationDBUpdate queueItem succeede"...
0x289d5  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x289da  ret
```
