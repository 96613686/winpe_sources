# CmsRpcClt_GetSiloObjectRootPath

- ea: `0x18000e250`
- end: `0x18000e275`
- name: `CmsRpcClt_GetSiloObjectRootPath`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e26a`
- `RPCRT4!NdrClientCall3` at `0x18000e26a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_GetSiloObjectRootPath(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x32u, 0, a1, a2);
}

```

## disassembly

```asm
0x18000e250  sub     rsp, 38h
0x18000e254  xor     r8d, r8d; pReturnValue
0x18000e257  mov     [rsp+38h+var_18], rdx
0x18000e25c  mov     r9, rcx
0x18000e25f  lea     rcx, pProxyInfo; pProxyInfo
0x18000e266  lea     edx, [r8+32h]; nProcNum
0x18000e26a  call    cs:__imp_NdrClientCall3
0x18000e270  add     rsp, 38h
0x18000e274  retn
```
