# HnsRpc_CreateNamespace

- ea: `0x18000c280`
- end: `0x18000c2b8`
- name: `HnsRpc_CreateNamespace`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c2ad`
- `RPCRT4!NdrClientCall3` at `0x18000c2ad`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CreateNamespace(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000c280  mov     r11, rsp
0x18000c283  sub     rsp, 48h
0x18000c287  mov     rax, [rsp+48h+arg_20]
0x18000c28c  mov     [r11-10h], rax
0x18000c290  mov     [r11-18h], r9
0x18000c294  mov     r9, rcx
0x18000c297  mov     [r11-20h], r8
0x18000c29b  lea     rcx, pProxyInfo; pProxyInfo
0x18000c2a2  xor     r8d, r8d; pReturnValue
0x18000c2a5  mov     [r11-28h], rdx
0x18000c2a9  lea     edx, [r8+0Bh]; nProcNum
0x18000c2ad  call    cs:__imp_NdrClientCall3
0x18000c2b3  add     rsp, 48h
0x18000c2b7  retn
```
