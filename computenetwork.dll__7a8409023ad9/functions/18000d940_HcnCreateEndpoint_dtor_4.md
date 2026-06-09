# HcnCreateEndpoint$dtor$4

- ea: `0x18000d940`
- end: `0x18000d94c`
- name: `HcnCreateEndpoint$dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004180`

## pseudocode

```c
__int64 __fastcall HcnCreateEndpoint_dtor_4(__int64 a1, __int64 a2)
{
  return std::shared_ptr<Rpc::RpcClient>::~shared_ptr<Rpc::RpcClient>(a2 + 88);
}

```

## disassembly

```asm
0x18000d940  lea     rcx, [rdx+58h]
0x18000d947  jmp     ??1?$shared_ptr@VRpcClient@Rpc@@@std@@QEAA@XZ; std::shared_ptr<Rpc::RpcClient>::~shared_ptr<Rpc::RpcClient>(void)
```
