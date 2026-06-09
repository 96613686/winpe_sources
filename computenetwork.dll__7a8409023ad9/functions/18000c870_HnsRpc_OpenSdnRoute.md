# HnsRpc_OpenSdnRoute

- ea: `0x18000c870`
- end: `0x18000c89f`
- name: `HnsRpc_OpenSdnRoute`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c894`
- `RPCRT4!NdrClientCall3` at `0x18000c894`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenSdnRoute(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x21u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c870  sub     rsp, 48h
0x18000c874  mov     [rsp+48h+var_18], r9
0x18000c879  mov     r9, rcx
0x18000c87c  mov     [rsp+48h+var_20], r8
0x18000c881  lea     rcx, pProxyInfo; pProxyInfo
0x18000c888  xor     r8d, r8d; pReturnValue
0x18000c88b  mov     [rsp+48h+var_28], rdx
0x18000c890  lea     edx, [r8+21h]; nProcNum
0x18000c894  call    cs:__imp_NdrClientCall3
0x18000c89a  add     rsp, 48h
0x18000c89e  retn
```
