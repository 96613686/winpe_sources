# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::Dispose

- ea: `0x1230`
- end: `0x1244`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::Dispose`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x370`

## callees

- `0xb50`
- `0x1270`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldarg.0
0x1231  callvirt instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::DisposePackageDeployerWrapper()
0x1236  ldarg.0
0x1237  ldc.i4.1
0x1238  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::Dispose(bool disposing)
0x123d  ldarg.0
0x123e  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x1243  ret
```
