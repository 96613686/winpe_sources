# Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::Execute

- ea: `0x28560`
- end: `0x285f4`
- name: `Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::Execute`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x28560`
- `0x28600`
- `0x28680`

## string_xrefs

- `0x2858f`: `SGCONFIG`
- `0x285bf`: `ScaleGroup statsdb updates are not yet implemented`

## pseudocode

```c

```

## disassembly

```asm
0x28560  ldarg.1
0x28561  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x28566  stloc.0
0x28567  ldloc.0
0x28568  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x2856d  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::Deserialize(string)
0x28572  stloc.1
0x28573  ldnull
0x28574  stloc.2
0x28575  ldloc.1
0x28576  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_DatabaseType()
0x2857b  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x28580  stloc.3
0x28581  ldloc.3
0x28582  ldstr    aSgorgs// "SGORGS"
0x28587  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2858c  brtrue.s loc_285AA
0x2858e  ldloc.3
0x2858f  ldstr    aSgconfig// "SGCONFIG"
0x28594  call     bool [mscorlib]System.String::op_Equality(string, string)
0x28599  brtrue.s loc_285B4
0x2859b  ldloc.3
0x2859c  ldstr    aSgstats// "SGSTATS"
0x285a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x285a6  brtrue.s loc_285BD
0x285a8  br.s     loc_285CC
0x285aa  ldloc.0
0x285ab  ldloc.1
0x285ac  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::ExecuteOrgDBUpdates(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem item, class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo info)
0x285b1  stloc.2
0x285b2  br.s     loc_285F2
0x285b4  ldloc.1
0x285b5  call     class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateExecutor::ExecuteConfigDBUpdates(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo info)
0x285ba  stloc.2
0x285bb  br.s     loc_285F2
0x285bd  ldc.i4.s 0xB
0x285bf  ldstr    aScalegroupStat// "ScaleGroup statsdb updates are not yet "...
0x285c4  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x285c9  stloc.2
0x285ca  br.s     loc_285F2
0x285cc  ldc.i4.s 0xB
0x285ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x285d3  ldstr    a0IsNotARecogni// "{0} is not a recognized ScaleGroup data"...
0x285d8  ldc.i4.1
0x285d9  newarr   [mscorlib]System.Object
0x285de  dup
0x285df  ldc.i4.0
0x285e0  ldloc.1
0x285e1  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.ScaleGroupDBUpdateInfo::get_DatabaseType()
0x285e6  stelem.ref
0x285e7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x285ec  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x285f1  stloc.2
0x285f2  ldloc.2
0x285f3  ret
```
