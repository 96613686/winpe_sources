# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::WaitForCompletion

- ea: `0x15d0`
- end: `0x1657`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::WaitForCompletion`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe90`

## callees

- `0xb40`
- `0xb80`
- `0xf60`
- `0x15d0`

## string_xrefs

- `0x15d7`: `Waiting for PackageDeployer completion...`
- `0x1647`: `PackageDeployer operation completed.`

## pseudocode

```c

```

## disassembly

```asm
0x15d0  ldarg.0
0x15d1  ldarg.0
0x15d2  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x15d7  ldstr    aWaitingForPack// "Waiting for PackageDeployer completion."...
0x15dc  call     string [mscorlib]System.String::Concat(string, string)
0x15e1  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x15e6  ldarg.0
0x15e7  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_completionEvent
0x15ec  ldarg.1
0x15ed  stloc.0
0x15ee  ldloca.s 0
0x15f0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::get_HasValue()
0x15f5  brtrue.s loc_15FF
0x15f7  ldarg.0
0x15f8  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobTimeout
0x15fd  br.s     loc_1606
0x15ff  ldloca.s 0
0x1601  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::GetValueOrDefault()
0x1606  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan)
0x160b  brtrue.s loc_1640
0x160d  ldarg.0
0x160e  ldarg.0
0x160f  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1614  ldstr    aPackagedeploye_2// "PackageDeployer operation timed out."
0x1619  call     string [mscorlib]System.String::Concat(string, string)
0x161e  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x1623  ldarg.0
0x1624  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1629  ldstr    aImportOperatio// "Import operation timed out."
0x162e  call     string [mscorlib]System.String::Concat(string, string)
0x1633  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message)
0x1638  dup
0x1639  ldc.i4.1
0x163a  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::set_TimedOut(bool value)
0x163f  throw
0x1640  ldarg.0
0x1641  ldarg.0
0x1642  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1647  ldstr    aPackagedeploye_3// "PackageDeployer operation completed."
0x164c  call     string [mscorlib]System.String::Concat(string, string)
0x1651  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x1656  ret
```
