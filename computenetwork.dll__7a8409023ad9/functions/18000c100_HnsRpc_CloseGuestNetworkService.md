# HnsRpc_CloseGuestNetworkService

- ea: `0x18000c100`
- end: `0x18000c118`
- name: `HnsRpc_CloseGuestNetworkService`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c111`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CloseGuestNetworkService(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x34u, 0, a1);
}

```

## disassembly

```asm
0x18000c100  xor     r8d, r8d
0x18000c103  mov     r9, rcx
0x18000c106  lea     rcx, pProxyInfo
0x18000c10d  lea     edx, [r8+34h]
0x18000c111  jmp     cs:__imp_NdrClientCall3
```
