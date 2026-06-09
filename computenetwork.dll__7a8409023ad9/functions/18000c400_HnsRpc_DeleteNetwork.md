# HnsRpc_DeleteNetwork

- ea: `0x18000c400`
- end: `0x18000c42a`
- name: `HnsRpc_DeleteNetwork`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c41f`
- `RPCRT4!NdrClientCall3` at `0x18000c41f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_DeleteNetwork(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c400  sub     rsp, 38h
0x18000c404  mov     [rsp+38h+var_10], r8
0x18000c409  mov     r9, rcx
0x18000c40c  xor     r8d, r8d; pReturnValue
0x18000c40f  mov     [rsp+38h+var_18], rdx
0x18000c414  lea     rcx, pProxyInfo; pProxyInfo
0x18000c41b  lea     edx, [r8+5]; nProcNum
0x18000c41f  call    cs:__imp_NdrClientCall3
0x18000c425  add     rsp, 38h
0x18000c429  retn
```
