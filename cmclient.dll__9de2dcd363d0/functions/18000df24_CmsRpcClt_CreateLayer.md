# CmsRpcClt_CreateLayer

- ea: `0x18000df24`
- end: `0x18000df6b`
- name: `CmsRpcClt_CreateLayer`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cc78`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000df60`
- `RPCRT4!NdrClientCall3` at `0x18000df60`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateLayer(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x34u, 0, a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18000df24  mov     r11, rsp
0x18000df27  sub     rsp, 58h
0x18000df2b  mov     rax, [rsp+58h+arg_28]
0x18000df33  mov     [r11-18h], rax
0x18000df37  mov     rax, [rsp+58h+arg_20]
0x18000df3f  mov     [r11-20h], rax
0x18000df43  mov     [r11-28h], r9
0x18000df47  mov     r9, rcx
0x18000df4a  mov     [r11-30h], r8
0x18000df4e  lea     rcx, pProxyInfo; pProxyInfo
0x18000df55  xor     r8d, r8d; pReturnValue
0x18000df58  mov     [rsp+58h+var_38], edx
0x18000df5c  lea     edx, [r8+34h]; nProcNum
0x18000df60  call    cs:__imp_NdrClientCall3
0x18000df66  add     rsp, 58h
0x18000df6a  retn
```
