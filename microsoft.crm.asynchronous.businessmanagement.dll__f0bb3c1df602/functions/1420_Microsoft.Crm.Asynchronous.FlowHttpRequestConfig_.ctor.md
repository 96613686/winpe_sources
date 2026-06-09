# Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::.ctor

- ea: `0x1420`
- end: `0x1450`
- name: `Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::.ctor`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1630`

## callees

- `0x13b0`
- `0x13d0`
- `0x13f0`
- `0x1410`

## pseudocode

```c

```

## disassembly

```asm
0x1420  ldarg.0
0x1421  call     instance void [mscorlib]System.Object::.ctor()
0x1426  ldarg.0
0x1427  ldc.i4.s 0xA
0x1429  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_ConnectionLimit(int32 value)
0x142e  ldarg.0
0x142f  ldc.i4   0x927C0
0x1434  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_ConnectionLeaseTimeoutInMilliSeconds(int32 value)
0x1439  ldarg.0
0x143a  ldc.i4   0x1D4C0
0x143f  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_MaxIdleTimeInMilliSeconds(int32 value)
0x1444  ldarg.0
0x1445  ldc.i4   0xEA60
0x144a  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_HttpRequestTimeoutInMilliSeconds(int32 value)
0x144f  ret
```
