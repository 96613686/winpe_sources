# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::GetJobTimeout

- ea: `0xd50`
- end: `0xd7a`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::GetJobTimeout`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x620`

## callees

- `0xd50`

## pseudocode

```c

```

## disassembly

```asm
0xd50  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xd55  ldstr    aPackagedeploye_5// "PackageDeployerProcessTimeoutInMinutes"
0xd5a  ldc.i4.1
0xd5b  callvirt T0x2B000003
0xd60  stloc.0
0xd61  ldloc.0
0xd62  brtrue.s loc_D67
0xd64  ldc.i4.s 0x78
0xd66  stloc.0
0xd67  ldloc.0
0xd68  ldc.i4.5
0xd69  bgt.s    loc_D6E
0xd6b  ldloc.0
0xd6c  br.s     loc_D71
0xd6e  ldloc.0
0xd6f  ldc.i4.5
0xd70  sub
0xd71  stloc.0
0xd72  ldloc.0
0xd73  conv.r8
0xd74  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xd79  ret
```
