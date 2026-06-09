# Microsoft.Crm.PackageDeployment.PackageDeployer::GetTraceCategory

- ea: `0x4b0`
- end: `0x4c0`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployer::GetTraceCategory`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x230`

## callees

- `0x5a0`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x4b5  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x4ba  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_TraceCategory()
0x4bf  ret
```
