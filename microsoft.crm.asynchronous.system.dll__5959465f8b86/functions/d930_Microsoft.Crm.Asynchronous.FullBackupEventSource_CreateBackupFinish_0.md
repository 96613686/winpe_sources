# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupFinish_0

- ea: `0xd930`
- end: `0xd972`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateBackupFinish_0`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd910`

## pseudocode

```c

```

## disassembly

```asm
0xd930  ldarg.0
0xd931  ldc.i4.8
0xd932  ldc.i4.6
0xd933  newarr   [mscorlib]System.Object
0xd938  dup
0xd939  ldc.i4.0
0xd93a  ldarg.1
0xd93b  box      [mscorlib]System.Guid
0xd940  stelem.ref
0xd941  dup
0xd942  ldc.i4.1
0xd943  ldarg.2
0xd944  box      [mscorlib]System.DateTime
0xd949  stelem.ref
0xd94a  dup
0xd94b  ldc.i4.2
0xd94c  ldarg.3
0xd94d  box      [mscorlib]System.Int64
0xd952  stelem.ref
0xd953  dup
0xd954  ldc.i4.3
0xd955  ldarg.s  4
0xd957  box      [mscorlib]System.Guid
0xd95c  stelem.ref
0xd95d  dup
0xd95e  ldc.i4.4
0xd95f  ldarg.s  5
0xd961  stelem.ref
0xd962  dup
0xd963  ldc.i4.5
0xd964  ldarg.s  6
0xd966  box      [mscorlib]System.Int64
0xd96b  stelem.ref
0xd96c  call     T0x2B000026
0xd971  ret
```
