# CmsRpcClt_CreateProcessInContainer

- ea: `0x18000df74`
- end: `0x18000dfdf`
- name: `CmsRpcClt_CreateProcessInContainer`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002748`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dfd4`
- `RPCRT4!NdrClientCall3` at `0x18000dfd4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateProcessInContainer(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x27u, 0, a1, a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x18000df74  mov     r11, rsp
0x18000df77  sub     rsp, 68h
0x18000df7b  mov     rax, [rsp+68h+arg_40]
0x18000df83  mov     [r11-10h], rax
0x18000df87  mov     rax, [rsp+68h+arg_38]
0x18000df8f  mov     [r11-18h], rax
0x18000df93  mov     rax, [rsp+68h+arg_30]
0x18000df9b  mov     [r11-20h], rax
0x18000df9f  mov     rax, [rsp+68h+arg_28]
0x18000dfa7  mov     [r11-28h], rax
0x18000dfab  mov     rax, [rsp+68h+arg_20]
0x18000dfb3  mov     [r11-30h], rax
0x18000dfb7  mov     [r11-38h], r9
0x18000dfbb  mov     r9, rcx
0x18000dfbe  mov     [r11-40h], r8d
0x18000dfc2  lea     rcx, pProxyInfo; pProxyInfo
0x18000dfc9  xor     r8d, r8d; pReturnValue
0x18000dfcc  mov     [r11-48h], rdx
0x18000dfd0  lea     edx, [r8+27h]; nProcNum
0x18000dfd4  call    cs:__imp_NdrClientCall3
0x18000dfda  add     rsp, 68h
0x18000dfde  retn
```
