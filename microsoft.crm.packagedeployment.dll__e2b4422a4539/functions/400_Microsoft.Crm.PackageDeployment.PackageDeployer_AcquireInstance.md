# Microsoft.Crm.PackageDeployment.PackageDeployer::AcquireInstance

- ea: `0x400`
- end: `0x445`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployer::AcquireInstance`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x370`

## callees

- `0x400`
- `0x5a0`

## pseudocode

```c

```

## disassembly

```asm
0x400  ldsfld   class [mscorlib]System.Threading.Mutex Microsoft.Crm.PackageDeployment.PackageDeployer::_instanceMutex
0x405  ldc.i4.0
0x406  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32)
0x40b  brtrue.s loc_418
0x40d  ldstr    aPackagedeploye_0// "PackageDeployer instance is being used"
0x412  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x417  throw
0x418  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x41d  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x422  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x427  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x42c  ldstr    a0// "{0}"
0x431  ldc.i4.1
0x432  newarr   [mscorlib]System.Object
0x437  dup
0x438  ldc.i4.0
0x439  ldstr    aPackagedeploye_1// "PackageDeployer: Acquired PackageDeploy"...
0x43e  stelem.ref
0x43f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x444  ret
```
