# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupStart_0

- ea: `0xd8d0`
- end: `0xd903`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupStart_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd8b0`

## pseudocode

```c

```

## disassembly

```asm
0xd8d0  ldarg.0
0xd8d1  ldc.i4.7
0xd8d2  ldc.i4.5
0xd8d3  newarr   [mscorlib]System.Object
0xd8d8  dup
0xd8d9  ldc.i4.0
0xd8da  ldarg.1
0xd8db  box      [mscorlib]System.Guid
0xd8e0  stelem.ref
0xd8e1  dup
0xd8e2  ldc.i4.1
0xd8e3  ldarg.2
0xd8e4  box      [mscorlib]System.DateTime
0xd8e9  stelem.ref
0xd8ea  dup
0xd8eb  ldc.i4.2
0xd8ec  ldarg.3
0xd8ed  box      [mscorlib]System.Guid
0xd8f2  stelem.ref
0xd8f3  dup
0xd8f4  ldc.i4.3
0xd8f5  ldarg.s  4
0xd8f7  stelem.ref
0xd8f8  dup
0xd8f9  ldc.i4.4
0xd8fa  ldarg.s  5
0xd8fc  stelem.ref
0xd8fd  call     T0x2B000026
0xd902  ret
```
