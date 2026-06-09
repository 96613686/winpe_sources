# Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationFailure

- ea: `0x56a0`
- end: `0x5725`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationFailure`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3ca0`
- `0x4000`
- `0x4360`
- `0x4680`

## pseudocode

```c

```

## disassembly

```asm
0x56a0  ldarg.0
0x56a1  ldc.i4.2
0x56a2  ldc.i4.s 0xF
0x56a4  newarr   [mscorlib]System.Object
0x56a9  dup
0x56aa  ldc.i4.0
0x56ab  ldarg.1
0x56ac  box      [mscorlib]System.Guid
0x56b1  stelem.ref
0x56b2  dup
0x56b3  ldc.i4.1
0x56b4  ldarg.2
0x56b5  stelem.ref
0x56b6  dup
0x56b7  ldc.i4.2
0x56b8  ldarg.3
0x56b9  stelem.ref
0x56ba  dup
0x56bb  ldc.i4.3
0x56bc  ldarg.s  4
0x56be  stelem.ref
0x56bf  dup
0x56c0  ldc.i4.4
0x56c1  ldarg.s  5
0x56c3  box      [mscorlib]System.Guid
0x56c8  stelem.ref
0x56c9  dup
0x56ca  ldc.i4.5
0x56cb  ldarg.s  6
0x56cd  stelem.ref
0x56ce  dup
0x56cf  ldc.i4.6
0x56d0  ldarg.s  7
0x56d2  box      [mscorlib]System.Int64
0x56d7  stelem.ref
0x56d8  dup
0x56d9  ldc.i4.7
0x56da  ldarg.s  8
0x56dc  stelem.ref
0x56dd  dup
0x56de  ldc.i4.8
0x56df  ldarg.s  9
0x56e1  box      [mscorlib]System.Int32
0x56e6  stelem.ref
0x56e7  dup
0x56e8  ldc.i4.s 9
0x56ea  ldarg.s  0xA
0x56ec  stelem.ref
0x56ed  dup
0x56ee  ldc.i4.s 0xA
0x56f0  ldarg.s  0xB
0x56f2  stelem.ref
0x56f3  dup
0x56f4  ldc.i4.s 0xB
0x56f6  ldarg.s  0xC
0x56f8  box      [mscorlib]System.Guid
0x56fd  stelem.ref
0x56fe  dup
0x56ff  ldc.i4.s 0xC
0x5701  ldarg.s  0xD
0x5703  box      [mscorlib]System.Guid
0x5708  stelem.ref
0x5709  dup
0x570a  ldc.i4.s 0xD
0x570c  ldarg.s  0xE
0x570e  box      [mscorlib]System.Guid
0x5713  stelem.ref
0x5714  dup
0x5715  ldc.i4.s 0xE
0x5717  ldarg.s  0xF
0x5719  box      [mscorlib]System.Boolean
0x571e  stelem.ref
0x571f  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x5724  ret
```
