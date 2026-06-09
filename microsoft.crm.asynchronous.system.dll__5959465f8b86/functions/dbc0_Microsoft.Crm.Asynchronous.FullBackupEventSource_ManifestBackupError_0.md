# Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupError_0

- ea: `0xdbc0`
- end: `0xdbf9`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupError_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xdba0`

## pseudocode

```c

```

## disassembly

```asm
0xdbc0  ldarg.0
0xdbc1  ldc.i4.s 0x10
0xdbc3  ldc.i4.5
0xdbc4  newarr   [mscorlib]System.Object
0xdbc9  dup
0xdbca  ldc.i4.0
0xdbcb  ldarg.1
0xdbcc  box      [mscorlib]System.Guid
0xdbd1  stelem.ref
0xdbd2  dup
0xdbd3  ldc.i4.1
0xdbd4  ldarg.2
0xdbd5  box      [mscorlib]System.DateTime
0xdbda  stelem.ref
0xdbdb  dup
0xdbdc  ldc.i4.2
0xdbdd  ldarg.3
0xdbde  box      [mscorlib]System.Int64
0xdbe3  stelem.ref
0xdbe4  dup
0xdbe5  ldc.i4.3
0xdbe6  ldarg.s  4
0xdbe8  box      [mscorlib]System.Guid
0xdbed  stelem.ref
0xdbee  dup
0xdbef  ldc.i4.4
0xdbf0  ldarg.s  5
0xdbf2  stelem.ref
0xdbf3  call     T0x2B000026
0xdbf8  ret
```
