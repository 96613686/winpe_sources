# EfsRpcRemoveUsersFromFile

- ea: `0x18000c760`
- end: `0x18000c78a`
- name: `EfsRpcRemoveUsersFromFile`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c21c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c77f`
- `RPCRT4!NdrClientCall3` at `0x18000c77f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcRemoveUsersFromFile(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 8u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c760  sub     rsp, 38h
0x18000c764  mov     [rsp+38h+var_10], r8
0x18000c769  mov     r9, rcx
0x18000c76c  xor     r8d, r8d; pReturnValue
0x18000c76f  mov     [rsp+38h+var_18], rdx
0x18000c774  lea     rcx, pProxyInfo; pProxyInfo
0x18000c77b  lea     edx, [r8+8]; nProcNum
0x18000c77f  call    cs:__imp_NdrClientCall3
0x18000c785  add     rsp, 38h
0x18000c789  retn
```
