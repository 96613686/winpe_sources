# CmsRpcClt_OpenContainerMemoryHostingProcess

- ea: `0x18000e4f4`
- end: `0x18000e51d`
- name: `CmsRpcClt_OpenContainerMemoryHostingProcess`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b578`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e512`
- `RPCRT4!NdrClientCall3` at `0x18000e512`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenContainerMemoryHostingProcess(__int64 a1, int a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x15u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000e4f4  sub     rsp, 38h
0x18000e4f8  mov     [rsp+38h+var_10], r8
0x18000e4fd  mov     r9, rcx
0x18000e500  xor     r8d, r8d; pReturnValue
0x18000e503  mov     [rsp+38h+var_18], edx
0x18000e507  lea     rcx, pProxyInfo; pProxyInfo
0x18000e50e  lea     edx, [r8+15h]; nProcNum
0x18000e512  call    cs:__imp_NdrClientCall3
0x18000e518  add     rsp, 38h
0x18000e51c  retn
```
