# EfsRpcReadFileRaw

- ea: `0x18000c730`
- end: `0x18000c755`
- name: `EfsRpcReadFileRaw`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c74a`
- `RPCRT4!NdrClientCall3` at `0x18000c74a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcReadFileRaw(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1, a2);
}

```

## disassembly

```asm
0x18000c730  sub     rsp, 38h
0x18000c734  xor     r8d, r8d; pReturnValue
0x18000c737  mov     [rsp+38h+var_18], rdx
0x18000c73c  mov     r9, rcx
0x18000c73f  lea     rcx, pProxyInfo; pProxyInfo
0x18000c746  lea     edx, [r8+1]; nProcNum
0x18000c74a  call    cs:__imp_NdrClientCall3
0x18000c750  add     rsp, 38h
0x18000c754  retn
```
