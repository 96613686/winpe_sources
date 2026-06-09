# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointError_0

- ea: `0xda90`
- end: `0xdac9`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointError_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xda70`

## pseudocode

```c

```

## disassembly

```asm
0xda90  ldarg.0
0xda91  ldc.i4.s 0xD
0xda93  ldc.i4.5
0xda94  newarr   [mscorlib]System.Object
0xda99  dup
0xda9a  ldc.i4.0
0xda9b  ldarg.1
0xda9c  box      [mscorlib]System.Guid
0xdaa1  stelem.ref
0xdaa2  dup
0xdaa3  ldc.i4.1
0xdaa4  ldarg.2
0xdaa5  box      [mscorlib]System.DateTime
0xdaaa  stelem.ref
0xdaab  dup
0xdaac  ldc.i4.2
0xdaad  ldarg.3
0xdaae  box      [mscorlib]System.Int64
0xdab3  stelem.ref
0xdab4  dup
0xdab5  ldc.i4.3
0xdab6  ldarg.s  4
0xdab8  box      [mscorlib]System.Guid
0xdabd  stelem.ref
0xdabe  dup
0xdabf  ldc.i4.4
0xdac0  ldarg.s  5
0xdac2  stelem.ref
0xdac3  call     T0x2B000026
0xdac8  ret
```
