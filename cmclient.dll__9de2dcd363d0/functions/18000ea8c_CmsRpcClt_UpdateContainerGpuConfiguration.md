# CmsRpcClt_UpdateContainerGpuConfiguration

- ea: `0x18000ea8c`
- end: `0x18000eab1`
- name: `CmsRpcClt_UpdateContainerGpuConfiguration`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, installer_update`

## callers

- `0x180002608`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000eaa6`
- `RPCRT4!NdrClientCall3` at `0x18000eaa6`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_UpdateContainerGpuConfiguration(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x26u, 0, a1, a2);
}

```

## disassembly

```asm
0x18000ea8c  sub     rsp, 38h
0x18000ea90  xor     r8d, r8d; pReturnValue
0x18000ea93  mov     [rsp+38h+var_18], rdx
0x18000ea98  mov     r9, rcx
0x18000ea9b  lea     rcx, pProxyInfo; pProxyInfo
0x18000eaa2  lea     edx, [r8+26h]; nProcNum
0x18000eaa6  call    cs:__imp_NdrClientCall3
0x18000eaac  add     rsp, 38h
0x18000eab0  retn
```
