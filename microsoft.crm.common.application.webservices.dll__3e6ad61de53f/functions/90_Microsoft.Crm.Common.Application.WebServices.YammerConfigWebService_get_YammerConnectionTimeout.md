# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::get_YammerConnectionTimeout

- ea: `0x90`
- end: `0xa9`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::get_YammerConnectionTimeout`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180`
- `0x520`

## pseudocode

```c

```

## disassembly

```asm
0x90  ldc.i4.0
0x91  ldc.i4.0
0x92  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x97  ldstr    aYammerconnecti// "YammerConnectionTimeoutInSeconds"
0x9c  ldc.i4.s 0x3C
0x9e  callvirt T0x2B000001
0xa3  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa8  ret
```
