# Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckNumberOfWorkerProcesses

- ea: `0x7150`
- end: `0x7222`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CheckNumberOfWorkerProcesses`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xc9f0`

## callees

- `0x48e0`
- `0x7150`
- `0x9730`
- `0x9770`
- `0x9de0`

## string_xrefs

- `0x719c`: `SandboxWorkerManager.CheckNumberOfWorkerProcesses: processPoolCopy.Count: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7150  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x7155  ldc.i4.1
0x7156  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x715b  stloc.0
0x715c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7161  ldc.i4.s 0x28
0x7163  ldstr    aSandboxworkerm_40// "SandboxWorkerManager.CheckNumberOfWorke"...
0x7168  ldc.i4.1
0x7169  newarr   [mscorlib]System.Object
0x716e  dup
0x716f  ldc.i4.0
0x7170  ldloc.0
0x7171  box      [mscorlib]System.Int32
0x7176  stelem.ref
0x7177  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x717c  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x7181  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Count()
0x7186  ldloc.0
0x7187  bgt.s    loc_718A
0x7189  ret
0x718a  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x718f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x7194  stloc.1
0x7195  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x719a  ldc.i4.s 0x28
0x719c  ldstr    aSandboxworkerm_41// "SandboxWorkerManager.CheckNumberOfWorke"...
0x71a1  ldc.i4.1
0x71a2  newarr   [mscorlib]System.Object
0x71a7  dup
0x71a8  ldc.i4.0
0x71a9  ldloc.1
0x71aa  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Count()
0x71af  box      [mscorlib]System.Int32
0x71b4  stelem.ref
0x71b5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x71ba  volatile.
0x71bc  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_shutdown
0x71c1  brfalse.s loc_71C4
0x71c3  ret
0x71c4  ldloc.1
0x71c5  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>, int32> <>c::<>9__22_0
0x71ca  dup
0x71cb  brtrue.s loc_71E4
0x71cd  pop
0x71ce  ldsfld   class <>c <>c::<>9
0x71d3  ldftn    instance int32 <>c::<CheckNumberOfWorkerProcesses>b__22_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> worker)
0x71d9  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>, int32>::.ctor(object, native int)
0x71de  dup
0x71df  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>, int32> <>c::<>9__22_0
0x71e4  call     T0x2B00000C
0x71e9  call     T0x2B00000D
0x71ee  stloc.3
0x71ef  ldloca.s 3
0x71f1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Value()
0x71f6  stloc.2
0x71f7  ldnull
0x71f8  ldloc.2
0x71f9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x71fe  ldc.i4.s 0x28
0x7200  ldstr    aSandboxworkerm_42// "SandboxWorkerManager.CheckNumberOfWorke"...
0x7205  ldc.i4.1
0x7206  newarr   [mscorlib]System.Object
0x720b  dup
0x720c  ldc.i4.0
0x720d  ldloc.2
0x720e  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x7213  stelem.ref
0x7214  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7219  ldloc.2
0x721a  ldc.i4.s 0xA
0x721c  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x7221  ret
```
