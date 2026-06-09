# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError

- ea: `0x870`
- end: `0x8f5`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError`
- size: `133`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x720`
- `0x7d0`
- `0xd80`
- `0xe70`
- `0xec0`
- `0xf00`
- `0x1080`

## callees

- `0x580`
- `0x5a0`
- `0x13f0`
- `0x1400`

## pseudocode

```c

```

## disassembly

```asm
0x870  call     class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::get_Instance()
0x875  ldarg.0
0x876  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x87b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::OrganizationId
0x880  ldarg.0
0x881  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x886  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x88b  ldarg.1
0x88c  ldc.i4.1
0x88d  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog(valuetype [mscorlib]System.Guid organizationId, string packageName, string log, bool error)
0x892  ldnull
0x893  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x898  ldarg.0
0x899  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x89e  ldstr    a0// "{0}"
0x8a3  ldc.i4.1
0x8a4  newarr   [mscorlib]System.Object
0x8a9  dup
0x8aa  ldc.i4.0
0x8ab  ldarg.1
0x8ac  stelem.ref
0x8ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8b2  ldarg.0
0x8b3  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobLog
0x8b8  ldc.i4.4
0x8b9  newarr   [mscorlib]System.Object
0x8be  dup
0x8bf  ldc.i4.0
0x8c0  ldstr    asc_231A// "["
0x8c5  stelem.ref
0x8c6  dup
0x8c7  ldc.i4.1
0x8c8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x8cd  box      [mscorlib]System.DateTime
0x8d2  stelem.ref
0x8d3  dup
0x8d4  ldc.i4.2
0x8d5  ldstr    asc_231E// "]: "
0x8da  stelem.ref
0x8db  dup
0x8dc  ldc.i4.3
0x8dd  ldarg.1
0x8de  stelem.ref
0x8df  call     string [mscorlib]System.String::Concat(object[])
0x8e4  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::Enqueue(var<u1>)
0x8e9  call     class [mscorlib]System.IO.TextWriter [mscorlib]System.Console::get_Error()
0x8ee  ldarg.1
0x8ef  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x8f4  ret
```
