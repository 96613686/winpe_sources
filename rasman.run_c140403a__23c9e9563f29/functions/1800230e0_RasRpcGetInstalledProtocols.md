# RasRpcGetInstalledProtocols

- ea: `0x1800230e0`
- end: `0x1800230f8`
- name: `RasRpcGetInstalledProtocols`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800230f1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetInstalledProtocols(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 8u, 0, a1);
}

```

## disassembly

```asm
0x1800230e0  xor     r8d, r8d
0x1800230e3  mov     r9, rcx
0x1800230e6  lea     rcx, pProxyInfo
0x1800230ed  lea     edx, [r8+8]
0x1800230f1  jmp     cs:__imp_NdrClientCall3
```
