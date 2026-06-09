# Microsoft.Crm.Unzip.Common.EndpointUrlHelper::Retrieve

- ea: `0xb0`
- end: `0xc8`
- name: `Microsoft.Crm.Unzip.Common.EndpointUrlHelper::Retrieve`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1b0`

## callees

- `0xb0`
- `0xd0`

## pseudocode

```c

```

## disassembly

```asm
0xb0  ldnull
0xb1  stloc.0
0xb2  ldloca.s 0
0xb4  call     bool Microsoft.Crm.Unzip.Common.EndpointUrlHelper::TryRetrieve([out] class [System]System.Uri& endpointUri)
0xb9  brtrue.s loc_C6
0xbb  ldstr    aInvalidServerN// "Invalid server name for Unzip proxy."
0xc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xc5  throw
0xc6  ldloc.0
0xc7  ret
```
