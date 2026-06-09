# HnsRpc_RegisterGuestNetworkServiceNotifications

- ea: `0x18000cc10`
- end: `0x18000cc3a`
- name: `HnsRpc_RegisterGuestNetworkServiceNotifications`
- size: `42`
- prototype: `int(void *, void **, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000cc2f`
- `RPCRT4!NdrClientCall3` at `0x18000cc2f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_RegisterGuestNetworkServiceNotifications(void *a1, void **a2, void **a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x31u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000cc10  sub     rsp, 38h
0x18000cc14  mov     [rsp+38h+var_10], r8
0x18000cc19  mov     r9, rcx
0x18000cc1c  xor     r8d, r8d; pReturnValue
0x18000cc1f  mov     [rsp+38h+var_18], rdx
0x18000cc24  lea     rcx, pProxyInfo; pProxyInfo
0x18000cc2b  lea     edx, [r8+31h]; nProcNum
0x18000cc2f  call    cs:__imp_NdrClientCall3
0x18000cc35  add     rsp, 38h
0x18000cc39  retn
```
