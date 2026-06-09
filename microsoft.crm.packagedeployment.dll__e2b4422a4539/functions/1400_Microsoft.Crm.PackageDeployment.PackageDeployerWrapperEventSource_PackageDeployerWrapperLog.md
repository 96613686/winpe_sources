# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog

- ea: `0x1400`
- end: `0x1429`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7f0`
- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x1400  ldarg.0
0x1401  ldc.i4.1
0x1402  ldc.i4.4
0x1403  newarr   [mscorlib]System.Object
0x1408  dup
0x1409  ldc.i4.0
0x140a  ldarg.1
0x140b  box      [mscorlib]System.Guid
0x1410  stelem.ref
0x1411  dup
0x1412  ldc.i4.1
0x1413  ldarg.2
0x1414  stelem.ref
0x1415  dup
0x1416  ldc.i4.2
0x1417  ldarg.3
0x1418  stelem.ref
0x1419  dup
0x141a  ldc.i4.3
0x141b  ldarg.s  4
0x141d  box      [mscorlib]System.Boolean
0x1422  stelem.ref
0x1423  call     T0x2B000004
0x1428  ret
```
