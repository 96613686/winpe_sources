# HnsRpc_QueryGuestNetworkServiceProperties

- ea: `0x18000ca10`
- end: `0x18000ca3f`
- name: `HnsRpc_QueryGuestNetworkServiceProperties`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ca34`
- `RPCRT4!NdrClientCall3` at `0x18000ca34`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_QueryGuestNetworkServiceProperties(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Fu, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ca10  sub     rsp, 48h
0x18000ca14  mov     [rsp+48h+var_18], r9
0x18000ca19  mov     r9, rcx
0x18000ca1c  mov     [rsp+48h+var_20], r8
0x18000ca21  lea     rcx, pProxyInfo; pProxyInfo
0x18000ca28  xor     r8d, r8d; pReturnValue
0x18000ca2b  mov     [rsp+48h+var_28], rdx
0x18000ca30  lea     edx, [r8+2Fh]; nProcNum
0x18000ca34  call    cs:__imp_NdrClientCall3
0x18000ca3a  add     rsp, 48h
0x18000ca3e  retn
```
