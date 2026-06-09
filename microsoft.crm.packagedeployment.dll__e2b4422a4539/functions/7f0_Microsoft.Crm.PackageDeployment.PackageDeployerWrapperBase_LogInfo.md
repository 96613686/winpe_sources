# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo

- ea: `0x7f0`
- end: `0x86f`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo`
- size: `127`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x7d0`
- `0xb60`
- `0xcd0`
- `0xd80`
- `0xdc0`
- `0xdf0`
- `0xe70`
- `0xf00`
- `0x11b0`

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
0x7f0  call     class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::get_Instance()
0x7f5  ldarg.0
0x7f6  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x7fb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::OrganizationId
0x800  ldarg.0
0x801  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x806  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerArguments::PackageName
0x80b  ldarg.1
0x80c  ldc.i4.0
0x80d  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::PackageDeployerWrapperLog(valuetype [mscorlib]System.Guid organizationId, string packageName, string log, bool error)
0x812  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x817  ldarg.0
0x818  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x81d  ldstr    a0// "{0}"
0x822  ldc.i4.1
0x823  newarr   [mscorlib]System.Object
0x828  dup
0x829  ldc.i4.0
0x82a  ldarg.1
0x82b  stelem.ref
0x82c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x831  ldarg.0
0x832  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobLog
0x837  ldc.i4.4
0x838  newarr   [mscorlib]System.Object
0x83d  dup
0x83e  ldc.i4.0
0x83f  ldstr    asc_231A// "["
0x844  stelem.ref
0x845  dup
0x846  ldc.i4.1
0x847  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x84c  box      [mscorlib]System.DateTime
0x851  stelem.ref
0x852  dup
0x853  ldc.i4.2
0x854  ldstr    asc_231E// "]: "
0x859  stelem.ref
0x85a  dup
0x85b  ldc.i4.3
0x85c  ldarg.1
0x85d  stelem.ref
0x85e  call     string [mscorlib]System.String::Concat(object[])
0x863  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::Enqueue(var<u1>)
0x868  ldarg.1
0x869  call     void [mscorlib]System.Console::WriteLine(string)
0x86e  ret
```
