# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::GetJobTimeout

- ea: `0x1530`
- end: `0x155a`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::GetJobTimeout`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd90`

## callees

- `0x1530`

## pseudocode

```c

```

## disassembly

```asm
0x1530  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x1535  ldstr    aPackagedeploye_1// "PackageDeployerProcessTimeoutInMinutes"
0x153a  ldc.i4.1
0x153b  callvirt T0x2B000004
0x1540  stloc.0
0x1541  ldloc.0
0x1542  brtrue.s loc_1547
0x1544  ldc.i4.s 0x78
0x1546  stloc.0
0x1547  ldloc.0
0x1548  ldc.i4.5
0x1549  bgt.s    loc_154E
0x154b  ldloc.0
0x154c  br.s     loc_1551
0x154e  ldloc.0
0x154f  ldc.i4.5
0x1550  sub
0x1551  stloc.0
0x1552  ldloc.0
0x1553  conv.r8
0x1554  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1559  ret
```
