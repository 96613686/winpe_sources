# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::.ctor

- ea: `0x620`
- end: `0x6ae`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::.ctor`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x12a0`
- `0x1310`

## callees

- `0x590`
- `0x5a0`
- `0x5b0`
- `0xd50`

## pseudocode

```c

```

## disassembly

```asm
0x620  ldarg.0
0x621  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::GetJobTimeout()
0x626  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobTimeout
0x62b  ldarg.0
0x62c  ldc.i4.1
0x62d  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x632  stfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_completionEvent
0x637  ldarg.0
0x638  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0x63d  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobLog
0x642  ldarg.0
0x643  ldstr    aPackagedeploye_3// "PackageDeployerWrapper: "
0x648  stfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x64d  ldarg.0
0x64e  ldc.i4.1
0x64f  stfld    bool Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_selectDefaultPackage
0x654  ldarg.0
0x655  call     instance void [mscorlib]System.Object::.ctor()
0x65a  ldarg.1
0x65b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::OrganizationId
0x660  ldstr    aArgumentsOrgan// "arguments.OrganizationId"
0x665  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x66a  ldarg.1
0x66b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::UserId
0x670  ldstr    aArgumentsUseri// "arguments.UserId"
0x675  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x67a  ldarg.1
0x67b  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageLocation
0x680  ldstr    aArgumentsPacka// "arguments.PackageLocation"
0x685  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x68a  ldarg.1
0x68b  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x690  ldstr    aArgumentsPacka_0// "arguments.PackageName"
0x695  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x69a  ldarg.0
0x69b  ldarg.0
0x69c  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x6a1  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::set_TraceCategory(valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory value)
0x6a6  ldarg.0
0x6a7  ldarg.1
0x6a8  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::set_Arguments(class Microsoft.Crm.PackageDeployment.PackageDeployerArguments value)
0x6ad  ret
```
