# CmsRpcClt_GetContainerSecurityInformation

- ea: `0x18000e1bc`
- end: `0x18000e1ea`
- name: `CmsRpcClt_GetContainerSecurityInformation`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800024a8`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e1df`
- `RPCRT4!NdrClientCall3` at `0x18000e1df`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_GetContainerSecurityInformation(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x10u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e1bc  sub     rsp, 48h
0x18000e1c0  mov     [rsp+48h+var_18], r9
0x18000e1c5  mov     r9, rcx
0x18000e1c8  mov     [rsp+48h+var_20], r8
0x18000e1cd  lea     rcx, pProxyInfo; pProxyInfo
0x18000e1d4  xor     r8d, r8d; pReturnValue
0x18000e1d7  mov     [rsp+48h+var_28], edx
0x18000e1db  lea     edx, [r8+10h]; nProcNum
0x18000e1df  call    cs:__imp_NdrClientCall3
0x18000e1e5  add     rsp, 48h
0x18000e1e9  retn
```
