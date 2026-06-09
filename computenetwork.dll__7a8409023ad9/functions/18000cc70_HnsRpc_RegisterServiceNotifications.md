# HnsRpc_RegisterServiceNotifications

- ea: `0x18000cc70`
- end: `0x18000cc9a`
- name: `HnsRpc_RegisterServiceNotifications`
- size: `42`
- prototype: `int(void *, void **, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000cc8f`
- `RPCRT4!NdrClientCall3` at `0x18000cc8f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_RegisterServiceNotifications(void *a1, void **a2, void **a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x27u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000cc70  sub     rsp, 38h
0x18000cc74  mov     [rsp+38h+var_10], r8
0x18000cc79  mov     r9, rcx
0x18000cc7c  xor     r8d, r8d; pReturnValue
0x18000cc7f  mov     [rsp+38h+var_18], rdx
0x18000cc84  lea     rcx, pProxyInfo; pProxyInfo
0x18000cc8b  lea     edx, [r8+27h]; nProcNum
0x18000cc8f  call    cs:__imp_NdrClientCall3
0x18000cc95  add     rsp, 38h
0x18000cc99  retn
```
