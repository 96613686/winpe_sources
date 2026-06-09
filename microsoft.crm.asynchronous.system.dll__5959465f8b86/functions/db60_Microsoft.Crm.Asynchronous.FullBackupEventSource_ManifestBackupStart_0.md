# Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupStart_0

- ea: `0xdb60`
- end: `0xdb9e`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::ManifestBackupStart_0`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xdb40`

## pseudocode

```c

```

## disassembly

```asm
0xdb60  ldarg.0
0xdb61  ldc.i4.s 0xE
0xdb63  ldc.i4.6
0xdb64  newarr   [mscorlib]System.Object
0xdb69  dup
0xdb6a  ldc.i4.0
0xdb6b  ldarg.1
0xdb6c  box      [mscorlib]System.Guid
0xdb71  stelem.ref
0xdb72  dup
0xdb73  ldc.i4.1
0xdb74  ldarg.2
0xdb75  box      [mscorlib]System.DateTime
0xdb7a  stelem.ref
0xdb7b  dup
0xdb7c  ldc.i4.2
0xdb7d  ldarg.3
0xdb7e  box      [mscorlib]System.Guid
0xdb83  stelem.ref
0xdb84  dup
0xdb85  ldc.i4.3
0xdb86  ldarg.s  4
0xdb88  stelem.ref
0xdb89  dup
0xdb8a  ldc.i4.4
0xdb8b  ldarg.s  5
0xdb8d  box      [mscorlib]System.DateTime
0xdb92  stelem.ref
0xdb93  dup
0xdb94  ldc.i4.5
0xdb95  ldarg.s  6
0xdb97  stelem.ref
0xdb98  call     T0x2B000026
0xdb9d  ret
```
