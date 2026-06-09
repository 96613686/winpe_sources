# Microsoft.Crm.ScaleGroupApi.Controllers.SyncApplyRequestController::ProcessResult

- ea: `0x48f0`
- end: `0x496e`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SyncApplyRequestController::ProcessResult`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4810`
- `0x4870`

## callees

- `0x48f0`

## string_xrefs

- `0x4924`: `TaskStatus: {0}, Details: {1}, Exception: {2}, TaskLog: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x48f0  ldarg.0
0x48f1  brfalse.s loc_4968
0x48f3  ldarg.0
0x48f4  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult, string>::get_Item1()
0x48f9  stloc.0
0x48fa  ldarg.0
0x48fb  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult, string>::get_Item2()
0x4900  stloc.1
0x4901  ldloc.0
0x4902  brfalse.s loc_4966
0x4904  ldloc.0
0x4905  callvirt instance class [mscorlib]System.Exception [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Exception()
0x490a  brtrue.s loc_4913
0x490c  ldsfld   string [mscorlib]System.String::Empty
0x4911  br.s     loc_491E
0x4913  ldloc.0
0x4914  callvirt instance class [mscorlib]System.Exception [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Exception()
0x4919  callvirt instance string [mscorlib]System.Object::ToString()
0x491e  stloc.2
0x491f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4924  ldstr    aTaskstatus0Det// "TaskStatus: {0}, Details: {1}, Exceptio"...
0x4929  ldc.i4.4
0x492a  newarr   [mscorlib]System.Object
0x492f  dup
0x4930  ldc.i4.0
0x4931  ldloc.0
0x4932  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Status()
0x4937  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus
0x493c  stelem.ref
0x493d  dup
0x493e  ldc.i4.1
0x493f  ldloc.0
0x4940  callvirt instance string [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Details()
0x4945  stelem.ref
0x4946  dup
0x4947  ldc.i4.2
0x4948  ldloc.2
0x4949  stelem.ref
0x494a  dup
0x494b  ldc.i4.3
0x494c  ldloc.1
0x494d  stelem.ref
0x494e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4953  stloc.3
0x4954  ldloc.0
0x4955  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::get_Status()
0x495a  ldc.i4.4
0x495b  beq.s    loc_4964
0x495d  ldloc.3
0x495e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4963  throw
0x4964  ldloc.3
0x4965  ret
0x4966  ldloc.1
0x4967  ret
0x4968  ldsfld   string [mscorlib]System.String::Empty
0x496d  ret
```
