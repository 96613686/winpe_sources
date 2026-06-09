# HnsRpc_OpenEndpoint

- ea: `0x18000c730`
- end: `0x18000c75f`
- name: `HnsRpc_OpenEndpoint`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c754`
- `RPCRT4!NdrClientCall3` at `0x18000c754`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenEndpoint(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x13u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c730  sub     rsp, 48h
0x18000c734  mov     [rsp+48h+var_18], r9
0x18000c739  mov     r9, rcx
0x18000c73c  mov     [rsp+48h+var_20], r8
0x18000c741  lea     rcx, pProxyInfo; pProxyInfo
0x18000c748  xor     r8d, r8d; pReturnValue
0x18000c74b  mov     [rsp+48h+var_28], rdx
0x18000c750  lea     edx, [r8+13h]; nProcNum
0x18000c754  call    cs:__imp_NdrClientCall3
0x18000c75a  add     rsp, 48h
0x18000c75e  retn
```
