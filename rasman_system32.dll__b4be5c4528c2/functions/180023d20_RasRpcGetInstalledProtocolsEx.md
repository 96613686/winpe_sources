# RasRpcGetInstalledProtocolsEx

- ea: `0x180023d20`
- end: `0x180023d55`
- name: `RasRpcGetInstalledProtocolsEx`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023d43`
- `RPCRT4!NdrClientCall3` at `0x180023d43`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetInstalledProtocolsEx(__int64 a1, int a2, int a3, int a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xEu, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180023d20  sub     rsp, 48h
0x180023d24  mov     [rsp+48h+var_18], r9d
0x180023d29  mov     r9, rcx
0x180023d2c  mov     [rsp+48h+var_20], r8d
0x180023d31  lea     rcx, pProxyInfo; pProxyInfo
0x180023d38  xor     r8d, r8d; pReturnValue
0x180023d3b  mov     [rsp+48h+var_28], edx
0x180023d3f  lea     edx, [r8+0Eh]; nProcNum
0x180023d43  call    cs:__imp_NdrClientCall3
0x180023d4a  nop     dword ptr [rax+rax+00h]
0x180023d4f  add     rsp, 48h
0x180023d53  retn
```
