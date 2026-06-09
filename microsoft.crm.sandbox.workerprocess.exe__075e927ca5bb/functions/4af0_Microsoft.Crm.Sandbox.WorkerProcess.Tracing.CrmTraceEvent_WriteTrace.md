# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::WriteTrace

- ea: `0x4af0`
- end: `0x4b67`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::WriteTrace`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5120`

## callees

- `0x4af0`
- `0x4d90`

## pseudocode

```c

```

## disassembly

```asm
0x4af0  ldc.i4.4
0x4af1  newarr   [mscorlib]System.Object
0x4af6  stloc.0
0x4af7  ldloc.0
0x4af8  ldc.i4.0
0x4af9  ldstr    aTrace// "Trace"
0x4afe  ldarg.2
0x4aff  box      [System]System.Diagnostics.TraceLevel
0x4b04  call     string [mscorlib]System.String::Concat(object, object)
0x4b09  stelem.ref
0x4b0a  ldloc.0
0x4b0b  ldc.i4.1
0x4b0c  ldarga.s 3
0x4b0e  constrained. [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory
0x4b14  callvirt instance string [mscorlib]System.Object::ToString()
0x4b19  stelem.ref
0x4b1a  ldloc.0
0x4b1b  ldc.i4.2
0x4b1c  ldarg.s  6
0x4b1e  brfalse.s loc_4B39
0x4b20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x4b25  ldarg.s  5
0x4b27  dup
0x4b28  brtrue.s loc_4B30
0x4b2a  pop
0x4b2b  ldsfld   string [mscorlib]System.String::Empty
0x4b30  ldarg.s  6
0x4b32  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4b37  br.s     loc_4B3B
0x4b39  ldarg.s  5
0x4b3b  stelem.ref
0x4b3c  ldloc.0
0x4b3d  ldc.i4.3
0x4b3e  ldarg.0
0x4b3f  ldfld    valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::level
0x4b44  ldc.i4.1
0x4b45  beq.s    loc_4B4E
0x4b47  ldsfld   string [mscorlib]System.String::Empty
0x4b4c  br.s     loc_4B5D
0x4b4e  ldarg.s  4
0x4b50  ldc.i4.1
0x4b51  add
0x4b52  ldc.i4.1
0x4b53  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor(int32, bool)
0x4b58  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::StackTraceToString(class [mscorlib]System.Diagnostics.StackTrace)
0x4b5d  stelem.ref
0x4b5e  ldarg.0
0x4b5f  ldarg.1
0x4b60  ldloc.0
0x4b61  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Write(valuetype [mscorlib]System.Guid organizationId, object[] data)
0x4b66  ret
```
