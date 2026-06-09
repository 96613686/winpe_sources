# HnsRpc_OpenGuestNetworkService

- ea: `0x18000c770`
- end: `0x18000c79f`
- name: `HnsRpc_OpenGuestNetworkService`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c794`
- `RPCRT4!NdrClientCall3` at `0x18000c794`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenGuestNetworkService(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Du, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c770  sub     rsp, 48h
0x18000c774  mov     [rsp+48h+var_18], r9
0x18000c779  mov     r9, rcx
0x18000c77c  mov     [rsp+48h+var_20], r8
0x18000c781  lea     rcx, pProxyInfo; pProxyInfo
0x18000c788  xor     r8d, r8d; pReturnValue
0x18000c78b  mov     [rsp+48h+var_28], rdx
0x18000c790  lea     edx, [r8+2Dh]; nProcNum
0x18000c794  call    cs:__imp_NdrClientCall3
0x18000c79a  add     rsp, 48h
0x18000c79e  retn
```
