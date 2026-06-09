# HnsRpc_DeleteSdnRoute

- ea: `0x18000c430`
- end: `0x18000c45a`
- name: `HnsRpc_DeleteSdnRoute`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c44f`
- `RPCRT4!NdrClientCall3` at `0x18000c44f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_DeleteSdnRoute(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x24u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c430  sub     rsp, 38h
0x18000c434  mov     [rsp+38h+var_10], r8
0x18000c439  mov     r9, rcx
0x18000c43c  xor     r8d, r8d; pReturnValue
0x18000c43f  mov     [rsp+38h+var_18], rdx
0x18000c444  lea     rcx, pProxyInfo; pProxyInfo
0x18000c44b  lea     edx, [r8+24h]; nProcNum
0x18000c44f  call    cs:__imp_NdrClientCall3
0x18000c455  add     rsp, 38h
0x18000c459  retn
```
