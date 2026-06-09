# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::get_Instance

- ea: `0x1c00`
- end: `0x1c0b`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::get_Instance`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xf60`
- `0xfe0`

## pseudocode

```c

```

## disassembly

```asm
0x1c00  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource> Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource::lazyInstance
0x1c05  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperEventSource>::get_Value()
0x1c0a  ret
```
