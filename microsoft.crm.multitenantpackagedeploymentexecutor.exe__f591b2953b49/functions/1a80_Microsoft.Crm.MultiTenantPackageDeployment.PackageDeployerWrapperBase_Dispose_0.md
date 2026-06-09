# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::Dispose_0

- ea: `0x1a80`
- end: `0x1a9e`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::Dispose_0`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1a40`
- `0x1a60`

## callees

- `0x1a80`

## pseudocode

```c

```

## disassembly

```asm
0x1a80  ldarg.0
0x1a81  ldfld    bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_disposed
0x1a86  brtrue.s loc_1A9D
0x1a88  ldarg.1
0x1a89  brfalse.s loc_1A96
0x1a8b  ldarg.0
0x1a8c  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_completionEvent
0x1a91  callvirt instance void [mscorlib]System.Threading.WaitHandle::Dispose()
0x1a96  ldarg.0
0x1a97  ldc.i4.1
0x1a98  stfld    bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_disposed
0x1a9d  ret
```
