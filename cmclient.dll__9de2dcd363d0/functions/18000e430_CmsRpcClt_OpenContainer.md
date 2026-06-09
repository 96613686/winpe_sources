# CmsRpcClt_OpenContainer

- ea: `0x18000e430`
- end: `0x18000e483`
- name: `CmsRpcClt_OpenContainer`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002970`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e478`
- `RPCRT4!NdrClientCall3` at `0x18000e478`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenContainer(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x18000e430  mov     r11, rsp
0x18000e433  sub     rsp, 58h
0x18000e437  mov     rax, [rsp+58h+arg_30]
0x18000e43f  mov     [r11-10h], rax
0x18000e443  mov     rax, [rsp+58h+arg_28]
0x18000e44b  mov     [r11-18h], rax
0x18000e44f  mov     rax, [rsp+58h+arg_20]
0x18000e457  mov     [r11-20h], rax
0x18000e45b  mov     [r11-28h], r9d
0x18000e45f  mov     r9, rcx
0x18000e462  mov     [r11-30h], r8d
0x18000e466  lea     rcx, pProxyInfo; pProxyInfo
0x18000e46d  xor     r8d, r8d; pReturnValue
0x18000e470  mov     [r11-38h], rdx
0x18000e474  lea     edx, [r8+2]; nProcNum
0x18000e478  call    cs:__imp_NdrClientCall3
0x18000e47e  add     rsp, 58h
0x18000e482  retn
```
