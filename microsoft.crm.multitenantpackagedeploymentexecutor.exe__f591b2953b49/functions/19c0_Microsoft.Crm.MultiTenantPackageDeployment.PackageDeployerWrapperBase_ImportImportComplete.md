# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ImportImportComplete

- ea: `0x19c0`
- end: `0x1a32`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ImportImportComplete`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xbb0`
- `0xf60`
- `0x1660`
- `0x1670`
- `0x19c0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.2
0x19c1  callvirt instance bool [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_isCompleted()
0x19c6  brfalse.s loc_19E5
0x19c8  ldarg.0
0x19c9  ldarg.0
0x19ca  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x19cf  ldstr    aPackagedeploye_9// "PackageDeployer succcessfully finished "...
0x19d4  call     string [mscorlib]System.String::Concat(string, string)
0x19d9  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x19de  ldarg.0
0x19df  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion()
0x19e4  ret
0x19e5  ldarg.0
0x19e6  ldarg.0
0x19e7  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x19ec  ldstr    aPackagedeploye_10// "PackageDeployer failed to import the so"...
0x19f1  call     string [mscorlib]System.String::Concat(string, string)
0x19f6  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x19fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a00  ldarg.0
0x1a01  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1a06  ldstr    aImportFailed0// "Import failed: {0}"
0x1a0b  call     string [mscorlib]System.String::Concat(string, string)
0x1a10  ldc.i4.1
0x1a11  newarr   [mscorlib]System.Object
0x1a16  dup
0x1a17  ldc.i4.0
0x1a18  ldarg.2
0x1a19  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_StatusMessage()
0x1a1e  stelem.ref
0x1a1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a24  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerImportException::.ctor(string message)
0x1a29  stloc.0
0x1a2a  ldarg.0
0x1a2b  ldloc.0
0x1a2c  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x1a31  ret
```
