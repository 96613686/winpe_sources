# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointFinish_0

- ea: `0xdaf0`
- end: `0xdb33`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointFinish_0`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xdad0`

## pseudocode

```c

```

## disassembly

```asm
0xdaf0  ldarg.0
0xdaf1  ldc.i4.s 0xC
0xdaf3  ldc.i4.6
0xdaf4  newarr   [mscorlib]System.Object
0xdaf9  dup
0xdafa  ldc.i4.0
0xdafb  ldarg.1
0xdafc  box      [mscorlib]System.Guid
0xdb01  stelem.ref
0xdb02  dup
0xdb03  ldc.i4.1
0xdb04  ldarg.2
0xdb05  box      [mscorlib]System.DateTime
0xdb0a  stelem.ref
0xdb0b  dup
0xdb0c  ldc.i4.2
0xdb0d  ldarg.3
0xdb0e  box      [mscorlib]System.Int64
0xdb13  stelem.ref
0xdb14  dup
0xdb15  ldc.i4.3
0xdb16  ldarg.s  4
0xdb18  box      [mscorlib]System.Guid
0xdb1d  stelem.ref
0xdb1e  dup
0xdb1f  ldc.i4.4
0xdb20  ldarg.s  5
0xdb22  box      [mscorlib]System.Guid
0xdb27  stelem.ref
0xdb28  dup
0xdb29  ldc.i4.5
0xdb2a  ldarg.s  6
0xdb2c  stelem.ref
0xdb2d  call     T0x2B000026
0xdb32  ret
```
