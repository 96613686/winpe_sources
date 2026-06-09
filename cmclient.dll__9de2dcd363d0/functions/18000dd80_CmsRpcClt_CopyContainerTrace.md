# CmsRpcClt_CopyContainerTrace

- ea: `0x18000dd80`
- end: `0x18000dda5`
- name: `CmsRpcClt_CopyContainerTrace`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dd9a`
- `RPCRT4!NdrClientCall3` at `0x18000dd9a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CopyContainerTrace(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x4Cu, 0, a1, a2);
}

```

## disassembly

```asm
0x18000dd80  sub     rsp, 38h
0x18000dd84  xor     r8d, r8d; pReturnValue
0x18000dd87  mov     [rsp+38h+var_18], rdx
0x18000dd8c  mov     r9, rcx
0x18000dd8f  lea     rcx, pProxyInfo; pProxyInfo
0x18000dd96  lea     edx, [r8+4Ch]; nProcNum
0x18000dd9a  call    cs:__imp_NdrClientCall3
0x18000dda0  add     rsp, 38h
0x18000dda4  retn
```
