# HnsRpc_UnregisterServiceNotifications

- ea: `0x18000cd60`
- end: `0x18000cd78`
- name: `HnsRpc_UnregisterServiceNotifications`
- size: `24`
- prototype: `int(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000cd71`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_UnregisterServiceNotifications(void *a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x28u, 0, a1);
}

```

## disassembly

```asm
0x18000cd60  xor     r8d, r8d
0x18000cd63  mov     r9, rcx
0x18000cd66  lea     rcx, pProxyInfo
0x18000cd6d  lea     edx, [r8+28h]
0x18000cd71  jmp     cs:__imp_NdrClientCall3
```
