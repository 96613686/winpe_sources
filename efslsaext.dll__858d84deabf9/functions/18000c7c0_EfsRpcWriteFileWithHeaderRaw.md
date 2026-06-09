# EfsRpcWriteFileWithHeaderRaw

- ea: `0x18000c7c0`
- end: `0x18000c7f7`
- name: `EfsRpcWriteFileWithHeaderRaw`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c7ec`
- `RPCRT4!NdrClientCall3` at `0x18000c7ec`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcWriteFileWithHeaderRaw(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x17u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000c7c0  sub     rsp, 48h
0x18000c7c4  mov     eax, [rsp+48h+arg_20]
0x18000c7c8  mov     [rsp+48h+var_10], eax
0x18000c7cc  mov     [rsp+48h+var_18], r9
0x18000c7d1  mov     r9, rcx
0x18000c7d4  mov     [rsp+48h+var_20], r8
0x18000c7d9  lea     rcx, pProxyInfo; pProxyInfo
0x18000c7e0  xor     r8d, r8d; pReturnValue
0x18000c7e3  mov     [rsp+48h+var_28], rdx
0x18000c7e8  lea     edx, [r8+17h]; nProcNum
0x18000c7ec  call    cs:__imp_NdrClientCall3
0x18000c7f2  add     rsp, 48h
0x18000c7f6  retn
```
