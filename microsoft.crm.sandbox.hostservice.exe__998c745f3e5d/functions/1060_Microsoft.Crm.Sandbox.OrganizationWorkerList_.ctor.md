# Microsoft.Crm.Sandbox.OrganizationWorkerList::.ctor

- ea: `0x1060`
- end: `0x1183`
- name: `Microsoft.Crm.Sandbox.OrganizationWorkerList::.ctor`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xcc80`
- `0xccf0`

## callees

- `0xc20`
- `0x1060`
- `0x48e0`

## string_xrefs

- `0x1149`: `OrganizationWorkerList:Thread[{0:d4}] Initializing OrganizationWorkerList with {1} MaxConcurrentWorkerProcessRequests and {2} MaxWorkerProcessCount`

## pseudocode

```c

```

## disassembly

```asm
0x1060  ldarg.0
0x1061  newobj   instance void [mscorlib]System.Object::.ctor()
0x1066  stfld    object Microsoft.Crm.Sandbox.OrganizationWorkerList::_scaleDownLock
0x106b  ldarg.0
0x106c  ldc.r8   15.0
0x1075  stfld    float64 Microsoft.Crm.Sandbox.OrganizationWorkerList::maxWaitTimeInSeconds
0x107a  ldarg.0
0x107b  call     instance void [mscorlib]System.Object::.ctor()
0x1080  ldarg.0
0x1081  ldnull
0x1082  stfld    class Microsoft.Crm.Sandbox.OrganizationWorkerBucket Microsoft.Crm.Sandbox.OrganizationWorkerList::_previousUsedBucket
0x1087  ldarg.0
0x1088  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x108d  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.OrganizationWorkerList::_lastScaleDown
0x1092  ldarg.0
0x1093  ldc.i4.0
0x1094  conv.i8
0x1095  stfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x109a  ldarg.0
0x109b  ldc.i4.0
0x109c  conv.i8
0x109d  stfld    int64 Microsoft.Crm.Sandbox.OrganizationWorkerList::_workersReadyCount
0x10a2  ldarg.0
0x10a3  ldarg.1
0x10a4  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x10a9  ldarg.0
0x10aa  ldc.i4.0
0x10ab  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_nextId
0x10b0  ldarg.0
0x10b1  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x10b6  ldc.i4.s 0x1B
0x10b8  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x10bd  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x10c2  ldarg.0
0x10c3  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x10c8  ldc.i4.s 0x1C
0x10ca  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x10cf  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_minConcurrentRequests
0x10d4  ldarg.0
0x10d5  ldc.i4.0
0x10d6  ldc.i4.0
0x10d7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x10dc  ldc.i4.s 0x1D
0x10de  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x10e3  ldc.i4.0
0x10e4  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32, int32)
0x10e9  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.OrganizationWorkerList::_scaleDownEvalInterval
0x10ee  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x10f3  ldc.i4.s 0x1E
0x10f5  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x10fa  stloc.0
0x10fb  ldarg.0
0x10fc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::.ctor()
0x1101  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1106  ldc.i4.0
0x1107  stloc.1
0x1108  br.s     loc_1121
0x110a  ldarg.0
0x110b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket> Microsoft.Crm.Sandbox.OrganizationWorkerList::_workerBucketList
0x1110  ldarg.0
0x1111  ldarg.1
0x1112  ldloc.1
0x1113  newobj   instance void Microsoft.Crm.Sandbox.OrganizationWorkerBucket::.ctor(class Microsoft.Crm.Sandbox.OrganizationWorkerList workerList, valuetype [mscorlib]System.Guid organizationId, int32 id)
0x1118  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.OrganizationWorkerBucket>::Add(var<u1>)
0x111d  ldloc.1
0x111e  ldc.i4.1
0x111f  add
0x1120  stloc.1
0x1121  ldloc.1
0x1122  ldloc.0
0x1123  blt.s    loc_110A
0x1125  ldarg.0
0x1126  ldloc.0
0x1127  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgCleanBucketsCount
0x112c  ldarg.0
0x112d  ldc.i4.0
0x112e  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgReadyBucketsCount
0x1133  ldarg.0
0x1134  ldc.i4.0
0x1135  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgInitializingBucketsCount
0x113a  ldarg.0
0x113b  ldc.i4.0
0x113c  stfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_orgWaitingInitializingBucketCount
0x1141  ldarg.0
0x1142  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.OrganizationWorkerList::_organizationId
0x1147  ldc.i4.s 0x21
0x1149  ldstr    aOrganizationwo_0// "OrganizationWorkerList:Thread[{0:d4}] I"...
0x114e  ldc.i4.3
0x114f  newarr   [mscorlib]System.Object
0x1154  dup
0x1155  ldc.i4.0
0x1156  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x115b  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x1160  box      [mscorlib]System.Int32
0x1165  stelem.ref
0x1166  dup
0x1167  ldc.i4.1
0x1168  ldarg.0
0x1169  ldfld    int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::_maxConcurrentRequests
0x116e  box      [mscorlib]System.Int32
0x1173  stelem.ref
0x1174  dup
0x1175  ldc.i4.2
0x1176  ldloc.0
0x1177  box      [mscorlib]System.Int32
0x117c  stelem.ref
0x117d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1182  ret
```
