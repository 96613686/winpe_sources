# Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupFinish_0

- ea: `0xdc20`
- end: `0xdc59`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupFinish_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xdc00`

## pseudocode

```c

```

## disassembly

```asm
0xdc20  ldarg.0
0xdc21  ldc.i4.s 0xF
0xdc23  ldc.i4.5
0xdc24  newarr   [mscorlib]System.Object
0xdc29  dup
0xdc2a  ldc.i4.0
0xdc2b  ldarg.1
0xdc2c  box      [mscorlib]System.Guid
0xdc31  stelem.ref
0xdc32  dup
0xdc33  ldc.i4.1
0xdc34  ldarg.2
0xdc35  box      [mscorlib]System.DateTime
0xdc3a  stelem.ref
0xdc3b  dup
0xdc3c  ldc.i4.2
0xdc3d  ldarg.3
0xdc3e  box      [mscorlib]System.Int64
0xdc43  stelem.ref
0xdc44  dup
0xdc45  ldc.i4.3
0xdc46  ldarg.s  4
0xdc48  box      [mscorlib]System.Guid
0xdc4d  stelem.ref
0xdc4e  dup
0xdc4f  ldc.i4.4
0xdc50  ldarg.s  5
0xdc52  stelem.ref
0xdc53  call     T0x2B000026
0xdc58  ret
```
