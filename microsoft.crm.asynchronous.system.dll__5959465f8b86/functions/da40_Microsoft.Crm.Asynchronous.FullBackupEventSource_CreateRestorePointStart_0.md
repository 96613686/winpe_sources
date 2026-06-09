# Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointStart_0

- ea: `0xda40`
- end: `0xda6a`
- name: `Microsoft.Crm.Asynchronous.FullBackupEventSource::CreateRestorePointStart_0`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xda30`

## pseudocode

```c

```

## disassembly

```asm
0xda40  ldarg.0
0xda41  ldc.i4.s 0xB
0xda43  ldc.i4.3
0xda44  newarr   [mscorlib]System.Object
0xda49  dup
0xda4a  ldc.i4.0
0xda4b  ldarg.1
0xda4c  box      [mscorlib]System.Guid
0xda51  stelem.ref
0xda52  dup
0xda53  ldc.i4.1
0xda54  ldarg.2
0xda55  box      [mscorlib]System.DateTime
0xda5a  stelem.ref
0xda5b  dup
0xda5c  ldc.i4.2
0xda5d  ldarg.3
0xda5e  box      [mscorlib]System.Guid
0xda63  stelem.ref
0xda64  call     T0x2B000026
0xda69  ret
```
