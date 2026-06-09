# HnsRpc_UnregisterGuestNetworkServiceNotifications

- ea: `0x18000cd20`
- end: `0x18000cd38`
- name: `HnsRpc_UnregisterGuestNetworkServiceNotifications`
- size: `24`
- prototype: `int(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000cd31`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_UnregisterGuestNetworkServiceNotifications(void *a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x32u, 0, a1);
}

```

## disassembly

```asm
0x18000cd20  xor     r8d, r8d
0x18000cd23  mov     r9, rcx
0x18000cd26  lea     rcx, pProxyInfo
0x18000cd2d  lea     edx, [r8+32h]
0x18000cd31  jmp     cs:__imp_NdrClientCall3
```
