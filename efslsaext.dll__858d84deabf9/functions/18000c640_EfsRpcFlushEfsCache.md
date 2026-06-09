# EfsRpcFlushEfsCache

- ea: `0x18000c640`
- end: `0x18000c658`
- name: `EfsRpcFlushEfsCache`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bc88`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c651`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcFlushEfsCache(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x14u, 0, a1);
}

```

## disassembly

```asm
0x18000c640  xor     r8d, r8d
0x18000c643  mov     r9, rcx
0x18000c646  lea     rcx, pProxyInfo
0x18000c64d  lea     edx, [r8+14h]
0x18000c651  jmp     cs:__imp_NdrClientCall3
```
