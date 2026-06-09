# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ImportImportComplete

- ea: `0x11b0`
- end: `0x1222`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ImportImportComplete`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x300`
- `0x7f0`
- `0xe60`
- `0xe70`
- `0x11b0`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.2
0x11b1  callvirt instance bool [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_isCompleted()
0x11b6  brfalse.s loc_11D5
0x11b8  ldarg.0
0x11b9  ldarg.0
0x11ba  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x11bf  ldstr    aPackagedeploye_13// "PackageDeployer succcessfully finished "...
0x11c4  call     string [mscorlib]System.String::Concat(string, string)
0x11c9  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x11ce  ldarg.0
0x11cf  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion()
0x11d4  ret
0x11d5  ldarg.0
0x11d6  ldarg.0
0x11d7  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x11dc  ldstr    aPackagedeploye_14// "PackageDeployer failed to import the so"...
0x11e1  call     string [mscorlib]System.String::Concat(string, string)
0x11e6  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x11eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11f0  ldarg.0
0x11f1  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x11f6  ldstr    aImportFailed0// "Import failed: {0}"
0x11fb  call     string [mscorlib]System.String::Concat(string, string)
0x1200  ldc.i4.1
0x1201  newarr   [mscorlib]System.Object
0x1206  dup
0x1207  ldc.i4.0
0x1208  ldarg.2
0x1209  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.ImportProgressStatus::get_StatusMessage()
0x120e  stelem.ref
0x120f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1214  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerImportException::.ctor(string message)
0x1219  stloc.0
0x121a  ldarg.0
0x121b  ldloc.0
0x121c  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion(class [mscorlib]System.Exception ex)
0x1221  ret
```
