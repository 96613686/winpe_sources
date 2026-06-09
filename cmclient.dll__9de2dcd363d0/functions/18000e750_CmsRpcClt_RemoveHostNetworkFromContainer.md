# CmsRpcClt_RemoveHostNetworkFromContainer

- ea: `0x18000e750`
- end: `0x18000e775`
- name: `CmsRpcClt_RemoveHostNetworkFromContainer`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e76a`
- `RPCRT4!NdrClientCall3` at `0x18000e76a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_RemoveHostNetworkFromContainer(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Cu, 0, a1, a2);
}

```

## disassembly

```asm
0x18000e750  sub     rsp, 38h
0x18000e754  xor     r8d, r8d; pReturnValue
0x18000e757  mov     [rsp+38h+var_18], rdx
0x18000e75c  mov     r9, rcx
0x18000e75f  lea     rcx, pProxyInfo; pProxyInfo
0x18000e766  lea     edx, [r8+1Ch]; nProcNum
0x18000e76a  call    cs:__imp_NdrClientCall3
0x18000e770  add     rsp, 38h
0x18000e774  retn
```
