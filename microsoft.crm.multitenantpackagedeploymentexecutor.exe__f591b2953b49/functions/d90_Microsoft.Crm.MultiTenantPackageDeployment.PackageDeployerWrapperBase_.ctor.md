# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::.ctor

- ea: `0xd90`
- end: `0xe1e`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::.ctor`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1ab0`
- `0x1b20`

## callees

- `0xd00`
- `0xd10`
- `0xd20`
- `0x1530`

## pseudocode

```c

```

## disassembly

```asm
0xd90  ldarg.0
0xd91  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::GetJobTimeout()
0xd96  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobTimeout
0xd9b  ldarg.0
0xd9c  ldc.i4.1
0xd9d  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0xda2  stfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_completionEvent
0xda7  ldarg.0
0xda8  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0xdad  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobLog
0xdb2  ldarg.0
0xdb3  ldstr    aPackagedeploye// "PackageDeployerWrapper: "
0xdb8  stfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xdbd  ldarg.0
0xdbe  ldc.i4.1
0xdbf  stfld    bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_selectDefaultPackage
0xdc4  ldarg.0
0xdc5  call     instance void [mscorlib]System.Object::.ctor()
0xdca  ldarg.1
0xdcb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::OrganizationId
0xdd0  ldstr    aArgumentsOrgan// "arguments.OrganizationId"
0xdd5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xdda  ldarg.1
0xddb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::UserId
0xde0  ldstr    aArgumentsUseri// "arguments.UserId"
0xde5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xdea  ldarg.1
0xdeb  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0xdf0  ldstr    aArgumentsPacka// "arguments.PackageLocation"
0xdf5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xdfa  ldarg.1
0xdfb  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0xe00  ldstr    aArgumentsPacka_0// "arguments.PackageName"
0xe05  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xe0a  ldarg.0
0xe0b  ldarg.0
0xe0c  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0xe11  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::set_TraceCategory(valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory value)
0xe16  ldarg.0
0xe17  ldarg.1
0xe18  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::set_Arguments(class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments value)
0xe1d  ret
```
