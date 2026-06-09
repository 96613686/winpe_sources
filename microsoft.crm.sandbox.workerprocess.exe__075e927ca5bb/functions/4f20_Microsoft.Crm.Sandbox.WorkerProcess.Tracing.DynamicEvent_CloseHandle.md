# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::CloseHandle

- ea: `0x4f20`
- end: `0x4f3b`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::CloseHandle`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4e90`
- `0x5050`

## callees

- `0x4f20`

## pseudocode

```c

```

## disassembly

```asm
0x4f20  ldarg.1
0x4f21  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4f26  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4f2b  brfalse.s loc_4F3A
0x4f2d  ldsfld   class [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::writer
0x4f32  ldarga.s 1
0x4f34  callvirt instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 [Microsoft.Cis.Monitoring.Tables]Microsoft.Cis.Monitoring.Tables.Writer::CloseTable(native int&)
0x4f39  pop
0x4f3a  ret
```
