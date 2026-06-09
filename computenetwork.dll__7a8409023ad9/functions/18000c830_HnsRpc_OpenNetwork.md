# HnsRpc_OpenNetwork

- ea: `0x18000c830`
- end: `0x18000c85f`
- name: `HnsRpc_OpenNetwork`
- size: `47`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c854`
- `RPCRT4!NdrClientCall3` at `0x18000c854`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenNetwork(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c830  sub     rsp, 48h
0x18000c834  mov     [rsp+48h+var_18], r9
0x18000c839  mov     r9, rcx
0x18000c83c  mov     [rsp+48h+var_20], r8
0x18000c841  lea     rcx, pProxyInfo; pProxyInfo
0x18000c848  xor     r8d, r8d; pReturnValue
0x18000c84b  mov     [rsp+48h+var_28], rdx
0x18000c850  lea     edx, [r8+2]; nProcNum
0x18000c854  call    cs:__imp_NdrClientCall3
0x18000c85a  add     rsp, 48h
0x18000c85e  retn
```
