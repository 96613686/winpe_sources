# CmsRpcClt_OpenContainerStorage

- ea: `0x18000e524`
- end: `0x18000e54e`
- name: `CmsRpcClt_OpenContainerStorage`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002814`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e543`
- `RPCRT4!NdrClientCall3` at `0x18000e543`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_OpenContainerStorage(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x30u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000e524  sub     rsp, 38h
0x18000e528  mov     [rsp+38h+var_10], r8
0x18000e52d  mov     r9, rcx
0x18000e530  xor     r8d, r8d; pReturnValue
0x18000e533  mov     [rsp+38h+var_18], rdx
0x18000e538  lea     rcx, pProxyInfo; pProxyInfo
0x18000e53f  lea     edx, [r8+30h]; nProcNum
0x18000e543  call    cs:__imp_NdrClientCall3
0x18000e549  add     rsp, 38h
0x18000e54d  retn
```
