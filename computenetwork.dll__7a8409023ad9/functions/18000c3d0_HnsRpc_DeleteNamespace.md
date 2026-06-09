# HnsRpc_DeleteNamespace

- ea: `0x18000c3d0`
- end: `0x18000c3fa`
- name: `HnsRpc_DeleteNamespace`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c3ef`
- `RPCRT4!NdrClientCall3` at `0x18000c3ef`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_DeleteNamespace(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c3d0  sub     rsp, 38h
0x18000c3d4  mov     [rsp+38h+var_10], r8
0x18000c3d9  mov     r9, rcx
0x18000c3dc  xor     r8d, r8d; pReturnValue
0x18000c3df  mov     [rsp+38h+var_18], rdx
0x18000c3e4  lea     rcx, pProxyInfo; pProxyInfo
0x18000c3eb  lea     edx, [r8+0Fh]; nProcNum
0x18000c3ef  call    cs:__imp_NdrClientCall3
0x18000c3f5  add     rsp, 38h
0x18000c3f9  retn
```
