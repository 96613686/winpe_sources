# EfsRpcWriteFileRaw

- ea: `0x18000c790`
- end: `0x18000c7b5`
- name: `EfsRpcWriteFileRaw`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c7aa`
- `RPCRT4!NdrClientCall3` at `0x18000c7aa`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcWriteFileRaw(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2);
}

```

## disassembly

```asm
0x18000c790  sub     rsp, 38h
0x18000c794  xor     r8d, r8d; pReturnValue
0x18000c797  mov     [rsp+38h+var_18], rdx
0x18000c79c  mov     r9, rcx
0x18000c79f  lea     rcx, pProxyInfo; pProxyInfo
0x18000c7a6  lea     edx, [r8+2]; nProcNum
0x18000c7aa  call    cs:__imp_NdrClientCall3
0x18000c7b0  add     rsp, 38h
0x18000c7b4  retn
```
