# HnsRpc_DeleteEndpoint

- ea: `0x18000c340`
- end: `0x18000c36a`
- name: `HnsRpc_DeleteEndpoint`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c35f`
- `RPCRT4!NdrClientCall3` at `0x18000c35f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_DeleteEndpoint(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x16u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c340  sub     rsp, 38h
0x18000c344  mov     [rsp+38h+var_10], r8
0x18000c349  mov     r9, rcx
0x18000c34c  xor     r8d, r8d; pReturnValue
0x18000c34f  mov     [rsp+38h+var_18], rdx
0x18000c354  lea     rcx, pProxyInfo; pProxyInfo
0x18000c35b  lea     edx, [r8+16h]; nProcNum
0x18000c35f  call    cs:__imp_NdrClientCall3
0x18000c365  add     rsp, 38h
0x18000c369  retn
```
