# HnsRpc_CreateLoadBalancer

- ea: `0x18000c240`
- end: `0x18000c278`
- name: `HnsRpc_CreateLoadBalancer`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c26d`
- `RPCRT4!NdrClientCall3` at `0x18000c26d`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CreateLoadBalancer(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x19u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000c240  mov     r11, rsp
0x18000c243  sub     rsp, 48h
0x18000c247  mov     rax, [rsp+48h+arg_20]
0x18000c24c  mov     [r11-10h], rax
0x18000c250  mov     [r11-18h], r9
0x18000c254  mov     r9, rcx
0x18000c257  mov     [r11-20h], r8
0x18000c25b  lea     rcx, pProxyInfo; pProxyInfo
0x18000c262  xor     r8d, r8d; pReturnValue
0x18000c265  mov     [r11-28h], rdx
0x18000c269  lea     edx, [r8+19h]; nProcNum
0x18000c26d  call    cs:__imp_NdrClientCall3
0x18000c273  add     rsp, 48h
0x18000c277  retn
```
