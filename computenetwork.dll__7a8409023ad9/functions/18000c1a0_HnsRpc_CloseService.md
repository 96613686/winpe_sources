# HnsRpc_CloseService

- ea: `0x18000c1a0`
- end: `0x18000c1b8`
- name: `HnsRpc_CloseService`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c1b1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_CloseService(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Au, 0, a1);
}

```

## disassembly

```asm
0x18000c1a0  xor     r8d, r8d
0x18000c1a3  mov     r9, rcx
0x18000c1a6  lea     rcx, pProxyInfo
0x18000c1ad  lea     edx, [r8+2Ah]
0x18000c1b1  jmp     cs:__imp_NdrClientCall3
```
