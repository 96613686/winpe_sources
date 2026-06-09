# Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcessInternal

- ea: `0x7610`
- end: `0x7768`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcessInternal`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x7370`

## callees

- `0xf10`
- `0xf20`
- `0xf30`
- `0xf40`
- `0xf50`
- `0x1190`
- `0x7610`
- `0x7770`
- `0xcc70`

## string_xrefs

- `0x762c`: `SandboxWorkerManager.GetWorkerProcessInternal:Thread[{0:d4}] SandboxWorkerProcess.GetWorkerProcessInternal`
- `0x76de`: `SandboxWorkerManager.GetWorkerProcessInternal: Thread[{0:d4}] organization {1} using useDrawbridgeIsolation {2} not found in organizationWorkerList`
- `0x7727`: `SandboxWorkerManager.GetWorkerProcessInternal: Thread[{0:d4}] Did not find organization in Organization Worker List`

## pseudocode

```c

```

## disassembly

```asm
0x7610  newobj   instance void <>c__DisplayClass26_0::.ctor()
0x7615  stloc.0
0x7616  ldloc.0
0x7617  ldarg.0
0x7618  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x761d  ldloc.0
0x761e  ldarg.1
0x761f  stfld    bool <>c__DisplayClass26_0::useDrawbridgeIsolation
0x7624  ldloc.0
0x7625  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x762a  ldc.i4.s 0x21
0x762c  ldstr    aSandboxworkerm_51// "SandboxWorkerManager.GetWorkerProcessIn"...
0x7631  ldc.i4.1
0x7632  newarr   [mscorlib]System.Object
0x7637  dup
0x7638  ldc.i4.0
0x7639  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x763e  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7643  box      [mscorlib]System.Int32
0x7648  stelem.ref
0x7649  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x764e  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x7653  stloc.1
0x7654  ldnull
0x7655  stloc.2
0x7656  ldnull
0x7657  stloc.3
0x7658  ldloc.0
0x7659  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x765e  ldloc.0
0x765f  ldfld    bool <>c__DisplayClass26_0::useDrawbridgeIsolation
0x7664  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>::.ctor(var<u1>, !!T0)
0x7669  stloc.s  4
0x766b  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList> Microsoft.Crm.Sandbox.SandboxWorkerManager::_organizationMap
0x7670  ldloc.s  4
0x7672  ldloc.0
0x7673  ldftn    instance class Microsoft.Crm.Sandbox.OrganizationWorkerList <>c__DisplayClass26_0::<GetWorkerProcessInternal>b__0(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool> Guid)
0x7679  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::.ctor(object, native int)
0x767e  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::GetOrAdd(void, var<u1>)
0x7683  stloc.2
0x7684  ldarg.2
0x7685  ldloc.2
0x7686  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::get_OrgCleanBucketsCount()
0x768b  stind.i4
0x768c  ldarg.3
0x768d  ldloc.2
0x768e  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::get_OrgReadyBucketsCount()
0x7693  stind.i4
0x7694  ldarg.s  4
0x7696  ldloc.2
0x7697  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::get_OrgInitializingBucketsCount()
0x769c  stind.i4
0x769d  ldarg.s  5
0x769f  ldloc.2
0x76a0  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::get_OrgWaitingInitializingBucketCount()
0x76a5  stind.i4
0x76a6  ldarg.s  6
0x76a8  ldloc.2
0x76a9  callvirt instance int32 Microsoft.Crm.Sandbox.OrganizationWorkerList::get_OrgInactiveBucketsCount()
0x76ae  stind.i4
0x76af  ldloc.2
0x76b0  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x76b5  ldloc.0
0x76b6  ldftn    instance class Microsoft.Crm.Sandbox.SandboxWorkerProcess <>c__DisplayClass26_0::<GetWorkerProcessInternal>b__1()
0x76bc  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::.ctor(object, native int)
0x76c1  ldloc.0
0x76c2  ldftn    instance void <>c__DisplayClass26_0::<GetWorkerProcessInternal>b__2()
0x76c8  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x76cd  ldloca.s 3
0x76cf  callvirt instance bool Microsoft.Crm.Sandbox.OrganizationWorkerList::TryGetNextWorkerProcess(class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> processPool, class [mscorlib]System.Func`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess> getCleanWorkerProcessFromQueue, class [mscorlib]System.Action startNewWorkersInBackground, [out] class Microsoft.Crm.Sandbox.SandboxWorkerProcess& returnValue)
0x76d4  brtrue.s loc_771C
0x76d6  ldloc.0
0x76d7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x76dc  ldc.i4.s 0x21
0x76de  ldstr    aSandboxworkerm_52// "SandboxWorkerManager.GetWorkerProcessIn"...
0x76e3  ldc.i4.3
0x76e4  newarr   [mscorlib]System.Object
0x76e9  dup
0x76ea  ldc.i4.0
0x76eb  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x76f0  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x76f5  box      [mscorlib]System.Int32
0x76fa  stelem.ref
0x76fb  dup
0x76fc  ldc.i4.1
0x76fd  ldloc.0
0x76fe  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x7703  box      [mscorlib]System.Guid
0x7708  stelem.ref
0x7709  dup
0x770a  ldc.i4.2
0x770b  ldloc.0
0x770c  ldfld    bool <>c__DisplayClass26_0::useDrawbridgeIsolation
0x7711  box      [mscorlib]System.Boolean
0x7716  stelem.ref
0x7717  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x771c  ldloc.3
0x771d  brtrue.s loc_7749
0x771f  ldloc.0
0x7720  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x7725  ldc.i4.s 0x21
0x7727  ldstr    aSandboxworkerm_53// "SandboxWorkerManager.GetWorkerProcessIn"...
0x772c  ldc.i4.1
0x772d  newarr   [mscorlib]System.Object
0x7732  dup
0x7733  ldc.i4.0
0x7734  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7739  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x773e  box      [mscorlib]System.Int32
0x7743  stelem.ref
0x7744  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7749  ldloc.1
0x774a  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x774f  ldloc.1
0x7750  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x7755  conv.r8
0x7756  ldloc.0
0x7757  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass26_0::organizationId
0x775c  ldstr    aSandboxworkerm_54// "SandboxWorkerManager.GetWorkerProcessIn"...
0x7761  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::LogExecutionTime(float64 elapsedTimeInMSecs, valuetype [mscorlib]System.Guid organizationId, string methodName)
0x7766  ldloc.3
0x7767  ret
```
