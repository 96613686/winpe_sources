# Microsoft.Crm.Asynchronous.AsyncService::SetThreadPoolLimits

- ea: `0x1120`
- end: `0x11f1`
- name: `Microsoft.Crm.Asynchronous.AsyncService::SetThreadPoolLimits`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0xc40`
- `0x1120`

## string_xrefs

- `0x1136`: `AsyncMinWorkerThreads`
- `0x1150`: `AsyncMinIOThreads`
- `0x1191`: `CRMAsyncService - SetThreadPoolLimits failed to SetMinThreads. MinWorkerThreads:{0} -> {1}; MinIOThreads:{2} -> {3}`
- `0x11d4`: `CrmAsyncService - SetThreadPoolLimits failed with exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1120  ldarg.0
0x1121  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x1126  brfalse.s loc_112D
0x1128  leave    loc_11F0
0x112d  ldloca.s 0
0x112f  ldloca.s 1
0x1131  call     void [mscorlib]System.Threading.ThreadPool::GetMinThreads(int32&, int32&)
0x1136  ldstr    aAsyncminworker// "AsyncMinWorkerThreads"
0x113b  ldc.i4   0x3E8
0x1140  box      [mscorlib]System.Int32
0x1145  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x114a  unbox.any [mscorlib]System.Int32
0x114f  stloc.2
0x1150  ldstr    aAsyncminiothre// "AsyncMinIOThreads"
0x1155  ldc.i4   0x100
0x115a  box      [mscorlib]System.Int32
0x115f  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1164  unbox.any [mscorlib]System.Int32
0x1169  stloc.3
0x116a  ldloc.2
0x116b  ldc.i4.0
0x116c  bgt.s    loc_1171
0x116e  ldloc.0
0x116f  br.s     loc_1172
0x1171  ldloc.2
0x1172  stloc.s  4
0x1174  ldloc.3
0x1175  ldc.i4.0
0x1176  bgt.s    loc_117B
0x1178  ldloc.1
0x1179  br.s     loc_117C
0x117b  ldloc.3
0x117c  stloc.s  5
0x117e  ldloc.s  4
0x1180  ldloc.s  5
0x1182  call     bool [mscorlib]System.Threading.ThreadPool::SetMinThreads(int32, int32)
0x1187  brtrue.s loc_11C7
0x1189  ldnull
0x118a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x118f  ldc.i4.s 0x15
0x1191  ldstr    aCrmasyncservic// "CRMAsyncService - SetThreadPoolLimits f"...
0x1196  ldc.i4.4
0x1197  newarr   [mscorlib]System.Object
0x119c  dup
0x119d  ldc.i4.0
0x119e  ldloc.0
0x119f  box      [mscorlib]System.Int32
0x11a4  stelem.ref
0x11a5  dup
0x11a6  ldc.i4.1
0x11a7  ldloc.s  4
0x11a9  box      [mscorlib]System.Int32
0x11ae  stelem.ref
0x11af  dup
0x11b0  ldc.i4.2
0x11b1  ldloc.1
0x11b2  box      [mscorlib]System.Int32
0x11b7  stelem.ref
0x11b8  dup
0x11b9  ldc.i4.3
0x11ba  ldloc.s  5
0x11bc  box      [mscorlib]System.Int32
0x11c1  stelem.ref
0x11c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11c7  leave.s  loc_11F0
0x11c9  stloc.s  6
0x11cb  ldloc.s  6
0x11cd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x11d2  ldc.i4.s 0x15
0x11d4  ldstr    aCrmasyncservic_0// "CrmAsyncService - SetThreadPoolLimits f"...
0x11d9  ldc.i4.1
0x11da  newarr   [mscorlib]System.Object
0x11df  dup
0x11e0  ldc.i4.0
0x11e1  ldloc.s  6
0x11e3  callvirt instance string [mscorlib]System.Object::ToString()
0x11e8  stelem.ref
0x11e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11ee  leave.s  loc_11F0
0x11f0  ret
```
