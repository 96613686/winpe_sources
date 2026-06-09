# HnsRpc_OpenLoadBalancer

- ea: `0x18000c7b0`
- end: `0x18000c7df`
- name: `HnsRpc_OpenLoadBalancer`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c7d4`
- `RPCRT4!NdrClientCall3` at `0x18000c7d4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenLoadBalancer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Au, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c7b0  sub     rsp, 48h
0x18000c7b4  mov     [rsp+48h+var_18], r9
0x18000c7b9  mov     r9, rcx
0x18000c7bc  mov     [rsp+48h+var_20], r8
0x18000c7c1  lea     rcx, pProxyInfo; pProxyInfo
0x18000c7c8  xor     r8d, r8d; pReturnValue
0x18000c7cb  mov     [rsp+48h+var_28], rdx
0x18000c7d0  lea     edx, [r8+1Ah]; nProcNum
0x18000c7d4  call    cs:__imp_NdrClientCall3
0x18000c7da  add     rsp, 48h
0x18000c7de  retn
```
