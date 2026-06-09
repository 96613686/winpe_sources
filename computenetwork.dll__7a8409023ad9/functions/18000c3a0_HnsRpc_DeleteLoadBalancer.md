# HnsRpc_DeleteLoadBalancer

- ea: `0x18000c3a0`
- end: `0x18000c3ca`
- name: `HnsRpc_DeleteLoadBalancer`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c3bf`
- `RPCRT4!NdrClientCall3` at `0x18000c3bf`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_DeleteLoadBalancer(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Du, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c3a0  sub     rsp, 38h
0x18000c3a4  mov     [rsp+38h+var_10], r8
0x18000c3a9  mov     r9, rcx
0x18000c3ac  xor     r8d, r8d; pReturnValue
0x18000c3af  mov     [rsp+38h+var_18], rdx
0x18000c3b4  lea     rcx, pProxyInfo; pProxyInfo
0x18000c3bb  lea     edx, [r8+1Dh]; nProcNum
0x18000c3bf  call    cs:__imp_NdrClientCall3
0x18000c3c5  add     rsp, 38h
0x18000c3c9  retn
```
