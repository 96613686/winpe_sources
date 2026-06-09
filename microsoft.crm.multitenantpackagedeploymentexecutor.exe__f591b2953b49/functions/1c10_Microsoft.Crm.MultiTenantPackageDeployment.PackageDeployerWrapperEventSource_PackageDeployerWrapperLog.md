# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog

- ea: `0x1c10`
- end: `0x1c39`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xf60`
- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0x1c10  ldarg.0
0x1c11  ldc.i4.1
0x1c12  ldc.i4.4
0x1c13  newarr   [mscorlib]System.Object
0x1c18  dup
0x1c19  ldc.i4.0
0x1c1a  ldarg.1
0x1c1b  box      [mscorlib]System.Guid
0x1c20  stelem.ref
0x1c21  dup
0x1c22  ldc.i4.1
0x1c23  ldarg.2
0x1c24  stelem.ref
0x1c25  dup
0x1c26  ldc.i4.2
0x1c27  ldarg.3
0x1c28  stelem.ref
0x1c29  dup
0x1c2a  ldc.i4.3
0x1c2b  ldarg.s  4
0x1c2d  box      [mscorlib]System.Boolean
0x1c32  stelem.ref
0x1c33  call     T0x2B000005
0x1c38  ret
```
