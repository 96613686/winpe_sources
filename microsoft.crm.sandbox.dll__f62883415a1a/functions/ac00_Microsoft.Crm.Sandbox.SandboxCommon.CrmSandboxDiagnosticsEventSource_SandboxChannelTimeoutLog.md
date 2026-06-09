# Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxChannelTimeoutLog

- ea: `0xac00`
- end: `0xac97`
- name: `Microsoft.Crm.Sandbox.SandboxCommon.CrmSandboxDiagnosticsEventSource::SandboxChannelTimeoutLog`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xac00`

## pseudocode

```c

```

## disassembly

```asm
0xac00  ldarg.0
0xac01  call     instance bool [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::IsEnabled()
0xac06  brfalse  loc_AC96
0xac0b  ldarg.s  6
0xac0d  callvirt instance int32 [mscorlib]System.String::get_Length()
0xac12  ldc.i4   0x3A98
0xac17  ble.s    loc_AC28
0xac19  ldarg.s  6
0xac1b  ldc.i4.0
0xac1c  ldc.i4   0x3A98
0xac21  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xac26  starg.s  6
0xac28  ldarg.0
0xac29  ldc.i4.3
0xac2a  ldc.i4.s 0xD
0xac2c  newarr   [mscorlib]System.Object
0xac31  dup
0xac32  ldc.i4.0
0xac33  ldarg.1
0xac34  box      [mscorlib]System.Guid
0xac39  stelem.ref
0xac3a  dup
0xac3b  ldc.i4.1
0xac3c  ldarg.2
0xac3d  stelem.ref
0xac3e  dup
0xac3f  ldc.i4.2
0xac40  ldarg.3
0xac41  box      [mscorlib]System.Boolean
0xac46  stelem.ref
0xac47  dup
0xac48  ldc.i4.3
0xac49  ldarg.s  4
0xac4b  box      [mscorlib]System.Guid
0xac50  stelem.ref
0xac51  dup
0xac52  ldc.i4.4
0xac53  ldarg.s  5
0xac55  stelem.ref
0xac56  dup
0xac57  ldc.i4.5
0xac58  ldarg.s  6
0xac5a  stelem.ref
0xac5b  dup
0xac5c  ldc.i4.6
0xac5d  ldarg.s  7
0xac5f  stelem.ref
0xac60  dup
0xac61  ldc.i4.7
0xac62  ldarg.s  8
0xac64  box      [mscorlib]System.Int32
0xac69  stelem.ref
0xac6a  dup
0xac6b  ldc.i4.8
0xac6c  ldarg.s  9
0xac6e  stelem.ref
0xac6f  dup
0xac70  ldc.i4.s 9
0xac72  ldarg.s  0xA
0xac74  stelem.ref
0xac75  dup
0xac76  ldc.i4.s 0xA
0xac78  ldarg.s  0xB
0xac7a  stelem.ref
0xac7b  dup
0xac7c  ldc.i4.s 0xB
0xac7e  ldarg.s  0xC
0xac80  box      [mscorlib]System.Guid
0xac85  stelem.ref
0xac86  dup
0xac87  ldc.i4.s 0xC
0xac89  ldarg.s  0xD
0xac8b  box      [mscorlib]System.Int32
0xac90  stelem.ref
0xac91  call     instance void [Microsoft.Diagnostics.Tracing.EventSource]Microsoft.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0xac96  ret
```
