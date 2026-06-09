# HnsRpc_CreateSdnRoute

- ea: `0x18000c300`
- end: `0x18000c338`
- name: `HnsRpc_CreateSdnRoute`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c32d`
- `RPCRT4!NdrClientCall3` at `0x18000c32d`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CreateSdnRoute(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x20u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000c300  mov     r11, rsp
0x18000c303  sub     rsp, 48h
0x18000c307  mov     rax, [rsp+48h+arg_20]
0x18000c30c  mov     [r11-10h], rax
0x18000c310  mov     [r11-18h], r9
0x18000c314  mov     r9, rcx
0x18000c317  mov     [r11-20h], r8
0x18000c31b  lea     rcx, pProxyInfo; pProxyInfo
0x18000c322  xor     r8d, r8d; pReturnValue
0x18000c325  mov     [r11-28h], rdx
0x18000c329  lea     edx, [r8+20h]; nProcNum
0x18000c32d  call    cs:__imp_NdrClientCall3
0x18000c333  add     rsp, 48h
0x18000c337  retn
```
