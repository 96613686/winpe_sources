# HnsRpc_CreateNetwork

- ea: `0x18000c2c0`
- end: `0x18000c2f8`
- name: `HnsRpc_CreateNetwork`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c2ed`
- `RPCRT4!NdrClientCall3` at `0x18000c2ed`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CreateNetwork(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000c2c0  mov     r11, rsp
0x18000c2c3  sub     rsp, 48h
0x18000c2c7  mov     rax, [rsp+48h+arg_20]
0x18000c2cc  mov     [r11-10h], rax
0x18000c2d0  mov     [r11-18h], r9
0x18000c2d4  mov     r9, rcx
0x18000c2d7  mov     [r11-20h], r8
0x18000c2db  lea     rcx, pProxyInfo; pProxyInfo
0x18000c2e2  xor     r8d, r8d; pReturnValue
0x18000c2e5  mov     [r11-28h], rdx
0x18000c2e9  lea     edx, [r8+1]; nProcNum
0x18000c2ed  call    cs:__imp_NdrClientCall3
0x18000c2f3  add     rsp, 48h
0x18000c2f7  retn
```
