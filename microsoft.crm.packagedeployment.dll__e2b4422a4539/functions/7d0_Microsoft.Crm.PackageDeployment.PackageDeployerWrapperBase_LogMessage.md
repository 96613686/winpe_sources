# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogMessage

- ea: `0x7d0`
- end: `0x7e4`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogMessage`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x490`
- `0x1320`

## callees

- `0x7d0`
- `0x7f0`
- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldarg.1
0x7d1  ldc.i4.1
0x7d2  bne.un.s loc_7DC
0x7d4  ldarg.0
0x7d5  ldarg.2
0x7d6  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x7db  ret
0x7dc  ldarg.0
0x7dd  ldarg.2
0x7de  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x7e3  ret
```
