# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_TimedOut

- ea: `0xca0`
- end: `0xcb8`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_TimedOut`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xbf0`
- `0x1c80`

## callees

- `0xb70`
- `0xc80`
- `0xca0`

## pseudocode

```c

```

## disassembly

```asm
0xca0  ldarg.0
0xca1  call     instance class [mscorlib]System.Exception Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportResult::get_Exception()
0xca6  isinst   Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException
0xcab  stloc.0
0xcac  ldloc.0
0xcad  brfalse.s loc_CB6
0xcaf  ldloc.0
0xcb0  callvirt instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::get_TimedOut()
0xcb5  ret
0xcb6  ldc.i4.0
0xcb7  ret
```
