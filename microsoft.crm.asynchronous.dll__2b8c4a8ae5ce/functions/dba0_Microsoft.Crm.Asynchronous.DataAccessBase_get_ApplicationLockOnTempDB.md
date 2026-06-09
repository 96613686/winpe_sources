# Microsoft.Crm.Asynchronous.DataAccessBase::get_ApplicationLockOnTempDB

- ea: `0xdba0`
- end: `0xdbb1`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::get_ApplicationLockOnTempDB`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd8e0`

## string_xrefs

- `0xdba5`: `ApplicationLockOnTempDB`

## pseudocode

```c

```

## disassembly

```asm
0xdba0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xdba5  ldstr    aApplicationloc// "ApplicationLockOnTempDB"
0xdbaa  ldc.i4.1
0xdbab  callvirt T0x2B00001C
0xdbb0  ret
```
