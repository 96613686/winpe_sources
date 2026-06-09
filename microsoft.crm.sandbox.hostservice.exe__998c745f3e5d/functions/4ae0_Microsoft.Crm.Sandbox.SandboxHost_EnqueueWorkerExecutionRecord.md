# Microsoft.Crm.Sandbox.SandboxHost::EnqueueWorkerExecutionRecord

- ea: `0x4ae0`
- end: `0x4b70`
- name: `Microsoft.Crm.Sandbox.SandboxHost::EnqueueWorkerExecutionRecord`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9ee0`

## callees

- `0x4ae0`
- `0x4b70`

## string_xrefs

- `0x4b27`: `SandboxHost.EnqueueWorkerExecutionRecord: create new WXR queue for scale group: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4ae0  ldarg.0
0x4ae1  ldstr    aWorkerexecutio// "workerExecutionRecord"
0x4ae6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4aeb  ldsfld   object Microsoft.Crm.Sandbox.SandboxHost::_queueLock
0x4af0  stloc.0
0x4af1  ldc.i4.0
0x4af2  stloc.1
0x4af3  ldloc.0
0x4af4  ldloca.s 1
0x4af6  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4afb  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>> Microsoft.Crm.Sandbox.SandboxHost::_workerExecutionRecordQueueDictionary
0x4b00  ldarg.0
0x4b01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_ScaleGroupId()
0x4b06  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>>::ContainsKey(var<u1>)
0x4b0b  brfalse.s loc_4B20
0x4b0d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>> Microsoft.Crm.Sandbox.SandboxHost::_workerExecutionRecordQueueDictionary
0x4b12  ldarg.0
0x4b13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_ScaleGroupId()
0x4b18  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>>::get_Item(void)
0x4b1d  stloc.2
0x4b1e  br.s     loc_4B5C
0x4b20  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4b25  ldc.i4.s 0x26
0x4b27  ldstr    aSandboxhostEnq// "SandboxHost.EnqueueWorkerExecutionRecor"...
0x4b2c  ldc.i4.1
0x4b2d  newarr   [mscorlib]System.Object
0x4b32  dup
0x4b33  ldc.i4.0
0x4b34  ldarg.0
0x4b35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_ScaleGroupId()
0x4b3a  box      [mscorlib]System.Guid
0x4b3f  stelem.ref
0x4b40  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b45  newobj   instance void class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::.ctor()
0x4b4a  stloc.2
0x4b4b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>> Microsoft.Crm.Sandbox.SandboxHost::_workerExecutionRecordQueueDictionary
0x4b50  ldarg.0
0x4b51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_ScaleGroupId()
0x4b56  ldloc.2
0x4b57  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>>::set_Item(var<u1>, !!T0)
0x4b5c  ldarg.0
0x4b5d  ldloc.2
0x4b5e  call     void Microsoft.Crm.Sandbox.SandboxHost::EnqueueWorkerExecutionRecord(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord workerExecutionRecord, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord> workerExecutionRecordQueue)
0x4b63  leave.s  loc_4B6F
0x4b65  ldloc.1
0x4b66  brfalse.s loc_4B6E
0x4b68  ldloc.0
0x4b69  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4b6e  endfinally
0x4b6f  ret
```
