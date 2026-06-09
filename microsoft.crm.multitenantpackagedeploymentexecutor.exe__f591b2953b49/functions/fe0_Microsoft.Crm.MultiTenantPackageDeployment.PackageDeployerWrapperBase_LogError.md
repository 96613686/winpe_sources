# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError

- ea: `0xfe0`
- end: `0x1065`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError`
- size: `133`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe90`
- `0xf40`
- `0x1560`
- `0x1670`
- `0x16c0`
- `0x1700`
- `0x1890`

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
0xfe0  call     class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::get_Instance()
0xfe5  ldarg.0
0xfe6  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xfeb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::OrganizationId
0xff0  ldarg.0
0xff1  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0xff6  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0xffb  ldarg.1
0xffc  ldc.i4.1
0xffd  callvirt instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog(valuetype [mscorlib]System.Guid organizationId, string packageName, string log, bool error)
0x1002  ldnull
0x1003  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1008  ldarg.0
0x1009  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x100e  ldstr    a0// "{0}"
0x1013  ldc.i4.1
0x1014  newarr   [mscorlib]System.Object
0x1019  dup
0x101a  ldc.i4.0
0x101b  ldarg.1
0x101c  stelem.ref
0x101d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1022  ldarg.0
0x1023  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobLog
0x1028  ldc.i4.4
0x1029  newarr   [mscorlib]System.Object
0x102e  dup
0x102f  ldc.i4.0
0x1030  ldstr    asc_3CF8// "["
0x1035  stelem.ref
0x1036  dup
0x1037  ldc.i4.1
0x1038  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x103d  box      [mscorlib]System.DateTime
0x1042  stelem.ref
0x1043  dup
0x1044  ldc.i4.2
0x1045  ldstr    asc_3CFC// "]: "
0x104a  stelem.ref
0x104b  dup
0x104c  ldc.i4.3
0x104d  ldarg.1
0x104e  stelem.ref
0x104f  call     string [mscorlib]System.String::Concat(object[])
0x1054  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::Enqueue(var<u1>)
0x1059  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x105e  ldarg.1
0x105f  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x1064  ret
```
