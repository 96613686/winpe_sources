# CmsRpcClt_CommitTransaction

- ea: `0x18000dd30`
- end: `0x18000dd48`
- name: `CmsRpcClt_CommitTransaction`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dd41`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CommitTransaction(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x3Du, 0, a1);
}

```

## disassembly

```asm
0x18000dd30  xor     r8d, r8d
0x18000dd33  mov     r9, rcx
0x18000dd36  lea     rcx, pProxyInfo
0x18000dd3d  lea     edx, [r8+3Dh]
0x18000dd41  jmp     cs:__imp_NdrClientCall3
```
