# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DequeueLog

- ea: `0x1070`
- end: `0x10bb`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::DequeueLog`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe90`

## callees

- `0x1070`

## pseudocode

```c

```

## disassembly

```asm
0x1070  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1075  stloc.0
0x1076  ldnull
0x1077  stloc.1
0x1078  br.s     loc_1081
0x107a  ldloc.0
0x107b  ldloc.1
0x107c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1081  ldarg.0
0x1082  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobLog
0x1087  ldloca.s 1
0x1089  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::TryDequeue(var<u1>&)
0x108e  brtrue.s loc_107A
0x1090  ldarg.0
0x1091  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x1096  brfalse.s loc_10B4
0x1098  ldloc.0
0x1099  ldstr    aDetailedLogsFr// "Detailed logs from PDCore:"
0x109e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a3  ldloc.0
0x10a4  ldarg.0
0x10a5  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_import
0x10aa  callvirt instance string[] [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.BaseImportCustomizations::GetAllLogs()
0x10af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x10b4  ldloc.0
0x10b5  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x10ba  ret
```
