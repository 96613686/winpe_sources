# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Write

- ea: `0x4d90`
- end: `0x4e6f`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Write`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4af0`
- `0x54c0`

## callees

- `0x4ce0`
- `0x4cf0`
- `0x4d90`
- `0x4e70`
- `0x4e90`

## pseudocode

```c

```

## disassembly

```asm
0x4d90  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4d95  stloc.0
0x4d96  ldarg.2
0x4d97  brtrue.s loc_4DA4
0x4d99  ldstr    aData// "data"
0x4d9e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4da3  throw
0x4da4  ldarg.2
0x4da5  ldlen
0x4da6  conv.i4
0x4da7  call     int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_DefaultFieldCount()
0x4dac  add
0x4dad  newarr   [mscorlib]System.Object
0x4db2  stloc.1
0x4db3  ldloc.1
0x4db4  ldc.i4.0
0x4db5  call     int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_ThreadId()
0x4dba  box      [mscorlib]System.Int32
0x4dbf  stelem.ref
0x4dc0  ldloc.1
0x4dc1  ldc.i4.1
0x4dc2  ldsfld   int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::ProcessId
0x4dc7  box      [mscorlib]System.Int32
0x4dcc  stelem.ref
0x4dcd  ldloc.1
0x4dce  ldc.i4.2
0x4dcf  ldarg.0
0x4dd0  ldfld    string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::containerId
0x4dd5  stelem.ref
0x4dd6  ldloc.1
0x4dd7  ldc.i4.3
0x4dd8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::get_ActivityId()
0x4ddd  stloc.s  4
0x4ddf  ldloca.s 4
0x4de1  constrained. [mscorlib]System.Guid
0x4de7  callvirt instance string [mscorlib]System.Object::ToString()
0x4dec  stelem.ref
0x4ded  ldloc.1
0x4dee  ldc.i4.4
0x4def  ldarga.s 1
0x4df1  constrained. [mscorlib]System.Guid
0x4df7  callvirt instance string [mscorlib]System.Object::ToString()
0x4dfc  stelem.ref
0x4dfd  ldarg.2
0x4dfe  ldc.i4.0
0x4dff  ldloc.1
0x4e00  call     int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_DefaultFieldCount()
0x4e05  ldarg.2
0x4e06  ldlen
0x4e07  conv.i4
0x4e08  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x4e0d  ldarg.0
0x4e0e  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x4e13  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::EnterReadLock()
0x4e18  ldarg.0
0x4e19  ldfld    native int Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentTableHandle
0x4e1e  stloc.3
0x4e1f  ldsfld   class [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::writer
0x4e24  ldloc.3
0x4e25  ldarg.0
0x4e26  ldfld    unsigned int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentSchemaHandle
0x4e2b  ldloc.1
0x4e2c  ldloc.0
0x4e2d  box      [mscorlib]System.DateTime
0x4e32  callvirt instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer::WriteRecordToTable(native int, unsigned int32, object[], modopt([mscorlib]System.Runtime.CompilerServices.IsBoxed) modopt([mscorlib]System.DateTime) class [mscorlib]System.ValueType)
0x4e37  stloc.2
0x4e38  leave.s  loc_4E46
0x4e3a  ldarg.0
0x4e3b  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::tableCreationLock
0x4e40  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitReadLock()
0x4e45  endfinally
0x4e46  ldloc.2
0x4e47  call     bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::IsTableCorrupted(int32 result)
0x4e4c  brfalse.s loc_4E6E
0x4e4e  ldarg.0
0x4e4f  ldloc.3
0x4e50  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::EnsureValidTableHandle(native int tableHandle)
0x4e55  ldsfld   class [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::writer
0x4e5a  ldloc.3
0x4e5b  ldarg.0
0x4e5c  ldfld    unsigned int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::currentSchemaHandle
0x4e61  ldloc.1
0x4e62  ldloc.0
0x4e63  box      [mscorlib]System.DateTime
0x4e68  callvirt instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer::WriteRecordToTable(native int, unsigned int32, object[], modopt([mscorlib]System.Runtime.CompilerServices.IsBoxed) modopt([mscorlib]System.DateTime) class [mscorlib]System.ValueType)
0x4e6d  pop
0x4e6e  ret
```
