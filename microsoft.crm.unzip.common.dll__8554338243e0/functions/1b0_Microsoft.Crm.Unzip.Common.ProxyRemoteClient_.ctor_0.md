# Microsoft.Crm.Unzip.Common.ProxyRemoteClient::.ctor_0

- ea: `0x1b0`
- end: `0x1bc`
- name: `Microsoft.Crm.Unzip.Common.ProxyRemoteClient::.ctor_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xb0`
- `0x120`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.0
0x1b1  call     class [System]System.Uri Microsoft.Crm.Unzip.Common.EndpointUrlHelper::Retrieve()
0x1b6  call     instance void Microsoft.Crm.Unzip.Common.ProxyRemoteClient::.ctor(class [System]System.Uri proxyUri)
0x1bb  ret
```
