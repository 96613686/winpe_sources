# Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationSuccess

- ea: `0x5630`
- end: `0x5698`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListenerEventSource::OperationSuccess`
- size: `104`
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
0x5630  ldarg.0
0x5631  ldc.i4.1
0x5632  ldc.i4.s 0xB
0x5634  newarr   [mscorlib]System.Object
0x5639  dup
0x563a  ldc.i4.0
0x563b  ldarg.1
0x563c  box      [mscorlib]System.Guid
0x5641  stelem.ref
0x5642  dup
0x5643  ldc.i4.1
0x5644  ldarg.2
0x5645  stelem.ref
0x5646  dup
0x5647  ldc.i4.2
0x5648  ldarg.3
0x5649  stelem.ref
0x564a  dup
0x564b  ldc.i4.3
0x564c  ldarg.s  4
0x564e  stelem.ref
0x564f  dup
0x5650  ldc.i4.4
0x5651  ldarg.s  5
0x5653  box      [mscorlib]System.Guid
0x5658  stelem.ref
0x5659  dup
0x565a  ldc.i4.5
0x565b  ldarg.s  6
0x565d  stelem.ref
0x565e  dup
0x565f  ldc.i4.6
0x5660  ldarg.s  7
0x5662  box      [mscorlib]System.Int64
0x5667  stelem.ref
0x5668  dup
0x5669  ldc.i4.7
0x566a  ldarg.s  8
0x566c  box      [mscorlib]System.Guid
0x5671  stelem.ref
0x5672  dup
0x5673  ldc.i4.8
0x5674  ldarg.s  9
0x5676  box      [mscorlib]System.Guid
0x567b  stelem.ref
0x567c  dup
0x567d  ldc.i4.s 9
0x567f  ldarg.s  0xA
0x5681  box      [mscorlib]System.Guid
0x5686  stelem.ref
0x5687  dup
0x5688  ldc.i4.s 0xA
0x568a  ldarg.s  0xB
0x568c  box      [mscorlib]System.Boolean
0x5691  stelem.ref
0x5692  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x5697  ret
```
