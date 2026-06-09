# HnsRpc_EnumerateGuestNetworkServices

- ea: `0x18000c4d0`
- end: `0x18000c4ff`
- name: `HnsRpc_EnumerateGuestNetworkServices`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c4f4`
- `RPCRT4!NdrClientCall3` at `0x18000c4f4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_EnumerateGuestNetworkServices(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Bu, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c4d0  sub     rsp, 48h
0x18000c4d4  mov     [rsp+48h+var_18], r9
0x18000c4d9  mov     r9, rcx
0x18000c4dc  mov     [rsp+48h+var_20], r8
0x18000c4e1  lea     rcx, pProxyInfo; pProxyInfo
0x18000c4e8  xor     r8d, r8d; pReturnValue
0x18000c4eb  mov     [rsp+48h+var_28], rdx
0x18000c4f0  lea     edx, [r8+2Bh]; nProcNum
0x18000c4f4  call    cs:__imp_NdrClientCall3
0x18000c4fa  add     rsp, 48h
0x18000c4fe  retn
```
