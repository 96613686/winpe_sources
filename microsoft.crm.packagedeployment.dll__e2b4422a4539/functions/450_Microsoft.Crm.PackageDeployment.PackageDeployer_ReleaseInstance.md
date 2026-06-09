# Microsoft.Crm.PackageDeployment.PackageDeployer::ReleaseInstance

- ea: `0x450`
- end: `0x487`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployer::ReleaseInstance`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x370`

## callees

- `0x5a0`

## pseudocode

```c

```

## disassembly

```asm
0x450  ldsfld   class [mscorlib]System.Threading.Mutex Microsoft.Crm.PackageDeployment.PackageDeployer::_instanceMutex
0x455  callvirt instance void [mscorlib]System.Threading.Mutex::ReleaseMutex()
0x45a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x45f  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x464  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x469  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x46e  ldstr    a0// "{0}"
0x473  ldc.i4.1
0x474  newarr   [mscorlib]System.Object
0x479  dup
0x47a  ldc.i4.0
0x47b  ldstr    aPackagedeploye_2// "PackageDeployer: Released PackageDeploy"...
0x480  stelem.ref
0x481  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x486  ret
```
