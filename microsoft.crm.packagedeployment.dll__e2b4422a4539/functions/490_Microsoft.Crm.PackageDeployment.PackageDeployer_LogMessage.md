# Microsoft.Crm.PackageDeployment.PackageDeployer::LogMessage

- ea: `0x490`
- end: `0x4a2`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployer::LogMessage`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x250`

## callees

- `0x7d0`

## pseudocode

```c

```

## disassembly

```asm
0x490  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase> Microsoft.Crm.PackageDeployment.PackageDeployer::_packageDeployerWrapperInstance
0x495  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase>::get_Value()
0x49a  ldarg.0
0x49b  ldarg.1
0x49c  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogMessage(valuetype [System]System.Diagnostics.TraceLevel level, string message)
0x4a1  ret
```
