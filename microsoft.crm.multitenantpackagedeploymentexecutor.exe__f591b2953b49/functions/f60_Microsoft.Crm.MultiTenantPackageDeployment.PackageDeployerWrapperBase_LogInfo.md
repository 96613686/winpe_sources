# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo

- ea: `0xf60`
- end: `0xfdf`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo`
- size: `127`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xf40`
- `0x1320`
- `0x14b0`
- `0x1560`
- `0x15a0`
- `0x15d0`
- `0x1670`
- `0x1700`
- `0x19c0`

## callees

- `0xcf0`
- `0xd10`
- `0x1c00`
- `0x1c10`

## pseudocode

```c

```

## disassembly

```asm
0xf60  call     class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::get_Instance()
0xf65  ldarg.0
0xf66  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xf6b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::OrganizationId
0xf70  ldarg.0
0xf71  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xf76  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0xf7b  ldarg.1
0xf7c  ldc.i4.0
0xf7d  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog(valuetype [mscorlib]System.Guid organizationId, string packageName, string log, bool error)
0xf82  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf87  ldarg.0
0xf88  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0xf8d  ldstr    a0// "{0}"
0xf92  ldc.i4.1
0xf93  newarr   [mscorlib]System.Object
0xf98  dup
0xf99  ldc.i4.0
0xf9a  ldarg.1
0xf9b  stelem.ref
0xf9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfa1  ldarg.0
0xfa2  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobLog
0xfa7  ldc.i4.4
0xfa8  newarr   [mscorlib]System.Object
0xfad  dup
0xfae  ldc.i4.0
0xfaf  ldstr    asc_3CF8// "["
0xfb4  stelem.ref
0xfb5  dup
0xfb6  ldc.i4.1
0xfb7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xfbc  box      [mscorlib]System.DateTime
0xfc1  stelem.ref
0xfc2  dup
0xfc3  ldc.i4.2
0xfc4  ldstr    asc_3CFC// "]: "
0xfc9  stelem.ref
0xfca  dup
0xfcb  ldc.i4.3
0xfcc  ldarg.1
0xfcd  stelem.ref
0xfce  call     string [mscorlib]System.String::Concat(object[])
0xfd3  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::Enqueue(var<u1>)
0xfd8  ldarg.1
0xfd9  call     void [mscorlib]System.Console::WriteLine(string)
0xfde  ret
```
