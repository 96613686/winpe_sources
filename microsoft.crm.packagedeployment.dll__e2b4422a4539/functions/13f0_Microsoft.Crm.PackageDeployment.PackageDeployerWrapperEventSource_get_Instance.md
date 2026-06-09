# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::get_Instance

- ea: `0x13f0`
- end: `0x13fb`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::get_Instance`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7f0`
- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x13f0  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource> Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource::lazyInstance
0x13f5  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.PackageDeployment.PackageDeployerWrapperEventSource>::get_Value()
0x13fa  ret
```
