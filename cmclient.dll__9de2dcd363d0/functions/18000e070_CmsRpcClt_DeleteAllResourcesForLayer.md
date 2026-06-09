# CmsRpcClt_DeleteAllResourcesForLayer

- ea: `0x18000e070`
- end: `0x18000e095`
- name: `CmsRpcClt_DeleteAllResourcesForLayer`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e08a`
- `RPCRT4!NdrClientCall3` at `0x18000e08a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_DeleteAllResourcesForLayer(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x4Au, 0, a1, a2);
}

```

## disassembly

```asm
0x18000e070  sub     rsp, 38h
0x18000e074  xor     r8d, r8d; pReturnValue
0x18000e077  mov     [rsp+38h+var_18], rdx
0x18000e07c  mov     r9, rcx
0x18000e07f  lea     rcx, pProxyInfo; pProxyInfo
0x18000e086  lea     edx, [r8+4Ah]; nProcNum
0x18000e08a  call    cs:__imp_NdrClientCall3
0x18000e090  add     rsp, 38h
0x18000e094  retn
```
